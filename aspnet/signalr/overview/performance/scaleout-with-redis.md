---
uid: signalr/overview/performance/scaleout-with-redis
title: "Expansão do SignalR com Redis | Microsoft Docs"
author: MikeWasson
description: "Versões de software usados neste tópico Visual Studio 2013 .NET 4.5 SignalR versões anteriores de versão 2 deste tópico para obter informações sobre versões anteriores do..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 06/10/2014
ms.topic: article
ms.assetid: 6ecd08c1-e364-4cd7-ad4c-806521911585
ms.technology: dotnet-signalr
ms.prod: .net-framework
msc.legacyurl: /signalr/overview/performance/scaleout-with-redis
msc.type: authoredcontent
ms.openlocfilehash: 965c32a4e2f2c9c4bd457d0c13ae99c1378c22c9
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2017
---
<a name="signalr-scaleout-with-redis"></a><span data-ttu-id="df7f7-103">Expansão do SignalR com Redis</span><span class="sxs-lookup"><span data-stu-id="df7f7-103">SignalR Scaleout with Redis</span></span>
====================
<span data-ttu-id="df7f7-104">por [Mike Wasson](https://github.com/MikeWasson), [Patrick Fletcher](https://github.com/pfletcher)</span><span class="sxs-lookup"><span data-stu-id="df7f7-104">by [Mike Wasson](https://github.com/MikeWasson), [Patrick Fletcher](https://github.com/pfletcher)</span></span>

> ## <a name="software-versions-used-in-this-topic"></a><span data-ttu-id="df7f7-105">Versões de software usadas neste tópico</span><span class="sxs-lookup"><span data-stu-id="df7f7-105">Software versions used in this topic</span></span>
> 
> 
> - [<span data-ttu-id="df7f7-106">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="df7f7-106">Visual Studio 2013</span></span>](https://www.microsoft.com/visualstudio/eng/2013-downloads)
> - <span data-ttu-id="df7f7-107">.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="df7f7-107">.NET 4.5</span></span>
> - <span data-ttu-id="df7f7-108">SignalR versão 2</span><span class="sxs-lookup"><span data-stu-id="df7f7-108">SignalR version 2</span></span>
>   
> 
> 
> ## <a name="previous-versions-of-this-topic"></a><span data-ttu-id="df7f7-109">Versões anteriores deste tópico</span><span class="sxs-lookup"><span data-stu-id="df7f7-109">Previous versions of this topic</span></span>
> 
> <span data-ttu-id="df7f7-110">Para obter informações sobre versões anteriores do SignalR, consulte [versões mais antigas do SignalR](../older-versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="df7f7-110">For information about earlier versions of SignalR, see [SignalR Older Versions](../older-versions/index.md).</span></span>
> 
> ## <a name="questions-and-comments"></a><span data-ttu-id="df7f7-111">Perguntas e comentários</span><span class="sxs-lookup"><span data-stu-id="df7f7-111">Questions and comments</span></span>
> 
> <span data-ttu-id="df7f7-112">Deixe comentários em como você gostou neste tutorial e o que podemos melhorar nos comentários na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="df7f7-112">Please leave feedback on how you liked this tutorial and what we could improve in the comments at the bottom of the page.</span></span> <span data-ttu-id="df7f7-113">Se você tiver dúvidas que não estão diretamente relacionadas ao tutorial, você poderá postá-los para o [ASP.NET SignalR fórum](https://forums.asp.net/1254.aspx/1?ASP+NET+SignalR) ou [StackOverflow.com](http://stackoverflow.com/).</span><span class="sxs-lookup"><span data-stu-id="df7f7-113">If you have questions that are not directly related to the tutorial, you can post them to the [ASP.NET SignalR forum](https://forums.asp.net/1254.aspx/1?ASP+NET+SignalR) or [StackOverflow.com](http://stackoverflow.com/).</span></span>


<span data-ttu-id="df7f7-114">Neste tutorial, você usará [Redis](http://redis.io/) para distribuir mensagens através de um aplicativo de SignalR é implantado em duas instâncias separadas do IIS.</span><span class="sxs-lookup"><span data-stu-id="df7f7-114">In this tutorial, you will use [Redis](http://redis.io/) to distribute messages across a SignalR application that is deployed on two separate IIS instances.</span></span>

<span data-ttu-id="df7f7-115">Redis é um repositório de chave-valor na memória.</span><span class="sxs-lookup"><span data-stu-id="df7f7-115">Redis is an in-memory key-value store.</span></span> <span data-ttu-id="df7f7-116">Ele também dá suporte a um sistema de mensagens com um modelo de publicação/assinatura.</span><span class="sxs-lookup"><span data-stu-id="df7f7-116">It also supports a messaging system with a publish/subscribe model.</span></span> <span data-ttu-id="df7f7-117">O backplane SignalR Redis usa o recurso de publicação/assinatura para encaminhar mensagens para outros servidores.</span><span class="sxs-lookup"><span data-stu-id="df7f7-117">The SignalR Redis backplane uses the pub/sub feature to forward messages to other servers.</span></span>

![](scaleout-with-redis/_static/image1.png)

<span data-ttu-id="df7f7-118">Para este tutorial, você usará os três servidores:</span><span class="sxs-lookup"><span data-stu-id="df7f7-118">For this tutorial, you will use three servers:</span></span>

- <span data-ttu-id="df7f7-119">Dois servidores que executam o Windows, que você usará para implantar um aplicativo do SignalR.</span><span class="sxs-lookup"><span data-stu-id="df7f7-119">Two servers running Windows, which you will use to deploy a SignalR application.</span></span>
- <span data-ttu-id="df7f7-120">Um servidor executando o Linux, o que você usará para executar o Redis.</span><span class="sxs-lookup"><span data-stu-id="df7f7-120">One server running Linux, which you will use to run Redis.</span></span> <span data-ttu-id="df7f7-121">Para as capturas de tela neste tutorial, usei Ubuntu 12.04 TLS.</span><span class="sxs-lookup"><span data-stu-id="df7f7-121">For the screenshots in this tutorial, I used Ubuntu 12.04 TLS.</span></span>

<span data-ttu-id="df7f7-122">Se você não tem três servidores físicos para usar, você pode criar VMs no Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="df7f7-122">If you don't have three physical servers to use, you can create VMs on Hyper-V.</span></span> <span data-ttu-id="df7f7-123">Outra opção é criar VMs no Azure.</span><span class="sxs-lookup"><span data-stu-id="df7f7-123">Another option is to create VMs on Azure.</span></span>

<span data-ttu-id="df7f7-124">Embora este tutorial usa a implementação de Redis oficial, há também uma [Windows porta do Redis](https://github.com/MSOpenTech/redis) de MSOpenTech.</span><span class="sxs-lookup"><span data-stu-id="df7f7-124">Although this tutorial uses the official Redis implementation, there is also a [Windows port of Redis](https://github.com/MSOpenTech/redis) from MSOpenTech.</span></span> <span data-ttu-id="df7f7-125">Instalação e configuração são diferentes, mas, caso contrário, as etapas são as mesmas.</span><span class="sxs-lookup"><span data-stu-id="df7f7-125">Setup and configuration are different, but otherwise the steps are the same.</span></span>

> [!NOTE] 
> 
> <span data-ttu-id="df7f7-126">Expansão do SignalR com Redis não oferece suporte a clusters do Redis.</span><span class="sxs-lookup"><span data-stu-id="df7f7-126">SignalR scaleout with Redis does not support Redis clusters.</span></span>


## <a name="overview"></a><span data-ttu-id="df7f7-127">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="df7f7-127">Overview</span></span>

<span data-ttu-id="df7f7-128">Antes de entrar para o tutorial detalhado, aqui está uma visão geral das tarefas que você executará.</span><span class="sxs-lookup"><span data-stu-id="df7f7-128">Before we get to the detailed tutorial, here is a quick overview of what you will do.</span></span>

1. <span data-ttu-id="df7f7-129">Instale o Redis e iniciar o servidor do Redis.</span><span class="sxs-lookup"><span data-stu-id="df7f7-129">Install Redis and start the Redis server.</span></span>
2. <span data-ttu-id="df7f7-130">Adicione esses pacotes do NuGet ao seu aplicativo:</span><span class="sxs-lookup"><span data-stu-id="df7f7-130">Add these NuGet packages to your application:</span></span> 

    - [<span data-ttu-id="df7f7-131">SignalR</span><span class="sxs-lookup"><span data-stu-id="df7f7-131">Microsoft.AspNet.SignalR</span></span>](http://nuget.org/packages/Microsoft.AspNet.SignalR)
    - [<span data-ttu-id="df7f7-132">Microsoft.AspNet.SignalR.Redis</span><span class="sxs-lookup"><span data-stu-id="df7f7-132">Microsoft.AspNet.SignalR.Redis</span></span>](http://nuget.org/packages/Microsoft.AspNet.SignalR.Redis)
3. <span data-ttu-id="df7f7-133">Crie um aplicativo do SignalR.</span><span class="sxs-lookup"><span data-stu-id="df7f7-133">Create a SignalR application.</span></span>
4. <span data-ttu-id="df7f7-134">Adicione o seguinte código ao Startup.cs para configurar o backplane:</span><span class="sxs-lookup"><span data-stu-id="df7f7-134">Add the following code to Startup.cs to configure the backplane:</span></span> 

    [!code-csharp[Main](scaleout-with-redis/samples/sample1.cs)]

## <a name="ubuntu-on-hyper-v"></a><span data-ttu-id="df7f7-135">Ubuntu no Hyper-V</span><span class="sxs-lookup"><span data-stu-id="df7f7-135">Ubuntu on Hyper-V</span></span>

<span data-ttu-id="df7f7-136">Usando o Windows Hyper-V, você pode criar facilmente uma VM Ubuntu no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="df7f7-136">Using Windows Hyper-V, you can easily create an Ubuntu VM on Windows Server.</span></span>

<span data-ttu-id="df7f7-137">Baixe o ISO Ubuntu da [http://www.ubuntu.com](http://www.ubuntu.com/).</span><span class="sxs-lookup"><span data-stu-id="df7f7-137">Download the Ubuntu ISO from [http://www.ubuntu.com](http://www.ubuntu.com/).</span></span>

<span data-ttu-id="df7f7-138">No Hyper-V, adicione uma nova VM.</span><span class="sxs-lookup"><span data-stu-id="df7f7-138">In Hyper-V, add a new VM.</span></span> <span data-ttu-id="df7f7-139">No **conectar disco rígido Virtual** etapa, selecione **criar um disco rígido virtual**.</span><span class="sxs-lookup"><span data-stu-id="df7f7-139">In the **Connect Virtual Hard Disk** step, select **Create a virtual hard disk**.</span></span>

![](scaleout-with-redis/_static/image2.png)

<span data-ttu-id="df7f7-140">No **opções de instalação** etapa, selecione **o arquivo de imagem (. ISO)**, clique em **procurar**e navegue para a instalação do Ubuntu ISO.</span><span class="sxs-lookup"><span data-stu-id="df7f7-140">In the **Installation Options** step, select **Image file (.iso)**, click **Browse**, and browse to the Ubuntu installation ISO.</span></span>

![](scaleout-with-redis/_static/image3.png)

## <a name="install-redis"></a><span data-ttu-id="df7f7-141">Instalar o Redis</span><span class="sxs-lookup"><span data-stu-id="df7f7-141">Install Redis</span></span>

<span data-ttu-id="df7f7-142">Siga as etapas em [http://redis.io/download](http://redis.io/download) para baixar e criar Redis.</span><span class="sxs-lookup"><span data-stu-id="df7f7-142">Follow the steps at [http://redis.io/download](http://redis.io/download) to download and build Redis.</span></span>

[!code-console[Main](scaleout-with-redis/samples/sample2.cmd)]

<span data-ttu-id="df7f7-143">Isso cria os binários do Redis a `src` directory.</span><span class="sxs-lookup"><span data-stu-id="df7f7-143">This builds the Redis binaries in the `src` directory.</span></span>

<span data-ttu-id="df7f7-144">Por padrão, o Redis não requer uma senha.</span><span class="sxs-lookup"><span data-stu-id="df7f7-144">By default, Redis does not require a password.</span></span> <span data-ttu-id="df7f7-145">Para definir uma senha, edite o `redis.conf` arquivo, que está localizado no diretório raiz do código-fonte.</span><span class="sxs-lookup"><span data-stu-id="df7f7-145">To set a password, edit the `redis.conf` file, which is located in the root directory of the source code.</span></span> <span data-ttu-id="df7f7-146">(Fazer uma cópia de backup do arquivo antes de editá-lo!) Adicione a seguinte diretiva para `redis.conf`:</span><span class="sxs-lookup"><span data-stu-id="df7f7-146">(Make a backup copy of the file before you edit it!) Add the following directive to `redis.conf`:</span></span>

[!code-powershell[Main](scaleout-with-redis/samples/sample3.ps1)]

<span data-ttu-id="df7f7-147">Agora, inicie o servidor do Redis:</span><span class="sxs-lookup"><span data-stu-id="df7f7-147">Now start the Redis server:</span></span>

[!code-css[Main](scaleout-with-redis/samples/sample4.css)]

![](scaleout-with-redis/_static/image4.png)

<span data-ttu-id="df7f7-148">Abra a porta 6379, que é a porta padrão que Redis escuta.</span><span class="sxs-lookup"><span data-stu-id="df7f7-148">Open port 6379, which is the default port that Redis listens on.</span></span> <span data-ttu-id="df7f7-149">(Você pode alterar o número da porta no arquivo de configuração).</span><span class="sxs-lookup"><span data-stu-id="df7f7-149">(You can change the port number in the configuration file.)</span></span>

## <a name="create-the-signalr-application"></a><span data-ttu-id="df7f7-150">Criar o aplicativo de SignalR</span><span class="sxs-lookup"><span data-stu-id="df7f7-150">Create the SignalR Application</span></span>

<span data-ttu-id="df7f7-151">Crie um aplicativo de SignalR seguindo um destes tutoriais:</span><span class="sxs-lookup"><span data-stu-id="df7f7-151">Create a SignalR application by following either of these tutorials:</span></span>

- [<span data-ttu-id="df7f7-152">Guia de Introdução ao SignalR 2.0</span><span class="sxs-lookup"><span data-stu-id="df7f7-152">Getting Started with SignalR 2.0</span></span>](../getting-started/tutorial-getting-started-with-signalr.md)
- [<span data-ttu-id="df7f7-153">Introdução ao SignalR 2.0 e MVC 5</span><span class="sxs-lookup"><span data-stu-id="df7f7-153">Getting Started with SignalR 2.0 and MVC 5</span></span>](../getting-started/tutorial-getting-started-with-signalr-and-mvc.md)

<span data-ttu-id="df7f7-154">Em seguida, modificaremos o aplicativo de chat para dar suporte a expansão com Redis.</span><span class="sxs-lookup"><span data-stu-id="df7f7-154">Next, we'll modify the chat application to support scaleout with Redis.</span></span> <span data-ttu-id="df7f7-155">Primeiro, adicione o pacote SignalR.Redis NuGet ao seu projeto.</span><span class="sxs-lookup"><span data-stu-id="df7f7-155">First, add the SignalR.Redis NuGet package to your project.</span></span> <span data-ttu-id="df7f7-156">No Visual Studio, do **ferramentas** menu, selecione **Gerenciador de biblioteca de pacote**, em seguida, selecione **Package Manager Console**.</span><span class="sxs-lookup"><span data-stu-id="df7f7-156">In Visual Studio, from the **Tools** menu, select **Library Package Manager**, then select **Package Manager Console**.</span></span> <span data-ttu-id="df7f7-157">Na janela do Console do Gerenciador de pacotes, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="df7f7-157">In the Package Manager Console window, enter the following command:</span></span>

[!code-powershell[Main](scaleout-with-redis/samples/sample5.ps1)]

<span data-ttu-id="df7f7-158">Em seguida, abra o arquivo Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="df7f7-158">Next, open the Startup.cs file.</span></span> <span data-ttu-id="df7f7-159">Adicione o seguinte código para o **configuração** método:</span><span class="sxs-lookup"><span data-stu-id="df7f7-159">Add the following code to the **Configuration** method:</span></span>

[!code-csharp[Main](scaleout-with-redis/samples/sample6.cs)]

- <span data-ttu-id="df7f7-160">"servidor" é o nome do servidor que está executando o Redis.</span><span class="sxs-lookup"><span data-stu-id="df7f7-160">"server" is the name of the server that is running Redis.</span></span>
- <span data-ttu-id="df7f7-161">*porta* é o número da porta</span><span class="sxs-lookup"><span data-stu-id="df7f7-161">*port* is the port number</span></span>
- <span data-ttu-id="df7f7-162">"password" é a senha que você definiu no arquivo conf.</span><span class="sxs-lookup"><span data-stu-id="df7f7-162">"password" is the password that you defined in the redis.conf file.</span></span>
- <span data-ttu-id="df7f7-163">"AppName" é qualquer cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="df7f7-163">"AppName" is any string.</span></span> <span data-ttu-id="df7f7-164">SignalR cria um canal de pub/sub Redis com esse nome.</span><span class="sxs-lookup"><span data-stu-id="df7f7-164">SignalR creates a Redis pub/sub channel with this name.</span></span>

<span data-ttu-id="df7f7-165">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="df7f7-165">For example:</span></span>

[!code-csharp[Main](scaleout-with-redis/samples/sample7.cs)]

## <a name="deploy-and-run-the-application"></a><span data-ttu-id="df7f7-166">Implantar e executar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="df7f7-166">Deploy and Run the Application</span></span>

<span data-ttu-id="df7f7-167">Prepare suas instâncias de servidor do Windows para implantar o aplicativo do SignalR.</span><span class="sxs-lookup"><span data-stu-id="df7f7-167">Prepare your Windows Server instances to deploy the SignalR application.</span></span>

<span data-ttu-id="df7f7-168">Adicione a função do IIS.</span><span class="sxs-lookup"><span data-stu-id="df7f7-168">Add the IIS role.</span></span> <span data-ttu-id="df7f7-169">Inclua recursos de "Desenvolvimento de aplicativos", incluindo o protocolo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="df7f7-169">Include "Application Development" features, including the WebSocket Protocol.</span></span>

![](scaleout-with-redis/_static/image5.png)

<span data-ttu-id="df7f7-170">Também inclui o serviço de gerenciamento (listadas em "Ferramentas de gerenciamento").</span><span class="sxs-lookup"><span data-stu-id="df7f7-170">Also include the Management Service (listed under "Management Tools").</span></span>

![](scaleout-with-redis/_static/image6.png)

<span data-ttu-id="df7f7-171">**Instalar Web implantação 3.0.**</span><span class="sxs-lookup"><span data-stu-id="df7f7-171">**Install Web Deploy 3.0.**</span></span> <span data-ttu-id="df7f7-172">Quando você executar o Gerenciador do IIS, ele solicitará que você instale o Microsoft Web Platform, ou você pode [baixar o intstaller](https://go.microsoft.com/fwlink/?LinkId=255386).</span><span class="sxs-lookup"><span data-stu-id="df7f7-172">When you run IIS Manager, it will prompt you to install Microsoft Web Platform, or you can [download the intstaller](https://go.microsoft.com/fwlink/?LinkId=255386).</span></span> <span data-ttu-id="df7f7-173">No instalador de plataforma, pesquisar para implantação da Web e instalar o Web Deploy 3.0</span><span class="sxs-lookup"><span data-stu-id="df7f7-173">In the Platform Installer, search for Web Deploy and install Web Deploy 3.0</span></span>

![](scaleout-with-redis/_static/image7.png)

<span data-ttu-id="df7f7-174">Verifique se o serviço de gerenciamento da Web está em execução.</span><span class="sxs-lookup"><span data-stu-id="df7f7-174">Check that the Web Management Service is running.</span></span> <span data-ttu-id="df7f7-175">Caso contrário, inicie o serviço.</span><span class="sxs-lookup"><span data-stu-id="df7f7-175">If not, start the service.</span></span> <span data-ttu-id="df7f7-176">(Se você não vir o serviço de gerenciamento da Web na lista de serviços do Windows, certifique-se de que você instalou o serviço de gerenciamento quando você adicionou a função do IIS.)</span><span class="sxs-lookup"><span data-stu-id="df7f7-176">(If you don't see Web Management Service in the list of Windows services, make sure that you installed the Management Service when you added the IIS role.)</span></span>

<span data-ttu-id="df7f7-177">Por padrão, o serviço de gerenciamento da Web escuta na porta TCP 8172.</span><span class="sxs-lookup"><span data-stu-id="df7f7-177">By default, the Web Management Service listens on TCP port 8172.</span></span> <span data-ttu-id="df7f7-178">No Firewall do Windows, crie uma nova regra de entrada para permitir o tráfego TCP na porta 8172.</span><span class="sxs-lookup"><span data-stu-id="df7f7-178">In Windows Firewall, create a new inbound rule to allow TCP traffic on port 8172.</span></span> <span data-ttu-id="df7f7-179">Para obter mais informações, consulte [Configurando regras de Firewall](https://technet.microsoft.com/en-us/library/dd448559(WS.10).aspx).</span><span class="sxs-lookup"><span data-stu-id="df7f7-179">For more information, see [Configuring Firewall Rules](https://technet.microsoft.com/en-us/library/dd448559(WS.10).aspx).</span></span> <span data-ttu-id="df7f7-180">(Se você estiver hospedando as VMs no Azure, você pode fazer isso diretamente no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="df7f7-180">(If you are hosting the VMs on Azure, you can do this directly in the Azure portal.</span></span> <span data-ttu-id="df7f7-181">Consulte [como configurar pontos de extremidade para uma máquina Virtual](https://azure.microsoft.com/en-us/documentation/articles/virtual-machines-set-up-endpoints/).)</span><span class="sxs-lookup"><span data-stu-id="df7f7-181">See [How to Set Up Endpoints to a Virtual Machine](https://azure.microsoft.com/en-us/documentation/articles/virtual-machines-set-up-endpoints/).)</span></span>

<span data-ttu-id="df7f7-182">Agora você está pronto para implantar o projeto do Visual Studio em seu computador de desenvolvimento para o servidor.</span><span class="sxs-lookup"><span data-stu-id="df7f7-182">Now you are ready to deploy the Visual Studio project from your development machine to the server.</span></span> <span data-ttu-id="df7f7-183">No Gerenciador de soluções, clique com botão direito a solução e clique em **publicar**.</span><span class="sxs-lookup"><span data-stu-id="df7f7-183">In Solution Explorer, right-click the solution and click **Publish**.</span></span>

<span data-ttu-id="df7f7-184">Para obter mais documentação sobre a implantação da web, consulte [mapa de conteúdo de implantação da Web do Visual Studio e ASP.NET](../../../whitepapers/aspnet-web-deployment-content-map.md).</span><span class="sxs-lookup"><span data-stu-id="df7f7-184">For more detailed documentation about web deployment, see [Web Deployment Content Map for Visual Studio and ASP.NET](../../../whitepapers/aspnet-web-deployment-content-map.md).</span></span>

<span data-ttu-id="df7f7-185">Se você implantar o aplicativo em dois servidores, você pode abrir cada instância em uma janela separada do navegador e ver a que cada um receba mensagens do SignalR da outra.</span><span class="sxs-lookup"><span data-stu-id="df7f7-185">If you deploy the application to two servers, you can open each instance in a separate browser window and see that they each receive SignalR messages from the other.</span></span> <span data-ttu-id="df7f7-186">(É claro que, em um ambiente de produção, os dois servidores estaria atrás de um balanceador de carga.)</span><span class="sxs-lookup"><span data-stu-id="df7f7-186">(Of course, in a production environment, the two servers would sit behind a load balancer.)</span></span>

![](scaleout-with-redis/_static/image8.png)

<span data-ttu-id="df7f7-187">Se você estiver curioso para ver as mensagens que são enviadas para Redis, você pode usar o **redis-cli** cliente, que é instalado com o Redis.</span><span class="sxs-lookup"><span data-stu-id="df7f7-187">If you're curious to see the messages that are sent to Redis, you can use the **redis-cli** client, which installs with Redis.</span></span>

[!code-xml[Main](scaleout-with-redis/samples/sample8.xml)]

![](scaleout-with-redis/_static/image9.png)