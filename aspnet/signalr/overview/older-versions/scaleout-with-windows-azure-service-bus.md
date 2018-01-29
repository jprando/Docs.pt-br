---
uid: signalr/overview/older-versions/scaleout-with-windows-azure-service-bus
title: "Expansão do SignalR com o barramento de serviço do Azure (SignalR 1. x) | Microsoft Docs"
author: MikeWasson
description: 
ms.author: aspnetcontent
manager: wpickett
ms.date: 05/01/2013
ms.topic: article
ms.assetid: 501db899-e68c-49ff-81b2-1dc561bfe908
ms.technology: dotnet-signalr
ms.prod: .net-framework
msc.legacyurl: /signalr/overview/older-versions/scaleout-with-windows-azure-service-bus
msc.type: authoredcontent
ms.openlocfilehash: b48a7b04701b69f68a492c0f7e08da4a37a92a48
ms.sourcegitcommit: 060879fcf3f73d2366b5c811986f8695fff65db8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2018
---
<a name="signalr-scaleout-with-azure-service-bus-signalr-1x"></a><span data-ttu-id="793f2-102">Expansão do SignalR com o barramento de serviço do Azure (SignalR 1. x)</span><span class="sxs-lookup"><span data-stu-id="793f2-102">SignalR Scaleout with Azure Service Bus (SignalR 1.x)</span></span>
====================
<span data-ttu-id="793f2-103">por [Mike Wasson](https://github.com/MikeWasson), [Patrick Fletcher](https://github.com/pfletcher)</span><span class="sxs-lookup"><span data-stu-id="793f2-103">by [Mike Wasson](https://github.com/MikeWasson), [Patrick Fletcher](https://github.com/pfletcher)</span></span>

<span data-ttu-id="793f2-104">Neste tutorial, você implantará um aplicativo SignalR para uma função do Windows Azure Web, usando o backplane de barramento de serviço para distribuir mensagens para cada instância de função.</span><span class="sxs-lookup"><span data-stu-id="793f2-104">In this tutorial, you will deploy a SignalR application to a Windows Azure Web Role, using the Service Bus backplane to distribute messages to each role instance.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image1.png)

<span data-ttu-id="793f2-105">Pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="793f2-105">Prerequisites:</span></span>

- <span data-ttu-id="793f2-106">Uma conta do Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="793f2-106">A Windows Azure account.</span></span>
- <span data-ttu-id="793f2-107">O [Windows Azure SDK](https://go.microsoft.com/fwlink/?linkid=254364&amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="793f2-107">The [Windows Azure SDK](https://go.microsoft.com/fwlink/?linkid=254364&amp;clcid=0x409).</span></span>
- <span data-ttu-id="793f2-108">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="793f2-108">Visual Studio 2012.</span></span>

<span data-ttu-id="793f2-109">O backplane de barramento de serviço também é compatível com [Service Bus for Windows Server](https://msdn.microsoft.com/library/windowsazure/dn282144.aspx), versão 1.1.</span><span class="sxs-lookup"><span data-stu-id="793f2-109">The service bus backplane is also compatible with [Service Bus for Windows Server](https://msdn.microsoft.com/library/windowsazure/dn282144.aspx), version 1.1.</span></span> <span data-ttu-id="793f2-110">No entanto, não é compatível com a versão 1.0 do Service Bus for Windows Server.</span><span class="sxs-lookup"><span data-stu-id="793f2-110">However, it is not compatible with version 1.0 of Service Bus for Windows Server.</span></span>

## <a name="pricing"></a><span data-ttu-id="793f2-111">Preços</span><span class="sxs-lookup"><span data-stu-id="793f2-111">Pricing</span></span>

<span data-ttu-id="793f2-112">O backplane de barramento de serviço usa tópicos para enviar mensagens.</span><span class="sxs-lookup"><span data-stu-id="793f2-112">The Service Bus backplane uses topics to send messages.</span></span> <span data-ttu-id="793f2-113">Para obter as informações mais recentes sobre preços, consulte [barramento de serviço](https://azure.microsoft.com/pricing/details/service-bus/).</span><span class="sxs-lookup"><span data-stu-id="793f2-113">For the latest pricing information, see [Service Bus](https://azure.microsoft.com/pricing/details/service-bus/).</span></span> <span data-ttu-id="793f2-114">No momento da redação deste artigo, você pode enviar 1.000.000 mensagens por mês para menor que US $1.</span><span class="sxs-lookup"><span data-stu-id="793f2-114">At the time of this writing, you can send 1,000,000 messages per month for less than $1.</span></span> <span data-ttu-id="793f2-115">O backplane envia uma mensagem de barramento de serviço para cada invocação de um método de hub SignalR.</span><span class="sxs-lookup"><span data-stu-id="793f2-115">The backplane sends a service bus message for each invocation of a SignalR hub method.</span></span> <span data-ttu-id="793f2-116">Também há algumas mensagens de controle para conexões, desconexões, unindo ou deixar grupos e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="793f2-116">There are also some control messages for connections, disconnections, joining or leaving groups, and so forth.</span></span> <span data-ttu-id="793f2-117">Na maioria dos aplicativos, a maioria do tráfego de mensagem será invocações de método do hub.</span><span class="sxs-lookup"><span data-stu-id="793f2-117">In most applications, the majority of the message traffic will be hub method invocations.</span></span>

## <a name="overview"></a><span data-ttu-id="793f2-118">Visão geral</span><span class="sxs-lookup"><span data-stu-id="793f2-118">Overview</span></span>

<span data-ttu-id="793f2-119">Antes de entrar para o tutorial detalhado, aqui está uma visão geral das tarefas que você executará.</span><span class="sxs-lookup"><span data-stu-id="793f2-119">Before we get to the detailed tutorial, here is a quick overview of what you will do.</span></span>

1. <span data-ttu-id="793f2-120">Use o portal do Windows Azure para criar um novo namespace de barramento de serviço.</span><span class="sxs-lookup"><span data-stu-id="793f2-120">Use the Windows Azure portal to create a new Service Bus namespace.</span></span>
2. <span data-ttu-id="793f2-121">Adicione esses pacotes do NuGet ao seu aplicativo:</span><span class="sxs-lookup"><span data-stu-id="793f2-121">Add these NuGet packages to your application:</span></span> 

    - [<span data-ttu-id="793f2-122">Microsoft.AspNet.SignalR</span><span class="sxs-lookup"><span data-stu-id="793f2-122">Microsoft.AspNet.SignalR</span></span>](http://nuget.org/packages/Microsoft.AspNet.SignalR)
    - [<span data-ttu-id="793f2-123">Microsoft.AspNet.SignalR.ServiceBus</span><span class="sxs-lookup"><span data-stu-id="793f2-123">Microsoft.AspNet.SignalR.ServiceBus</span></span>](http://www.nuget.org/packages/SignalR.WindowsAzureServiceBus)
3. <span data-ttu-id="793f2-124">Crie um aplicativo do SignalR.</span><span class="sxs-lookup"><span data-stu-id="793f2-124">Create a SignalR application.</span></span>
4. <span data-ttu-id="793f2-125">Adicione o seguinte código para global. asax para configurar o backplane:</span><span class="sxs-lookup"><span data-stu-id="793f2-125">Add the following code to Global.asax to configure the backplane:</span></span> 

    [!code-csharp[Main](scaleout-with-windows-azure-service-bus/samples/sample1.cs)]

<span data-ttu-id="793f2-126">Para cada aplicativo, escolha um valor diferente de "Nomedoseuaplicativo".</span><span class="sxs-lookup"><span data-stu-id="793f2-126">For each application, pick a different value for "YourAppName".</span></span> <span data-ttu-id="793f2-127">Não use o mesmo valor em vários aplicativos.</span><span class="sxs-lookup"><span data-stu-id="793f2-127">Do not use the same value across multiple applications.</span></span>

## <a name="create-the-azure-services"></a><span data-ttu-id="793f2-128">Criar os serviços do Azure</span><span class="sxs-lookup"><span data-stu-id="793f2-128">Create the Azure Services</span></span>

<span data-ttu-id="793f2-129">Criar um serviço de nuvem, conforme descrito em [como criar e implantar um serviço de nuvem](https://docs.microsoft.com/azure/cloud-services/cloud-services-how-to-create-deploy).</span><span class="sxs-lookup"><span data-stu-id="793f2-129">Create a Cloud Service, as described in [How to Create and Deploy a Cloud Service](https://docs.microsoft.com/azure/cloud-services/cloud-services-how-to-create-deploy).</span></span> <span data-ttu-id="793f2-130">Siga as etapas na seção "como: criar um serviço de nuvem usando a criação rápida".</span><span class="sxs-lookup"><span data-stu-id="793f2-130">Follow the steps in the section "How to: Create a cloud service using Quick Create".</span></span> <span data-ttu-id="793f2-131">Para este tutorial, você não precisa carregar um certificado.</span><span class="sxs-lookup"><span data-stu-id="793f2-131">For this tutorial, you do not need to upload a certificate.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image2.png)

<span data-ttu-id="793f2-132">Criar um novo namespace de barramento de serviço, conforme descrito em [como barramento de serviço para usar tópicos/assinaturas](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions).</span><span class="sxs-lookup"><span data-stu-id="793f2-132">Create a new Service Bus namespace, as described in [How to Use Service Bus Topics/Subscriptions](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions).</span></span> <span data-ttu-id="793f2-133">Siga as etapas na seção "Criar um Namespace de serviço".</span><span class="sxs-lookup"><span data-stu-id="793f2-133">Follow the steps in the section "Create a Service Namespace".</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image3.png)

> [!NOTE]
> <span data-ttu-id="793f2-134">Certifique-se de selecionar a mesma região para o serviço de nuvem e o namespace do barramento de serviço.</span><span class="sxs-lookup"><span data-stu-id="793f2-134">Make sure to select the same region for the cloud service and the Service Bus namespace.</span></span>


## <a name="create-the-visual-studio-project"></a><span data-ttu-id="793f2-135">Criar o projeto do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="793f2-135">Create the Visual Studio Project</span></span>

<span data-ttu-id="793f2-136">Inicie o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="793f2-136">Start Visual Studio.</span></span> <span data-ttu-id="793f2-137">Do **arquivo** menu, clique em **novo projeto**.</span><span class="sxs-lookup"><span data-stu-id="793f2-137">From the **File** menu, click **New Project**.</span></span>

<span data-ttu-id="793f2-138">No **novo projeto** caixa de diálogo caixa, expanda **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="793f2-138">In the **New Project** dialog box, expand **Visual C#**.</span></span> <span data-ttu-id="793f2-139">Em **modelos instalados**, selecione **nuvem** e, em seguida, selecione **serviço de nuvem do Windows Azure**.</span><span class="sxs-lookup"><span data-stu-id="793f2-139">Under **Installed Templates**, select **Cloud** and then select **Windows Azure Cloud Service**.</span></span> <span data-ttu-id="793f2-140">Mantenha o padrão do .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="793f2-140">Keep the default .NET Framework 4.5.</span></span> <span data-ttu-id="793f2-141">Nome do aplicativo ChatService e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="793f2-141">Name the application ChatService and click **OK**.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image4.png)

<span data-ttu-id="793f2-142">No **novo serviço de nuvem do Windows Azure** caixa de diálogo, selecione função de Web do ASP.NET MVC 4.</span><span class="sxs-lookup"><span data-stu-id="793f2-142">In the **New Windows Azure Cloud Service** dialog, select ASP.NET MVC 4 Web Role.</span></span> <span data-ttu-id="793f2-143">Clique no botão de seta para a direita (**&gt;**) para adicionar a função à sua solução.</span><span class="sxs-lookup"><span data-stu-id="793f2-143">Click the right-arrow button (**&gt;**) to add the role to your solution.</span></span>

<span data-ttu-id="793f2-144">Passe o mouse sobre a nova função, então o ícone de lápis visível.</span><span class="sxs-lookup"><span data-stu-id="793f2-144">Hover the mouse over the new role, so the pencil icon visible.</span></span> <span data-ttu-id="793f2-145">Clique nesse ícone para renomear a função.</span><span class="sxs-lookup"><span data-stu-id="793f2-145">Click this icon to rename the role.</span></span> <span data-ttu-id="793f2-146">Nome de função "SignalRChat" e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="793f2-146">Name the role "SignalRChat" and click **OK**.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image5.png)

<span data-ttu-id="793f2-147">No **novo projeto ASP.NET MVC 4** assistente, selecione **aplicativo de Internet**.</span><span class="sxs-lookup"><span data-stu-id="793f2-147">In the **New ASP.NET MVC 4 Project** wizard, select **Internet Application**.</span></span> <span data-ttu-id="793f2-148">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="793f2-148">Click **OK**.</span></span> <span data-ttu-id="793f2-149">O Assistente de projeto cria dois projetos:</span><span class="sxs-lookup"><span data-stu-id="793f2-149">The project wizard creates two projects:</span></span>

- <span data-ttu-id="793f2-150">ChatService: Este projeto é o aplicativo do Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="793f2-150">ChatService: This project is the Windows Azure application.</span></span> <span data-ttu-id="793f2-151">Ele define as funções do Azure e outras opções de configuração.</span><span class="sxs-lookup"><span data-stu-id="793f2-151">It defines the Azure roles and other configuration options.</span></span>
- <span data-ttu-id="793f2-152">SignalRChat: Este projeto é seu projeto ASP.NET MVC 4.</span><span class="sxs-lookup"><span data-stu-id="793f2-152">SignalRChat: This project is your ASP.NET MVC 4 project.</span></span>

## <a name="create-the-signalr-chat-application"></a><span data-ttu-id="793f2-153">Criar o aplicativo de Chat de SignalR</span><span class="sxs-lookup"><span data-stu-id="793f2-153">Create the SignalR Chat Application</span></span>

<span data-ttu-id="793f2-154">Para criar o aplicativo de chat, siga as etapas no tutorial [Introdução ao SignalR e MVC 4](tutorial-getting-started-with-signalr-and-mvc-4.md).</span><span class="sxs-lookup"><span data-stu-id="793f2-154">To create the chat application, follow the steps in the tutorial [Getting Started with SignalR and MVC 4](tutorial-getting-started-with-signalr-and-mvc-4.md).</span></span>

<span data-ttu-id="793f2-155">Use NuGet para instalar as bibliotecas necessárias.</span><span class="sxs-lookup"><span data-stu-id="793f2-155">Use NuGet to install the required libraries.</span></span> <span data-ttu-id="793f2-156">Do **ferramentas** menu, selecione **Gerenciador de biblioteca de pacote**, em seguida, selecione **Package Manager Console**.</span><span class="sxs-lookup"><span data-stu-id="793f2-156">From the **Tools** menu, select **Library Package Manager**, then select **Package Manager Console**.</span></span> <span data-ttu-id="793f2-157">No **Package Manager Console** janela, digite os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="793f2-157">In the **Package Manager Console** window, enter the following commands:</span></span>

[!code-powershell[Main](scaleout-with-windows-azure-service-bus/samples/sample2.ps1)]

<span data-ttu-id="793f2-158">Use o `-ProjectName` opção para instalar os pacotes para o projeto ASP.NET MVC, em vez de projeto do Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="793f2-158">Use the `-ProjectName` option to install the packages to the ASP.NET MVC project, rather than the Windows Azure project.</span></span>

## <a name="configure-the-backplane"></a><span data-ttu-id="793f2-159">Configurar o Backplane</span><span class="sxs-lookup"><span data-stu-id="793f2-159">Configure the Backplane</span></span>

<span data-ttu-id="793f2-160">No arquivo global asax do seu aplicativo, adicione o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="793f2-160">In your application's Global.asax file, add the following code:</span></span>

[!code-csharp[Main](scaleout-with-windows-azure-service-bus/samples/sample3.cs)]

<span data-ttu-id="793f2-161">Agora você precisa obter sua cadeia de conexão do barramento de serviço.</span><span class="sxs-lookup"><span data-stu-id="793f2-161">Now you need to get your service bus connection string.</span></span> <span data-ttu-id="793f2-162">No portal do Azure, selecione o namespace de barramento de serviço que você criou e clique no ícone de chave de acesso.</span><span class="sxs-lookup"><span data-stu-id="793f2-162">In the Azure portal, select the service bus namespace that you created and click the Access Key icon.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image6.png)

<span data-ttu-id="793f2-163">Copie a cadeia de conexão para a área de transferência e, em seguida, cole-o no *connectionString* variável.</span><span class="sxs-lookup"><span data-stu-id="793f2-163">Copy the connection string to the clipboard, then paste it into the *connectionString* variable.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image7.png)

[!code-csharp[Main](scaleout-with-windows-azure-service-bus/samples/sample4.cs)]

## <a name="deploy-to-azure"></a><span data-ttu-id="793f2-164">Implantar no Azure</span><span class="sxs-lookup"><span data-stu-id="793f2-164">Deploy to Azure</span></span>

<span data-ttu-id="793f2-165">No Gerenciador de soluções, expanda o **funções** pasta dentro do projeto ChatService.</span><span class="sxs-lookup"><span data-stu-id="793f2-165">In Solution Explorer, expand the **Roles** folder inside the ChatService project.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image8.png)

<span data-ttu-id="793f2-166">A função SignalRChat e selecione **propriedades**.</span><span class="sxs-lookup"><span data-stu-id="793f2-166">Right-click the SignalRChat role and select **Properties**.</span></span> <span data-ttu-id="793f2-167">Selecione o **configuração** guia. Em **instâncias** selecione 2.</span><span class="sxs-lookup"><span data-stu-id="793f2-167">Select the **Configuration** tab. Under **Instances** select 2.</span></span> <span data-ttu-id="793f2-168">Você também pode definir o tamanho da VM **Extrapequeno**.</span><span class="sxs-lookup"><span data-stu-id="793f2-168">You can also set the VM size to **Extra Small**.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image9.png)

<span data-ttu-id="793f2-169">Salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="793f2-169">Save the changes.</span></span>

<span data-ttu-id="793f2-170">No Gerenciador de soluções, clique com botão direito no projeto ChatService.</span><span class="sxs-lookup"><span data-stu-id="793f2-170">In Solution Explorer, right-click the ChatService project.</span></span> <span data-ttu-id="793f2-171">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="793f2-171">Select **Publish**.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image10.png)

<span data-ttu-id="793f2-172">Se esta for sua primeira publicação de tempo para o Windows Azure, você deve baixar suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="793f2-172">If this is your first time publishing to Windows Azure, you must download your credentials.</span></span> <span data-ttu-id="793f2-173">No **publicar** assistente, clique em "Entrar para baixar credenciais".</span><span class="sxs-lookup"><span data-stu-id="793f2-173">In the **Publish** wizard, click "Sign in to download credentials".</span></span> <span data-ttu-id="793f2-174">Isso solicitará que você entrar no portal do Windows Azure e baixar um arquivo de configurações de publicação.</span><span class="sxs-lookup"><span data-stu-id="793f2-174">This will prompt you to sign into the Windows Azure portal and download a publish settings file.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image11.png)

<span data-ttu-id="793f2-175">Clique em **importação** e selecione o arquivo de configurações de publicação que você baixou.</span><span class="sxs-lookup"><span data-stu-id="793f2-175">Click **Import** and select the publish settings file that you downloaded.</span></span>

<span data-ttu-id="793f2-176">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="793f2-176">Click **Next**.</span></span> <span data-ttu-id="793f2-177">No **configurações de publicação** caixa de diálogo, em **serviço de nuvem**, selecione o serviço de nuvem que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="793f2-177">In the **Publish Settings** dialog, under **Cloud Service**, select the cloud service that you created earlier.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image12.png)

<span data-ttu-id="793f2-178">Clique em **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="793f2-178">Click **Publish**.</span></span> <span data-ttu-id="793f2-179">Pode levar alguns minutos para implantar o aplicativo e iniciar as máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="793f2-179">It can take a few minutes to deploy the application and start the VMs.</span></span>

<span data-ttu-id="793f2-180">Agora quando você executa o aplicativo, as instâncias de função se comunicar por meio do barramento de serviço do Azure, usando um tópico do barramento de serviço.</span><span class="sxs-lookup"><span data-stu-id="793f2-180">Now when you run the chat application, the role instances communicate through Azure Service Bus, using a Service Bus topic.</span></span> <span data-ttu-id="793f2-181">Um tópico é uma fila de mensagens que permite que vários assinantes.</span><span class="sxs-lookup"><span data-stu-id="793f2-181">A topic is a message queue that allows multiple subscribers.</span></span>

<span data-ttu-id="793f2-182">O backplane cria automaticamente o tópico e as assinaturas.</span><span class="sxs-lookup"><span data-stu-id="793f2-182">The backplane automatically creates the topic and the subscriptions.</span></span> <span data-ttu-id="793f2-183">Para ver as assinaturas e a atividade de mensagens, abra o portal do Azure, selecione o namespace de barramento de serviço e clique em "Tópicos de".</span><span class="sxs-lookup"><span data-stu-id="793f2-183">To see the subscriptions and message activity, open the Azure portal, select the Service Bus namespace, and click on "Topics".</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image13.png)

<span data-ttu-id="793f2-184">Ele poderá levar alguns minutos para que a atividade de mensagem exibida no painel.</span><span class="sxs-lookup"><span data-stu-id="793f2-184">It make take a few minutes for the message activity to show up in the dashboard.</span></span>

![](scaleout-with-windows-azure-service-bus/_static/image14.png)

<span data-ttu-id="793f2-185">SignalR gerencia o tempo de vida do tópico.</span><span class="sxs-lookup"><span data-stu-id="793f2-185">SignalR manages the topic lifetime.</span></span> <span data-ttu-id="793f2-186">Como o aplicativo é implantado, não tente excluir tópicos manualmente ou alterar as configurações no tópico.</span><span class="sxs-lookup"><span data-stu-id="793f2-186">As long as your application is deployed, don't try to manually delete topics or change settings on the topic.</span></span>