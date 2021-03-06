---
title: Host ASP.NET Core no Linux com Nginx
author: rick-anderson
description: "Descreve como configurar Nginx como um proxy reverso no Ubuntu 16.04 para encaminhar o tráfego HTTP para um aplicativo web do ASP.NET Core em execução no Kestrel."
manager: wpickett
ms.author: riande
ms.custom: mvc
ms.date: 08/21/2017
ms.prod: asp.net-core
ms.technology: aspnet
ms.topic: article
uid: host-and-deploy/linux-nginx
ms.openlocfilehash: 1044a87a4dcc7636413078b0fc09ade206c97d0a
ms.sourcegitcommit: b83a5f731a9c02bdb1cc1e3f9a8bf273eb5b33e0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2018
---
# <a name="host-aspnet-core-on-linux-with-nginx"></a>Host ASP.NET Core no Linux com Nginx

Por [Sourabh Shirhatti](https://twitter.com/sshirhatti)

Este guia explica como configurar um ambiente do ASP.NET Core pronto para produção em um servidor do Ubuntu 16.04.

**Observação:** para Ubuntu 14.04 *supervisord* é recomendado como uma solução para monitorar o processo de Kestrel. *systemd* não está disponível no Ubuntu 14.04. [Consulte a versão anterior deste documento](https://github.com/aspnet/Docs/blob/e9c1419175c4dd7e152df3746ba1df5935aaafd5/aspnetcore/publishing/linuxproduction.md)

Este guia:

* Coloca um aplicativo ASP.NET Core existente em um servidor proxy reverso.
* Configura o servidor proxy inverso para encaminhar solicitações ao servidor da web Kestrel.
* Garante que o aplicativo web é executado na inicialização como um daemon.
* Configura uma ferramenta de gerenciamento de processo para ajudar a reiniciar o aplicativo web.

## <a name="prerequisites"></a>Pré-requisitos

1. Acesso a um Servidor Ubuntu 16.04 com uma conta de usuário padrão com privilégio sudo
1. Um aplicativo ASP.NET Core existente

## <a name="copy-over-the-app"></a>Copie o aplicativo

Executar `dotnet publish` do ambiente de desenvolvimento para empacotar um aplicativo em um diretório autocontido que pode ser executado no servidor.

O aplicativo ASP.NET Core para o servidor usando qualquer ferramenta de cópia se integra ao fluxo de trabalho da organização (por exemplo, "SCP", "FTP"). Teste o aplicativo, por exemplo:

* Na linha de comando, execute `dotnet <app_assembly>.dll`.
* Em um navegador, navegue até `http://<serveraddress>:<port>` para verificar se o aplicativo funciona no Linux. 
 
## <a name="configure-a-reverse-proxy-server"></a>Configurar um servidor proxy reverso

Um proxy reverso é uma instalação comum para que serve a aplicativos web dinâmicos. Um proxy reverso encerra a solicitação HTTP e as encaminha para o aplicativo ASP.NET Core.

### <a name="why-use-a-reverse-proxy-server"></a>Por que usar um servidor proxy reverso?

Kestrel é excelente para servir conteúdo dinâmico do ASP.NET Core. No entanto, os recursos de servidor web não são como muitos recursos como servidores, como o IIS, o Apache ou Nginx. Um servidor proxy reverso pode descarregar o trabalho, como que serve o conteúdo estático, solicitações de cache, a compactação de solicitações e a terminação de SSL do servidor HTTP. Um servidor proxy reverso pode residir em um computador dedicado ou pode ser implantado junto com um servidor HTTP.

Para os fins deste guia, uma única instância de Nginx é usada. Ela é executada no mesmo servidor, junto com o servidor HTTP. Com base nos requisitos, uma configuração diferente pode ser escolhida.

Como as solicitações são encaminhadas pelo proxy reverso, use o Middleware de cabeçalhos encaminhados do [Microsoft.AspNetCore.HttpOverrides](https://www.nuget.org/packages/Microsoft.AspNetCore.HttpOverrides/) pacote. As atualizações de middleware de `Request.Scheme`, usando o `X-Forwarded-Proto` cabeçalho, de forma que URIs de redirecionamento e outras políticas de segurança funcionam corretamente.

Ao usar qualquer tipo de middleware de autenticação, o Middleware de cabeçalhos encaminhado deve ser executado primeiro. Essa ordenação garantirá que o middleware de autenticação pode consumir os valores de cabeçalho e gerar URIs de redirecionamento correto.

# <a name="aspnet-core-2xtabaspnetcore2x"></a>[ASP.NET Core 2.x](#tab/aspnetcore2x)

Invocar o [UseForwardedHeaders](/dotnet/api/microsoft.aspnetcore.builder.forwardedheadersextensions.useforwardedheaders) método `Startup.Configure` antes de chamar [UseAuthentication](/dotnet/api/microsoft.aspnetcore.builder.authappbuilderextensions.useauthentication) ou semelhante middleware de esquema de autenticação:

```csharp
app.UseForwardedHeaders(new ForwardedHeadersOptions
{
    ForwardedHeaders = ForwardedHeaders.XForwardedFor | ForwardedHeaders.XForwardedProto
});

app.UseAuthentication();
```

# <a name="aspnet-core-1xtabaspnetcore1x"></a>[ASP.NET Core 1.x](#tab/aspnetcore1x)

Invocar o [UseForwardedHeaders](/dotnet/api/microsoft.aspnetcore.builder.forwardedheadersextensions.useforwardedheaders) método `Startup.Configure` antes de chamar [UseIdentity](/dotnet/api/microsoft.aspnetcore.builder.builderextensions.useidentity) e [UseFacebookAuthentication](/dotnet/api/microsoft.aspnetcore.builder.facebookappbuilderextensions.usefacebookauthentication) ou esquema de autenticação semelhantes middleware:

```csharp
app.UseForwardedHeaders(new ForwardedHeadersOptions
{
    ForwardedHeaders = ForwardedHeaders.XForwardedFor | ForwardedHeaders.XForwardedProto
});

app.UseIdentity();
app.UseFacebookAuthentication(new FacebookOptions()
{
    AppId = Configuration["Authentication:Facebook:AppId"],
    AppSecret = Configuration["Authentication:Facebook:AppSecret"]
});
```

---

Se nenhum [ForwardedHeadersOptions](/dotnet/api/microsoft.aspnetcore.builder.forwardedheadersoptions) são especificados para o middleware, os cabeçalhos padrão para encaminhar são `None`.

### <a name="install-nginx"></a>Instalar o Nginx

```bash
sudo apt-get install nginx
```

> [!NOTE]
> Se módulos Nginx opcionais serão instalados, pode ser necessário criar Nginx da fonte.

Use `apt-get` para instalar o Nginx. O instalador cria um script de inicialização System V que executa o Nginx como daemon na inicialização do sistema. Já que Nginx foi instalado pela primeira vez, inicie-o explicitamente executando:

```bash
sudo service nginx start
```

Verifique se um navegador exibe a página de aterrissagem padrão do Nginx.

### <a name="configure-nginx"></a>Configurar o Nginx

Para configurar Nginx como um proxy inverso para encaminhar solicitações para o nosso aplicativo ASP.NET Core, modifique `/etc/nginx/sites-available/default`. Abra-o em um editor de texto arquivo e substitua o conteúdo pelo mostrado a seguir:

```
server {
    listen 80;
    location / {
        proxy_pass http://localhost:5000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection keep-alive;
        proxy_set_header Host $http_host;
        proxy_cache_bypass $http_upgrade;
    }
}
```

Esse arquivo de configuração do Nginx encaminha tráfego público de entrada da porta `80` para a porta `5000`.

Quando a configuração Nginx é estabelecida, execute `sudo nginx -t` para verificar a sintaxe dos arquivos de configuração. Se o teste do arquivo de configuração for bem-sucedida, forçar Nginx para acompanhar as alterações executando `sudo nginx -s reload`.

## <a name="monitoring-the-app"></a>Monitoramento do aplicativo

O servidor está configurado para encaminhar solicitações feitas a `http://<serveraddress>:80` para o aplicativo ASP.NET Core em execução em Kestrel em `http://127.0.0.1:5000`. No entanto, Nginx não está configurado para gerenciar o processo de Kestrel. *systemd* pode ser usado para criar um arquivo de serviço para iniciar e monitorar o aplicativo web subjacente. *systemd* é um sistema de inicialização que fornece muitos recursos poderosos para iniciar, parar e gerenciar processos. 

### <a name="create-the-service-file"></a>Criar o arquivo de serviço

Crie o arquivo de definição de serviço:

```bash
sudo nano /etc/systemd/system/kestrel-hellomvc.service
```

Este é um exemplo de arquivo de serviço para o aplicativo:

```ini
[Unit]
Description=Example .NET Web API App running on Ubuntu

[Service]
WorkingDirectory=/var/aspnetcore/hellomvc
ExecStart=/usr/bin/dotnet /var/aspnetcore/hellomvc/hellomvc.dll
Restart=always
RestartSec=10  # Restart service after 10 seconds if dotnet service crashes
SyslogIdentifier=dotnet-example
User=www-data
Environment=ASPNETCORE_ENVIRONMENT=Production
Environment=DOTNET_PRINT_TELEMETRY_MESSAGE=false

[Install]
WantedBy=multi-user.target
```

**Observação:** se o usuário *www dados* não é usado pela configuração do usuário definido aqui deve ser criado primeiro e dado propriedade adequada para arquivos.
**Observação:** Linux tem um sistema de arquivos diferencia maiusculas de minúsculas. Definindo ASPNETCORE_ENVIRONMENT como resultados de "Produção" na pesquisa do arquivo de configuração *appsettings. Production.JSON*, não *appsettings.production.json*.

Salve o arquivo e habilite o serviço.

```bash
systemctl enable kestrel-hellomvc.service
```

Inicie o serviço e verifique se ele está em execução.

```
systemctl start kestrel-hellomvc.service
systemctl status kestrel-hellomvc.service

● kestrel-hellomvc.service - Example .NET Web API App running on Ubuntu
    Loaded: loaded (/etc/systemd/system/kestrel-hellomvc.service; enabled)
    Active: active (running) since Thu 2016-10-18 04:09:35 NZDT; 35s ago
Main PID: 9021 (dotnet)
    CGroup: /system.slice/kestrel-hellomvc.service
            └─9021 /usr/local/bin/dotnet /var/aspnetcore/hellomvc/hellomvc.dll
```

Com o proxy reverso configurado e Kestrel gerenciadas por meio de systemd, o aplicativo web está totalmente configurado e pode ser acessado a partir de um navegador no computador local em `http://localhost`. Também é acessível a partir de um computador remoto, bloqueio qualquer firewall pode estar bloqueando. Inspecionando os cabeçalhos de resposta, o `Server` cabeçalho mostra o aplicativo do ASP.NET Core sendo servido por Kestrel.

```text
HTTP/1.1 200 OK
Date: Tue, 11 Oct 2016 16:22:23 GMT
Server: Kestrel
Keep-Alive: timeout=5, max=98
Connection: Keep-Alive
Transfer-Encoding: chunked
```

### <a name="viewing-logs"></a>Exibindo logs

Desde que o aplicativo web usar Kestrel é gerenciada usando `systemd`, todos os eventos e os processos são registrados para um diário centralizado. No entanto, esse diário contém todas as entradas para todos os serviços e processos gerenciados pelo `systemd`. Para exibir os itens específicos de `kestrel-hellomvc.service`, use o seguinte comando:

```bash
sudo journalctl -fu kestrel-hellomvc.service
```

Para obter mais filtragem, opções de hora como `--since today`, `--until 1 hour ago` ou uma combinação delas, pode reduzir a quantidade de entradas retornadas.

```bash
sudo journalctl -fu kestrel-hellomvc.service --since "2016-10-18" --until "2016-10-18 04:00"
```

## <a name="securing-the-app"></a>Protegendo o aplicativo

### <a name="enable-apparmor"></a>Habilitar AppArmor

Módulos de segurança do Linux (LSM) é uma estrutura que é parte do kernel do Linux desde 2.6 do Linux. O LSM dá suporte a diferentes implementações de módulos de segurança. O [AppArmor](https://wiki.ubuntu.com/AppArmor) é um LSM que implementa um sistema de controle de acesso obrigatório que permite restringir o programa a um conjunto limitado de recursos. Verifique se o AppArmor está habilitado e configurado corretamente.

### <a name="configuring-the-firewall"></a>Configurando o firewall

Feche todas as portas externas que não estão em uso. Firewall descomplicado (ufw) fornece um front-end para `iptables` fornecendo uma interface de linha de comando para configurar o firewall. Verifique `ufw` está configurado para permitir o tráfego em todas as portas necessárias.

```bash
sudo apt-get install ufw
sudo ufw enable

sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
```

### <a name="securing-nginx"></a>Protegendo o Nginx

A distribuição padrão do Nginx não habilita o SSL. Para habilitar recursos de segurança adicionais, compile da origem.

#### <a name="download-the-source-and-install-the-build-dependencies"></a>Baixe a origem e instale as dependências de build

```bash
# Install the build dependencies
sudo apt-get update
sudo apt-get install build-essential zlib1g-dev libpcre3-dev libssl-dev libxslt1-dev libxml2-dev libgd2-xpm-dev libgeoip-dev libgoogle-perftools-dev libperl-dev

# Download Nginx 1.10.0 or latest
wget http://www.nginx.org/download/nginx-1.10.0.tar.gz
tar zxf nginx-1.10.0.tar.gz
```

#### <a name="change-the-nginx-response-name"></a>Alterar o nome da resposta do Nginx

Edite *src/http/ngx_http_header_filter_module.c*:

```c
static char ngx_http_server_string[] = "Server: Web Server" CRLF;
static char ngx_http_server_full_string[] = "Server: Web Server" CRLF;
```

#### <a name="configure-the-options-and-build"></a>Configurar as opções e compilar

A biblioteca PCRE é necessária para expressões regulares. Expressões regulares são usadas na diretiva local para o ngx_http_rewrite_module. O http_ssl_module adiciona suporte a protocolo HTTPS.

Considere o uso de um firewall de aplicativo da web como *ModSecurity* para proteger o aplicativo.

```bash
./configure
--with-pcre=../pcre-8.38
--with-zlib=../zlib-1.2.8
--with-http_ssl_module
--with-stream
--with-mail=dynamic
```

#### <a name="configure-ssl"></a>Configurar o SSL

* Configurar o servidor para ouvir o tráfego HTTPS na porta `443` especificando um certificado válido emitido por uma autoridade de certificação confiável (CA).

* Proteger a segurança, empregando algumas das práticas descritas na seguinte */etc/nginx/nginx.conf* arquivo. Exemplos incluem a escolha de uma criptografia mais forte e o redirecionamento de todo o tráfego por meio de HTTP para HTTPS.

* Adicionar um cabeçalho `HTTP Strict-Transport-Security` (HSTS) garante que todas as solicitações subsequentes feitas pelo cliente sejam apenas via HTTPS.

* Não adicione o cabeçalho de segurança de transporte Strict ou escolher um apropriado `max-age` se SSL será desabilitado no futuro.

Adicione o arquivo de configuração */etc/nginx/proxy.conf*:

[!code-nginx[Main](linux-nginx/proxy.conf)]

Edite o arquivo de configuração */etc/nginx/nginx.conf*. O exemplo contém ambas as seções `http` e `server` em um arquivo de configuração.

[!code-nginx[Main](linux-nginx/nginx.conf?highlight=2)]

#### <a name="secure-nginx-from-clickjacking"></a>Proteger o Nginx de clickjacking
Clickjacking é uma técnica mal-intencionada para coletar cliques de um usuário infectado. O clickjacking engana a vítima (visitante) fazendo-a clicar em um site infectado. Use X-FRAME-OPTIONS para proteger o site.

Edite o arquivo *nginx.conf*:

```bash
sudo nano /etc/nginx/nginx.conf
```

Adicione a linha `add_header X-Frame-Options "SAMEORIGIN";` e salve o arquivo, depois reinicie o Nginx.

#### <a name="mime-type-sniffing"></a>Detecção de tipo MIME

Esse cabeçalho evita que a maioria dos navegadores faça detecção MIME de uma resposta distante do tipo de conteúdo declarado, visto que o cabeçalho instrui o navegador para não substituir o tipo de conteúdo de resposta. Com a opção `nosniff`, se o servidor informa que o conteúdo é "text/html", o navegador renderiza-a como "text/html".

Edite o arquivo *nginx.conf*:

```bash
sudo nano /etc/nginx/nginx.conf
```

Adicione a linha `add_header X-Content-Type-Options "nosniff";` e salve o arquivo, depois reinicie o Nginx.
