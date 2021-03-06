---
uid: signalr/overview/getting-started/supported-platforms
title: Plataformas com suporte | Microsoft Docs
author: pfletcher
description: "Este artigo descreve quais clientes e servidores são suportados pelo SignalR."
ms.author: aspnetcontent
manager: wpickett
ms.date: 06/10/2014
ms.topic: article
ms.assetid: eac31beb-0f46-4afa-9def-e80904dea4f0
ms.technology: dotnet-signalr
ms.prod: .net-framework
msc.legacyurl: /signalr/overview/getting-started/supported-platforms
msc.type: authoredcontent
ms.openlocfilehash: 1379b9fb638f67896d88d7aa4312d95280ef7318
ms.sourcegitcommit: a510f38930abc84c4b302029d019a34dfe76823b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2018
---
<a name="supported-platforms"></a>Plataformas compatíveis
====================
por [Patrick Fletcher](https://github.com/pfletcher)

> Este artigo descreve quais clientes e servidores são suportados pelo SignalR. 
> 
> ## <a name="questions-and-comments"></a>Perguntas e comentários
> 
> Deixe comentários em como você gostou neste tutorial e o que podemos melhorar nos comentários na parte inferior da página. Se você tiver dúvidas que não estão diretamente relacionadas ao tutorial, você poderá postá-los para o [ASP.NET SignalR fórum](https://forums.asp.net/1254.aspx/1?ASP+NET+SignalR) ou [StackOverflow.com](http://stackoverflow.com/).


Há suporte para o SignalR em uma variedade de configurações de cliente e servidor. Além disso, cada opção de transporte tem um conjunto de requisitos de sua própria; Se os requisitos de sistema para um transporte não estiverem disponíveis, SignalR normalmente ocorrerá o failover para outros transportes. Para obter mais informações sobre os transportes que dá suporte ao SignalR, consulte [transportes e Fallbacks](introduction-to-signalr.md#transports).

## <a name="server-system-requirements"></a>Requisitos de sistema do servidor

O componente de servidor do SignalR pode ser hospedado em uma variedade de configurações do servidor. Esta seção descreve as versões com suporte dos sistemas operacionais, .NET framework, Internet Information Server e outros componentes.

### <a name="supported-server-operating-systems"></a>Sistemas operacionais de servidor compatíveis

O componente de servidor do SignalR pode ser hospedado no servidor ou cliente de sistemas operacionais a seguir. Observe que para o SignalR usar o WebSocket, Windows Server 2012 ou Windows 8 é necessário (WebSocket pode ser usado no Windows Azure Web Sites, desde que a versão do .NET framework do site é definido como 4.5 e soquetes da Web está habilitado na página de configuração do site).

- Windows Server 2012
- Windows Server 2008 r2
- Windows 10
- Windows 8
- Windows 7
- Microsoft Azure

### <a name="supported-server-net-framework-version"></a>Versão do servidor com suporte do .NET Framework

Somente há suporte para o SignalR 2 no .NET Framework 4.5. Consulte o [atualizações recomendadas](#updates) seção atualizações que melhoram a confiabilidade, compatibilidade, estabilidade e desempenho.

### <a name="supported-server-iis-versions"></a>Versões de servidor com suporte do IIS

Quando o SignalR é hospedado no IIS, as seguintes versões têm suporte. Observe que se um sistema operacional cliente for usado, como para desenvolvimento (Windows 8 ou Windows 7), versões completas do IIS ou Cassini não devem ser usadas, desde que haja um limite de 10 conexões simultâneas imposto, que seja atingido muito rapidamente desde que as conexões transitório, com frequência restabelecida e são não descartadas imediatamente após não mais em uso. O IIS Express deve ser usado em sistemas operacionais cliente.

Observe também que para o SignalR usar o WebSocket, IIS 8 ou Express do IIS 8 deve ser usado, o servidor deve estar usando o Windows 8, Windows Server 2012 ou posterior, e WebSocket deve ser habilitada no IIS. Para obter informações sobre como habilitar o WebSocket no IIS, consulte [suporte de protocolo WebSocket do IIS 8.0](https://www.iis.net/learn/get-started/whats-new-in-iis-8/iis-80-websocket-protocol-support).

- IIS 8 ou o IIS 8 Express.
- IIS 7 e 7.5. Suporte para [URLs sem extensão](https://support.microsoft.com/kb/980368) é necessária.
- O IIS deve estar em execução no modo integrado; Não há suporte para o modo clássico. Podem ocorrer atrasos de mensagem de até 30 segundos se o IIS é executado no modo clássico, usando o transporte Server-Sent eventos.
- O aplicativo de hospedagem deve estar em execução no modo de confiança total.

## <a name="client-system-requirements"></a>Requisitos do sistema cliente

SignalR pode ser usado em uma variedade de plataformas de cliente. Esta seção descreve os requisitos de sistema para usar o SignalR em navegadores da web, aplicativos de área de trabalho do Windows, os aplicativos do Silverlight e dispositivos móveis.

### <a name="web-browsers"></a>Navegadores da Web

SignalR pode ser usado em uma variedade de navegadores da web, mas em geral, apenas as duas versões mais recentes têm suporte.

Aplicativos que usam o SignalR em navegadores devem usar a versão de jQuery 1.6.4 ou versões posteriores principais (como 1.7.2, 1.8.2 ou 1.9.1).

SignalR pode ser usado nos seguintes navegadores:

- Versões do Microsoft Internet Explorer 8, 9, 10 e 11. Moderno, Desktop e móveis versões têm suporte.
- Mozilla Firefox: versão de atual - 1, versões do Windows e Mac.
- Google Chrome: versão atual - 1, versões do Windows e Mac.
- Safari: versão atual - 1, versões de Mac e iOS.
- Opera: versão atual - 1, somente o Windows.
- Navegador do Android

Além de exigir que determinados navegadores, vários meios de transporte SignalR usa têm requisitos de seus próprios. Os transportes a seguir são suportados sob as seguintes configurações:

<a id="browser"></a>

**Requisitos de transporte do navegador da Web**

| Transporte | Internet Explorer | Chrome (Windows ou iOS) | Firefox | Safari (OSX ou iOS) | Android |
| --- | --- | --- | --- | --- | --- |
| WebSockets | 10+ | atual - 1 | atual - 1 | atual - 1 | N/D |
| Eventos enviados pelo servidor | N/D | atual - 1 | atual - 1 | atual - 1 | N/D |
| ForeverFrame | 8+ | N/D | N/D | N/D | 4.1 |
| Sondagem longa | 8+ | atual - 1 | atual - 1 | atual - 1 | 4.1 |

\*: 6 + necessária para a funcionalidade completa.

#### <a name="unsupported-browsers"></a>Navegadores sem suporte

Enquanto o SignalR *pode* executados sem problemas principais em versões mais antigas do navegador, nós não teste ativamente SignalR neles e geralmente não corrigir erros que podem aparecer em-los.

### <a name="windows-desktop-and-silverlight-applications"></a>Área de trabalho do Windows e aplicativos do Silverlight

Além de executar em um navegador da web, SignalR pode ser hospedado no cliente do Windows autônoma ou aplicativos do Silverlight. Aplicativos de área de trabalho do Windows e o Silverlight SignalR têm os seguintes requisitos de sistema.

- Aplicativos usando o .NET 4 têm suporte no Windows XP SP3 ou posterior.
- Aplicativos que usam o .NET Framework 4.5 têm suporte no Windows Vista ou posterior.

Além de sistema operacional e requisitos do .NET framework, os transportes disponíveis para o SignalR têm requisitos de seus próprios. Os transportes a seguir são suportados sob as seguintes configurações:

**Área de trabalho do Windows e os requisitos de transporte do Silverlight**

| Transporte | Aplicativo .NET | Silverlight |
| --- | --- | --- |
| Soquetes da Web | Windows 8 e posteriores e o .NET 4.5 + | N/D |
| Quadro para sempre | N/D | N/D |
| Eventos enviados pelo servidor | .NET 4+ | 5+ |
| Sondagem longa | .NET 4+ | 5+ |

<a id="android"></a>

### <a name="windows-store-and-windows-phone-applications"></a>Windows Store e aplicativos do Windows Phone

SignalR pode ser usado em aplicativos da Windows Store e aplicativos do Windows Phone 8. Os transportes a seguir são suportados sob as seguintes configurações:

**Windows Store e requisitos de transporte do Windows Phone**

| Transporte | Armazenamento do Windows / .NET | Windows Store / JavaScript | Windows Phone / IE | Windows Phone / .NET |
| --- | --- | --- | --- | --- |
| WebSockets | N/D | Win8 + | 8+ | N/D |
| Quadro para sempre | N/D | Win8 + | 7.5+ | N/D |
| Eventos enviados pelo servidor | Win8 + | N/D | N/D | 8+ |
| Sondagem longa | Win8 + | Win8 + | 7.5+ | 8+ |

<a id="updates"></a>

## <a name="recommended-updates"></a>Atualizações recomendadas

As seguintes atualizações são recomendadas para o SignalR servidores:

- Há uma atualização para o .NET Framework 4.5 [aqui](https://support.microsoft.com/kb/2750149).
- A Microsoft lançará periodicamente QFE para ASP.NET. Eles devem ser aplicados como disponíveis.
