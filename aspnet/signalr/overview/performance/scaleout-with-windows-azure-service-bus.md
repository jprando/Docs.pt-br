---
uid: signalr/overview/performance/scaleout-with-windows-azure-service-bus
title: "Expansão do SignalR com o barramento de serviço do Azure | Microsoft Docs"
author: MikeWasson
description: "Versões de software usada nesta versão do Visual Studio 2013 .NET 4.5 SignalR tópico 2 versões anteriores desta versão do tópico para o SignalR 1. x desse tópico,..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 06/10/2014
ms.topic: article
ms.assetid: ce1305f9-30fd-49e3-bf38-d0a78dfb06c3
ms.technology: dotnet-signalr
ms.prod: .net-framework
msc.legacyurl: /signalr/overview/performance/scaleout-with-windows-azure-service-bus
msc.type: authoredcontent
ms.openlocfilehash: 7cb68d578fee8d6ee036f8fb096ba45e0c8ef3d6
ms.sourcegitcommit: 060879fcf3f73d2366b5c811986f8695fff65db8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2018
---
<a name="signalr-scaleout-with-azure-service-bus"></a><span data-ttu-id="7d02f-103">Expansão do SignalR com o barramento de serviço do Azure</span><span class="sxs-lookup"><span data-stu-id="7d02f-103">SignalR Scaleout with Azure Service Bus</span></span>
====================
<span data-ttu-id="7d02f-104">por [Mike Wasson](https://github.com/MikeWasson), [Patrick Fletcher](https://github.com/pfletcher)</span><span class="sxs-lookup"><span data-stu-id="7d02f-104">by [Mike Wasson](https://github.com/MikeWasson), [Patrick Fletcher](https://github.com/pfletcher)</span></span>

<span data-ttu-id="7d02f-105">Neste tutorial, você implantará um aplicativo SignalR para uma função do Windows Azure Web, usando o backplane de barramento de serviço para distribuir mensagens para cada instância de função.</span><span class="sxs-lookup"><span data-stu-id="7d02f-105">In this tutorial, you will deploy a SignalR application to a Windows Azure Web Role, using the Service Bus backplane to distribute messages to each role instance.</span></span> <span data-ttu-id="7d02f-106">(Você também pode usar o backplane de barramento de serviço com [aplicativos no serviço de aplicativo do Azure web](https://docs.microsoft.com/azure/app-service-web/).)</span><span class="sxs-lookup"><span data-stu-id="7d02f-106">(You can also use the Service Bus backplane with [web apps in Azure App Service](https://docs.microsoft.com/azure/app-service-web/).)</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image1.png)

<span data-ttu-id="7d02f-107">Pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="7d02f-107">Prerequisites:</span></span>

- <span data-ttu-id="7d02f-108">Uma conta do Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="7d02f-108">A Windows Azure account.</span></span>
- <span data-ttu-id="7d02f-109">O [Windows Azure SDK](https://go.microsoft.com/fwlink/?linkid=254364&amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="7d02f-109">The [Windows Azure SDK](https://go.microsoft.com/fwlink/?linkid=254364&amp;clcid=0x409).</span></span>
- <span data-ttu-id="7d02f-110">Visual Studio 2012 ou 2013.</span><span class="sxs-lookup"><span data-stu-id="7d02f-110">Visual Studio 2012 or 2013.</span></span>

<span data-ttu-id="7d02f-111">O backplane de barramento de serviço também é compatível com [Service Bus for Windows Server](https://msdn.microsoft.com/library/windowsazure/dn282144.aspx), versão 1.1.</span><span class="sxs-lookup"><span data-stu-id="7d02f-111">The service bus backplane is also compatible with [Service Bus for Windows Server](https://msdn.microsoft.com/library/windowsazure/dn282144.aspx), version 1.1.</span></span> <span data-ttu-id="7d02f-112">No entanto, não é compatível com a versão 1.0 do Service Bus for Windows Server.</span><span class="sxs-lookup"><span data-stu-id="7d02f-112">However, it is not compatible with version 1.0 of Service Bus for Windows Server.</span></span>

## <a name="pricing"></a><span data-ttu-id="7d02f-113">Preços</span><span class="sxs-lookup"><span data-stu-id="7d02f-113">Pricing</span></span>

<span data-ttu-id="7d02f-114">O backplane de barramento de serviço usa tópicos para enviar mensagens.</span><span class="sxs-lookup"><span data-stu-id="7d02f-114">The Service Bus backplane uses topics to send messages.</span></span> <span data-ttu-id="7d02f-115">Para obter as informações mais recentes sobre preços, consulte [barramento de serviço](https://azure.microsoft.com/pricing/details/service-bus/).</span><span class="sxs-lookup"><span data-stu-id="7d02f-115">For the latest pricing information, see [Service Bus](https://azure.microsoft.com/pricing/details/service-bus/).</span></span> <span data-ttu-id="7d02f-116">No momento da redação deste artigo, você pode enviar 1.000.000 mensagens por mês para menor que US $1.</span><span class="sxs-lookup"><span data-stu-id="7d02f-116">At the time of this writing, you can send 1,000,000 messages per month for less than $1.</span></span> <span data-ttu-id="7d02f-117">O backplane envia uma mensagem de barramento de serviço para cada invocação de um método de hub SignalR.</span><span class="sxs-lookup"><span data-stu-id="7d02f-117">The backplane sends a service bus message for each invocation of a SignalR hub method.</span></span> <span data-ttu-id="7d02f-118">Também há algumas mensagens de controle para conexões, desconexões, unindo ou deixar grupos e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="7d02f-118">There are also some control messages for connections, disconnections, joining or leaving groups, and so forth.</span></span> <span data-ttu-id="7d02f-119">Na maioria dos aplicativos, a maioria do tráfego de mensagem será invocações de método do hub.</span><span class="sxs-lookup"><span data-stu-id="7d02f-119">In most applications, the majority of the message traffic will be hub method invocations.</span></span>

## <a name="overview"></a><span data-ttu-id="7d02f-120">Visão geral</span><span class="sxs-lookup"><span data-stu-id="7d02f-120">Overview</span></span>

<span data-ttu-id="7d02f-121">Antes de entrar para o tutorial detalhado, aqui está uma visão geral das tarefas que você executará.</span><span class="sxs-lookup"><span data-stu-id="7d02f-121">Before we get to the detailed tutorial, here is a quick overview of what you will do.</span></span>

1. <span data-ttu-id="7d02f-122">Use o portal do Windows Azure para criar um novo namespace de barramento de serviço.</span><span class="sxs-lookup"><span data-stu-id="7d02f-122">Use the Windows Azure portal to create a new Service Bus namespace.</span></span>
2. <span data-ttu-id="7d02f-123">Adicione esses pacotes do NuGet ao seu aplicativo:</span><span class="sxs-lookup"><span data-stu-id="7d02f-123">Add these NuGet packages to your application:</span></span> 

    - [<span data-ttu-id="7d02f-124">Microsoft.AspNet.SignalR</span><span class="sxs-lookup"><span data-stu-id="7d02f-124">Microsoft.AspNet.SignalR</span></span>](http://nuget.org/packages/Microsoft.AspNet.SignalR)
    - [<span data-ttu-id="7d02f-125">Microsoft.AspNet.SignalR.ServiceBus</span><span class="sxs-lookup"><span data-stu-id="7d02f-125">Microsoft.AspNet.SignalR.ServiceBus</span></span>](http://www.nuget.org/packages/SignalR.WindowsAzureServiceBus)
3. <span data-ttu-id="7d02f-126">Crie um aplicativo do SignalR.</span><span class="sxs-lookup"><span data-stu-id="7d02f-126">Create a SignalR application.</span></span>
4. <span data-ttu-id="7d02f-127">Adicione o seguinte código ao Startup.cs para configurar o backplane:</span><span class="sxs-lookup"><span data-stu-id="7d02f-127">Add the following code to Startup.cs to configure the backplane:</span></span> 

    [!code-csharp[Main](scaleout-with-windows-azure-service-bus/samples/sample1.cs)]

<span data-ttu-id="7d02f-128">Este código configura o backplane com os valores padrão para [TopicCount](https://msdn.microsoft.com/library/microsoft.aspnet.signalr.servicebusscaleoutconfiguration.topiccount(v=vs.118).aspx) e [MaxQueueLength](https://msdn.microsoft.com/library/microsoft.aspnet.signalr.messaging.scaleoutconfiguration.maxqueuelength(v=vs.118).aspx).</span><span class="sxs-lookup"><span data-stu-id="7d02f-128">This code configures the backplane with the default values for [TopicCount](https://msdn.microsoft.com/library/microsoft.aspnet.signalr.servicebusscaleoutconfiguration.topiccount(v=vs.118).aspx) and [MaxQueueLength](https://msdn.microsoft.com/library/microsoft.aspnet.signalr.messaging.scaleoutconfiguration.maxqueuelength(v=vs.118).aspx).</span></span> <span data-ttu-id="7d02f-129">Para obter informações sobre como alterar esses valores, consulte [desempenho SignalR: métricas de expansão](signalr-performance.md#scaleout_metrics).</span><span class="sxs-lookup"><span data-stu-id="7d02f-129">For information on changing these values, see [SignalR Performance: Scaleout Metrics](signalr-performance.md#scaleout_metrics).</span></span>

<span data-ttu-id="7d02f-130">Para cada aplicativo, escolha um valor diferente de "Nomedoseuaplicativo".</span><span class="sxs-lookup"><span data-stu-id="7d02f-130">For each application, pick a different value for "YourAppName".</span></span> <span data-ttu-id="7d02f-131">Não use o mesmo valor em vários aplicativos.</span><span class="sxs-lookup"><span data-stu-id="7d02f-131">Do not use the same value across multiple applications.</span></span>

## <a name="create-the-azure-services"></a><span data-ttu-id="7d02f-132">Criar os serviços do Azure</span><span class="sxs-lookup"><span data-stu-id="7d02f-132">Create the Azure Services</span></span>

<span data-ttu-id="7d02f-133">Criar um serviço de nuvem, conforme descrito em [como criar e implantar um serviço de nuvem](https://docs.microsoft.com/azure/cloud-services/cloud-services-how-to-create-deploy).</span><span class="sxs-lookup"><span data-stu-id="7d02f-133">Create a Cloud Service, as described in [How to Create and Deploy a Cloud Service](https://docs.microsoft.com/azure/cloud-services/cloud-services-how-to-create-deploy).</span></span> <span data-ttu-id="7d02f-134">Siga as etapas na seção "como: criar um serviço de nuvem usando a criação rápida".</span><span class="sxs-lookup"><span data-stu-id="7d02f-134">Follow the steps in the section "How to: Create a cloud service using Quick Create".</span></span> <span data-ttu-id="7d02f-135">Para este tutorial, você não precisa carregar um certificado.</span><span class="sxs-lookup"><span data-stu-id="7d02f-135">For this tutorial, you do not need to upload a certificate.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image2.png)

<span data-ttu-id="7d02f-136">Criar um novo namespace de barramento de serviço, conforme descrito em [como barramento de serviço para usar tópicos/assinaturas](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions).</span><span class="sxs-lookup"><span data-stu-id="7d02f-136">Create a new Service Bus namespace, as described in [How to Use Service Bus Topics/Subscriptions](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions).</span></span> <span data-ttu-id="7d02f-137">Siga as etapas na seção "Criar um Namespace de serviço".</span><span class="sxs-lookup"><span data-stu-id="7d02f-137">Follow the steps in the section "Create a Service Namespace".</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image3.png)

> [!NOTE]
> <span data-ttu-id="7d02f-138">Certifique-se de selecionar a mesma região para o serviço de nuvem e o namespace do barramento de serviço.</span><span class="sxs-lookup"><span data-stu-id="7d02f-138">Make sure to select the same region for the cloud service and the Service Bus namespace.</span></span>


## <a name="create-the-visual-studio-project"></a><span data-ttu-id="7d02f-139">Criar o projeto do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7d02f-139">Create the Visual Studio Project</span></span>

<span data-ttu-id="7d02f-140">Inicie o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7d02f-140">Start Visual Studio.</span></span> <span data-ttu-id="7d02f-141">Do **arquivo** menu, clique em **novo projeto**.</span><span class="sxs-lookup"><span data-stu-id="7d02f-141">From the **File** menu, click **New Project**.</span></span>

<span data-ttu-id="7d02f-142">No **novo projeto** caixa de diálogo caixa, expanda **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="7d02f-142">In the **New Project** dialog box, expand **Visual C#**.</span></span> <span data-ttu-id="7d02f-143">Em **modelos instalados**, selecione **nuvem** e, em seguida, selecione **serviço de nuvem do Windows Azure**.</span><span class="sxs-lookup"><span data-stu-id="7d02f-143">Under **Installed Templates**, select **Cloud** and then select **Windows Azure Cloud Service**.</span></span> <span data-ttu-id="7d02f-144">Mantenha o padrão do .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="7d02f-144">Keep the default .NET Framework 4.5.</span></span> <span data-ttu-id="7d02f-145">Nome do aplicativo ChatService e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="7d02f-145">Name the application ChatService and click **OK**.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image4.png)

<span data-ttu-id="7d02f-146">No **novo serviço de nuvem do Windows Azure** caixa de diálogo, selecione função Web do ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="7d02f-146">In the **New Windows Azure Cloud Service** dialog, select ASP.NET Web Role.</span></span> <span data-ttu-id="7d02f-147">Clique no botão de seta para a direita (**&gt;**) para adicionar a função à sua solução.</span><span class="sxs-lookup"><span data-stu-id="7d02f-147">Click the right-arrow button (**&gt;**) to add the role to your solution.</span></span>

<span data-ttu-id="7d02f-148">Passe o mouse sobre a nova função, então o ícone de lápis visível.</span><span class="sxs-lookup"><span data-stu-id="7d02f-148">Hover the mouse over the new role, so the pencil icon visible.</span></span> <span data-ttu-id="7d02f-149">Clique nesse ícone para renomear a função.</span><span class="sxs-lookup"><span data-stu-id="7d02f-149">Click this icon to rename the role.</span></span> <span data-ttu-id="7d02f-150">Nome de função "SignalRChat" e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="7d02f-150">Name the role "SignalRChat" and click **OK**.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image5.png)

<span data-ttu-id="7d02f-151">No **novo projeto ASP.NET** caixa de diálogo, selecione **MVC**e clique em Okey.</span><span class="sxs-lookup"><span data-stu-id="7d02f-151">In the **New ASP.NET Project** dialog, select **MVC**, and click OK.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image6.png)

<span data-ttu-id="7d02f-152">O Assistente de projeto cria dois projetos:</span><span class="sxs-lookup"><span data-stu-id="7d02f-152">The project wizard creates two projects:</span></span>

- <span data-ttu-id="7d02f-153">ChatService: Este projeto é o aplicativo do Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="7d02f-153">ChatService: This project is the Windows Azure application.</span></span> <span data-ttu-id="7d02f-154">Ele define as funções do Azure e outras opções de configuração.</span><span class="sxs-lookup"><span data-stu-id="7d02f-154">It defines the Azure roles and other configuration options.</span></span>
- <span data-ttu-id="7d02f-155">SignalRChat: Este projeto é seu projeto ASP.NET MVC 5.</span><span class="sxs-lookup"><span data-stu-id="7d02f-155">SignalRChat: This project is your ASP.NET MVC 5 project.</span></span>

## <a name="create-the-signalr-chat-application"></a><span data-ttu-id="7d02f-156">Criar o aplicativo de Chat de SignalR</span><span class="sxs-lookup"><span data-stu-id="7d02f-156">Create the SignalR Chat Application</span></span>

<span data-ttu-id="7d02f-157">Para criar o aplicativo de chat, siga as etapas no tutorial [Introdução ao SignalR e MVC 5](../getting-started/tutorial-getting-started-with-signalr-and-mvc.md).</span><span class="sxs-lookup"><span data-stu-id="7d02f-157">To create the chat application, follow the steps in the tutorial [Getting Started with SignalR and MVC 5](../getting-started/tutorial-getting-started-with-signalr-and-mvc.md).</span></span>

<span data-ttu-id="7d02f-158">Use NuGet para instalar as bibliotecas necessárias.</span><span class="sxs-lookup"><span data-stu-id="7d02f-158">Use NuGet to install the required libraries.</span></span> <span data-ttu-id="7d02f-159">Do **ferramentas** menu, selecione **Gerenciador de biblioteca de pacote**, em seguida, selecione **Package Manager Console**.</span><span class="sxs-lookup"><span data-stu-id="7d02f-159">From the **Tools** menu, select **Library Package Manager**, then select **Package Manager Console**.</span></span> <span data-ttu-id="7d02f-160">No **Package Manager Console** janela, digite os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="7d02f-160">In the **Package Manager Console** window, enter the following commands:</span></span>

[!code-powershell[Main](scaleout-with-windows-azure-service-bus/samples/sample2.ps1)]

<span data-ttu-id="7d02f-161">Use o `-ProjectName` opção para instalar os pacotes para o projeto ASP.NET MVC, em vez de projeto do Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="7d02f-161">Use the `-ProjectName` option to install the packages to the ASP.NET MVC project, rather than the Windows Azure project.</span></span>

## <a name="configure-the-backplane"></a><span data-ttu-id="7d02f-162">Configurar o Backplane</span><span class="sxs-lookup"><span data-stu-id="7d02f-162">Configure the Backplane</span></span>

<span data-ttu-id="7d02f-163">No arquivo de Startup.cs do seu aplicativo, adicione o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="7d02f-163">In your application's Startup.cs file, add the following code:</span></span>

[!code-csharp[Main](scaleout-with-windows-azure-service-bus/samples/sample3.cs)]

<span data-ttu-id="7d02f-164">Agora você precisa obter sua cadeia de conexão do barramento de serviço.</span><span class="sxs-lookup"><span data-stu-id="7d02f-164">Now you need to get your service bus connection string.</span></span> <span data-ttu-id="7d02f-165">No portal do Azure, selecione o namespace de barramento de serviço que você criou e clique no ícone de chave de acesso.</span><span class="sxs-lookup"><span data-stu-id="7d02f-165">In the Azure portal, select the service bus namespace that you created and click the Access Key icon.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image7.png)

<span data-ttu-id="7d02f-166">Copie a cadeia de conexão para a área de transferência e, em seguida, cole-o no *connectionString* variável.</span><span class="sxs-lookup"><span data-stu-id="7d02f-166">Copy the connection string to the clipboard, then paste it into the *connectionString* variable.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image8.png)

[!code-csharp[Main](scaleout-with-windows-azure-service-bus/samples/sample4.cs)]

## <a name="deploy-to-azure"></a><span data-ttu-id="7d02f-167">Implantar no Azure</span><span class="sxs-lookup"><span data-stu-id="7d02f-167">Deploy to Azure</span></span>

<span data-ttu-id="7d02f-168">No Gerenciador de soluções, expanda o **funções** pasta dentro do projeto ChatService.</span><span class="sxs-lookup"><span data-stu-id="7d02f-168">In Solution Explorer, expand the **Roles** folder inside the ChatService project.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image9.png)

<span data-ttu-id="7d02f-169">A função SignalRChat e selecione **propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7d02f-169">Right-click the SignalRChat role and select **Properties**.</span></span> <span data-ttu-id="7d02f-170">Selecione o **configuração** guia. Em **instâncias** selecione 2.</span><span class="sxs-lookup"><span data-stu-id="7d02f-170">Select the **Configuration** tab. Under **Instances** select 2.</span></span> <span data-ttu-id="7d02f-171">Você também pode definir o tamanho da VM **Extrapequeno**.</span><span class="sxs-lookup"><span data-stu-id="7d02f-171">You can also set the VM size to **Extra Small**.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image10.png)

<span data-ttu-id="7d02f-172">Salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="7d02f-172">Save the changes.</span></span>

<span data-ttu-id="7d02f-173">No Gerenciador de soluções, clique com botão direito no projeto ChatService.</span><span class="sxs-lookup"><span data-stu-id="7d02f-173">In Solution Explorer, right-click the ChatService project.</span></span> <span data-ttu-id="7d02f-174">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="7d02f-174">Select **Publish**.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image11.png)

<span data-ttu-id="7d02f-175">Se esta for sua primeira publicação de tempo para o Windows Azure, você deve baixar suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="7d02f-175">If this is your first time publishing to Windows Azure, you must download your credentials.</span></span> <span data-ttu-id="7d02f-176">No **publicar** assistente, clique em "Entrar para baixar credenciais".</span><span class="sxs-lookup"><span data-stu-id="7d02f-176">In the **Publish** wizard, click "Sign in to download credentials".</span></span> <span data-ttu-id="7d02f-177">Isso solicitará que você entrar no portal do Windows Azure e baixar um arquivo de configurações de publicação.</span><span class="sxs-lookup"><span data-stu-id="7d02f-177">This will prompt you to sign into the Windows Azure portal and download a publish settings file.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image12.png)

<span data-ttu-id="7d02f-178">Clique em **importação** e selecione o arquivo de configurações de publicação que você baixou.</span><span class="sxs-lookup"><span data-stu-id="7d02f-178">Click **Import** and select the publish settings file that you downloaded.</span></span>

<span data-ttu-id="7d02f-179">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7d02f-179">Click **Next**.</span></span> <span data-ttu-id="7d02f-180">No **configurações de publicação** caixa de diálogo, em **serviço de nuvem**, selecione o serviço de nuvem que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7d02f-180">In the **Publish Settings** dialog, under **Cloud Service**, select the cloud service that you created earlier.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image13.png)

<span data-ttu-id="7d02f-181">Clique em **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="7d02f-181">Click **Publish**.</span></span> <span data-ttu-id="7d02f-182">Pode levar alguns minutos para implantar o aplicativo e iniciar as máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="7d02f-182">It can take a few minutes to deploy the application and start the VMs.</span></span>

<span data-ttu-id="7d02f-183">Agora quando você executa o aplicativo, as instâncias de função se comunicar por meio do barramento de serviço do Azure, usando um tópico do barramento de serviço.</span><span class="sxs-lookup"><span data-stu-id="7d02f-183">Now when you run the chat application, the role instances communicate through Azure Service Bus, using a Service Bus topic.</span></span> <span data-ttu-id="7d02f-184">Um tópico é uma fila de mensagens que permite que vários assinantes.</span><span class="sxs-lookup"><span data-stu-id="7d02f-184">A topic is a message queue that allows multiple subscribers.</span></span>

<span data-ttu-id="7d02f-185">O backplane cria automaticamente o tópico e as assinaturas.</span><span class="sxs-lookup"><span data-stu-id="7d02f-185">The backplane automatically creates the topic and the subscriptions.</span></span> <span data-ttu-id="7d02f-186">Para ver as assinaturas e a atividade de mensagens, abra o portal do Azure, selecione o namespace de barramento de serviço e clique em "Tópicos de".</span><span class="sxs-lookup"><span data-stu-id="7d02f-186">To see the subscriptions and message activity, open the Azure portal, select the Service Bus namespace, and click on "Topics".</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image14.png)

<span data-ttu-id="7d02f-187">Ele poderá levar alguns minutos para que a atividade de mensagem exibida no painel.</span><span class="sxs-lookup"><span data-stu-id="7d02f-187">It make take a few minutes for the message activity to show up in the dashboard.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image15.png)

<span data-ttu-id="7d02f-188">SignalR gerencia o tempo de vida do tópico.</span><span class="sxs-lookup"><span data-stu-id="7d02f-188">SignalR manages the topic lifetime.</span></span> <span data-ttu-id="7d02f-189">Como o aplicativo é implantado, não tente excluir tópicos manualmente ou alterar as configurações no tópico.</span><span class="sxs-lookup"><span data-stu-id="7d02f-189">As long as your application is deployed, don't try to manually delete topics or change settings on the topic.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7d02f-190">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="7d02f-190">Troubleshooting</span></span>

<span data-ttu-id="7d02f-191">**System. InvalidOperationException "O somente IsolationLevel com suporte é 'IsolationLevel.Serializable'".**</span><span class="sxs-lookup"><span data-stu-id="7d02f-191">**System.InvalidOperationException "The only supported IsolationLevel is 'IsolationLevel.Serializable'."**</span></span>

<span data-ttu-id="7d02f-192">Esse erro pode ocorrer se o nível de transação para uma operação é definido como algo diferente de `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="7d02f-192">This error can occur if the transaction level for an operation is set to something other than `Serializable`.</span></span> <span data-ttu-id="7d02f-193">Verifique se que nenhuma operação está sendo executada com outros níveis de transação.</span><span class="sxs-lookup"><span data-stu-id="7d02f-193">Verify that no operations are being performed with other transaction levels.</span></span>