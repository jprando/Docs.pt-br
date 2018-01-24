---
uid: signalr/overview/older-versions/tutorial-getting-started-with-signalr-and-mvc-4
title: "Tutorial: Introdução ao SignalR 1. x e MVC 4 | Microsoft Docs"
author: pfletcher
description: Use o SignalR do ASP.NET e ASP.NET MVC 4 para criar um aplicativo de bate-papo em tempo real.
ms.author: aspnetcontent
manager: wpickett
ms.date: 03/29/2013
ms.topic: article
ms.assetid: eeef9f73-6de3-49f9-b50b-9af22108f2ce
ms.technology: dotnet-signalr
ms.prod: .net-framework
msc.legacyurl: /signalr/overview/older-versions/tutorial-getting-started-with-signalr-and-mvc-4
msc.type: authoredcontent
ms.openlocfilehash: e678c85520613fea2a8d00de60aca04d895d6307
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2017
---
<a name="tutorial-getting-started-with-signalr-1x-and-mvc-4"></a><span data-ttu-id="5b93b-103">Tutorial: Introdução ao SignalR 1. x e MVC 4</span><span class="sxs-lookup"><span data-stu-id="5b93b-103">Tutorial: Getting Started with SignalR 1.x and MVC 4</span></span>
====================
<span data-ttu-id="5b93b-104">por [Patrick Fletcher](https://github.com/pfletcher), [Tim Teebken](https://github.com/timlt)</span><span class="sxs-lookup"><span data-stu-id="5b93b-104">by [Patrick Fletcher](https://github.com/pfletcher), [Tim Teebken](https://github.com/timlt)</span></span>

> <span data-ttu-id="5b93b-105">Este tutorial mostra como usar o SignalR do ASP.NET para criar um aplicativo de bate-papo em tempo real.</span><span class="sxs-lookup"><span data-stu-id="5b93b-105">This tutorial shows how to use ASP.NET SignalR to create a real-time chat application.</span></span> <span data-ttu-id="5b93b-106">Você adicionará o SignalR para um aplicativo MVC 4 e criar uma exibição de bate-papo para enviar e exibir as mensagens.</span><span class="sxs-lookup"><span data-stu-id="5b93b-106">You will add SignalR to an MVC 4 application and create a chat view to send and display messages.</span></span>


## <a name="overview"></a><span data-ttu-id="5b93b-107">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="5b93b-107">Overview</span></span>

<span data-ttu-id="5b93b-108">Este tutorial o apresenta ao desenvolvimento de aplicativos web em tempo real com ASP.NET SignalR e ASP.NET MVC 4.</span><span class="sxs-lookup"><span data-stu-id="5b93b-108">This tutorial introduces you to real-time web application development with ASP.NET SignalR and ASP.NET MVC 4.</span></span> <span data-ttu-id="5b93b-109">O tutorial usa o mesmo código de aplicativo de bate-papo, como o [tutorial de Introdução SignalR](tutorial-getting-started-with-signalr.md), mas mostra como adicioná-lo a um aplicativo MVC 4 com base no modelo de Internet.</span><span class="sxs-lookup"><span data-stu-id="5b93b-109">The tutorial uses the same chat application code as the [SignalR Getting Started tutorial](tutorial-getting-started-with-signalr.md), but shows how to add it to an MVC 4 application based on the Internet template.</span></span>

<span data-ttu-id="5b93b-110">Neste tópico, você aprenderá as seguintes tarefas de desenvolvimento SignalR:</span><span class="sxs-lookup"><span data-stu-id="5b93b-110">In this topic you will learn the following SignalR development tasks:</span></span>

- <span data-ttu-id="5b93b-111">Adicionar a biblioteca de SignalR para um aplicativo MVC 4.</span><span class="sxs-lookup"><span data-stu-id="5b93b-111">Adding the SignalR library to an MVC 4 application.</span></span>
- <span data-ttu-id="5b93b-112">Criando uma classe de hub para enviar por push o conteúdo aos clientes.</span><span class="sxs-lookup"><span data-stu-id="5b93b-112">Creating a hub class to push content to clients.</span></span>
- <span data-ttu-id="5b93b-113">Usando a biblioteca de jQuery SignalR em uma página da web para enviar mensagens e exibir as atualizações do hub.</span><span class="sxs-lookup"><span data-stu-id="5b93b-113">Using the SignalR jQuery library in a web page to send messages and display updates from the hub.</span></span>

<span data-ttu-id="5b93b-114">A captura de tela a seguir mostra o aplicativo de chat concluído em execução em um navegador.</span><span class="sxs-lookup"><span data-stu-id="5b93b-114">The following screen shot shows the completed chat application running in a browser.</span></span>

![Instâncias de bate-papo](tutorial-getting-started-with-signalr-and-mvc-4/_static/image2.png)

<span data-ttu-id="5b93b-116">Seções:</span><span class="sxs-lookup"><span data-stu-id="5b93b-116">Sections:</span></span>

- [<span data-ttu-id="5b93b-117">Configurar o projeto</span><span class="sxs-lookup"><span data-stu-id="5b93b-117">Set up the Project</span></span>](#setup)
- [<span data-ttu-id="5b93b-118">Executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="5b93b-118">Run the Sample</span></span>](#run)
- [<span data-ttu-id="5b93b-119">Examine o código</span><span class="sxs-lookup"><span data-stu-id="5b93b-119">Examine the Code</span></span>](#code)
- [<span data-ttu-id="5b93b-120">Próximas Etapas</span><span class="sxs-lookup"><span data-stu-id="5b93b-120">Next Steps</span></span>](#next)

<a id="setup"></a>

## <a name="set-up-the-project"></a><span data-ttu-id="5b93b-121">Configurar o projeto</span><span class="sxs-lookup"><span data-stu-id="5b93b-121">Set up the Project</span></span>

<span data-ttu-id="5b93b-122">Pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="5b93b-122">Prerequisites:</span></span>

- <span data-ttu-id="5b93b-123">Visual Studio 2010 SP1, o Visual Studio 2012 ou Visual Studio 2012 Express.</span><span class="sxs-lookup"><span data-stu-id="5b93b-123">Visual Studio 2010 SP1, Visual Studio 2012, or Visual Studio 2012 Express.</span></span> <span data-ttu-id="5b93b-124">Se você não tiver o Visual Studio, consulte [ASP.NET Downloads](https://www.asp.net/downloads) para obter o Visual Studio 2012 Express desenvolvimento ferramenta gratuita.</span><span class="sxs-lookup"><span data-stu-id="5b93b-124">If you do not have Visual Studio, see [ASP.NET Downloads](https://www.asp.net/downloads) to get the free Visual Studio 2012 Express Development Tool.</span></span>
- <span data-ttu-id="5b93b-125">Para o Visual Studio 2010, instale [ASP.NET MVC 4](https://www.microsoft.com/en-us/download/details.aspx?id=30683).</span><span class="sxs-lookup"><span data-stu-id="5b93b-125">For Visual Studio 2010, install [ASP.NET MVC 4](https://www.microsoft.com/en-us/download/details.aspx?id=30683).</span></span>

<span data-ttu-id="5b93b-126">Esta seção mostra como criar um aplicativo ASP.NET MVC 4, adicione a biblioteca de SignalR e criar o aplicativo de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="5b93b-126">This section shows how to create an ASP.NET MVC 4 application, add the SignalR library, and create the chat application.</span></span>

1. 1. <span data-ttu-id="5b93b-127">No Visual Studio criar um aplicativo ASP.NET MVC 4, nomeie-o SignalRChat e clique em Okey.</span><span class="sxs-lookup"><span data-stu-id="5b93b-127">In Visual Studio create an ASP.NET MVC 4 application, name it SignalRChat, and click OK.</span></span>

        > [!NOTE]
        > <span data-ttu-id="5b93b-128">No VS 2010, selecione **.NET Framework 4** no controle de lista suspensa de versão do Framework.</span><span class="sxs-lookup"><span data-stu-id="5b93b-128">In VS 2010, select **.NET Framework 4** in the Framework version dropdown control.</span></span> <span data-ttu-id="5b93b-129">Código de SignalR é executado em versões do .NET Framework 4 e 4.5.</span><span class="sxs-lookup"><span data-stu-id="5b93b-129">SignalR code runs on .NET Framework versions 4 and 4.5.</span></span>

        ![Criar web mvc](tutorial-getting-started-with-signalr-and-mvc-4/_static/image3.png)
    2. <span data-ttu-id="5b93b-131">Selecione o modelo de aplicativo de Internet, desmarque a opção de **criar um projeto de teste de unidade**e clique em Okey.</span><span class="sxs-lookup"><span data-stu-id="5b93b-131">Select the Internet Application template, clear the option to **Create a unit test project**, and click OK.</span></span>

        ![Criar um site da internet mvc](tutorial-getting-started-with-signalr-and-mvc-4/_static/image4.png)
    3. <span data-ttu-id="5b93b-133">Abra o **ferramentas | Gerenciador de biblioteca de pacote | Package Manager Console** e execute o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="5b93b-133">Open the **Tools | Library Package Manager | Package Manager Console** and run the following command.</span></span> <span data-ttu-id="5b93b-134">Esta etapa adiciona ao projeto um conjunto de arquivos de script e referências de assembly que habilitar a funcionalidade do SignalR.</span><span class="sxs-lookup"><span data-stu-id="5b93b-134">This step adds to the project a set of script files and assembly references that enable SignalR functionality.</span></span>

        `install-package Microsoft.AspNet.SignalR -Version 1.1.3`
    4. <span data-ttu-id="5b93b-135">Em **Solution Explorer** expanda a pasta de Scripts.</span><span class="sxs-lookup"><span data-stu-id="5b93b-135">In **Solution Explorer** expand the Scripts folder.</span></span> <span data-ttu-id="5b93b-136">Observe que as bibliotecas de scripts para o SignalR foram adicionadas ao projeto.</span><span class="sxs-lookup"><span data-stu-id="5b93b-136">Note that script libraries for SignalR have been added to the project.</span></span>

        ![Referências de biblioteca](tutorial-getting-started-with-signalr-and-mvc-4/_static/image6.png)
    5. <span data-ttu-id="5b93b-138">Em **Solution Explorer**, clique com o botão direito, selecione **adicionar | Nova pasta**, e adicione uma nova pasta chamada **Hubs**.</span><span class="sxs-lookup"><span data-stu-id="5b93b-138">In **Solution Explorer**, right-click the project, select **Add | New Folder**, and add a new folder named **Hubs**.</span></span>
    6. <span data-ttu-id="5b93b-139">Clique com botão direito do **Hubs** pasta, clique em **adicionar | Classe**e crie uma nova classe c# chamada **ChatHub.cs**.</span><span class="sxs-lookup"><span data-stu-id="5b93b-139">Right-click the **Hubs** folder, click **Add | Class**, and create a new C# class named **ChatHub.cs**.</span></span> <span data-ttu-id="5b93b-140">Você usará essa classe como um hub de servidor do SignalR que envia mensagens para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="5b93b-140">You will use this class as a SignalR server hub that sends messages to all clients.</span></span>

> [!NOTE]
> <span data-ttu-id="5b93b-141">Se você usar o Visual Studio 2012 e tiver instalado o [atualização ASP.NET e Web Tools 2012.2](../../../visual-studio/overview/2012/aspnet-and-web-tools-20122-release-notes-rtw.md#_Installation), você pode usar o novo modelo de item de SignalR para criar a classe de hub.</span><span class="sxs-lookup"><span data-stu-id="5b93b-141">If you use Visual Studio 2012 and have installed the [ASP.NET and Web Tools 2012.2 update](../../../visual-studio/overview/2012/aspnet-and-web-tools-20122-release-notes-rtw.md#_Installation), you can use the new SignalR item template to create the hub class.</span></span> <span data-ttu-id="5b93b-142">Para fazer isso, clique com botão direito do **Hubs** pasta, clique em **adicionar | Novo Item**, selecione **classe de Hub SignalR (v1)**e nomeie a classe **ChatHub.cs**.</span><span class="sxs-lookup"><span data-stu-id="5b93b-142">To do that, right-click the **Hubs** folder, click **Add | New Item**, select **SignalR Hub Class (v1)**, and name the class **ChatHub.cs**.</span></span>


1. <span data-ttu-id="5b93b-143">Substitua o código no **ChatHub** classe com o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="5b93b-143">Replace the code in the **ChatHub** class with the following code.</span></span>

    [!code-csharp[Main](tutorial-getting-started-with-signalr-and-mvc-4/samples/sample1.cs)]
2. <span data-ttu-id="5b93b-144">Abra o **global. asax** de arquivos para o projeto e adicionar uma chamada ao método `RouteTable.Routes.MapHubs();` como a primeira linha do código no `Application_Start` método.</span><span class="sxs-lookup"><span data-stu-id="5b93b-144">Open the **Global.asax** file for the project, and add a call to the method `RouteTable.Routes.MapHubs();` as the first line of code in the `Application_Start` method.</span></span> <span data-ttu-id="5b93b-145">Esse código registra a rota padrão para hubs de SignalR e deve ser chamado antes de registrar todas as outras rotas.</span><span class="sxs-lookup"><span data-stu-id="5b93b-145">This code registers the default route for SignalR hubs and must be called before you register any other routes.</span></span> <span data-ttu-id="5b93b-146">Concluído `Application_Start` método é semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="5b93b-146">The completed `Application_Start` method looks like the following example.</span></span>

    [!code-csharp[Main](tutorial-getting-started-with-signalr-and-mvc-4/samples/sample2.cs)]
3. <span data-ttu-id="5b93b-147">Editar o `HomeController` classe encontrada no **Controllers/HomeController.cs** e adicione o seguinte método à classe.</span><span class="sxs-lookup"><span data-stu-id="5b93b-147">Edit the `HomeController` class found in **Controllers/HomeController.cs** and add the following method to the class.</span></span> <span data-ttu-id="5b93b-148">Esse método retorna o **bate-papo** modo de exibição que você criará em uma etapa posterior.</span><span class="sxs-lookup"><span data-stu-id="5b93b-148">This method returns the **Chat** view that you will create in a later step.</span></span>

    [!code-csharp[Main](tutorial-getting-started-with-signalr-and-mvc-4/samples/sample3.cs)]
4. <span data-ttu-id="5b93b-149">Clique dentro do `Chat` método recém-criado e clique em **adicionar exibição** para criar um novo arquivo de exibição.</span><span class="sxs-lookup"><span data-stu-id="5b93b-149">Right-click within the `Chat` method you just created, and click **Add View** to create a new view file.</span></span>
5. <span data-ttu-id="5b93b-150">No **adicionar exibição** caixa de diálogo, verifique se a caixa de seleção é selecionada para **usar uma layout ou página mestra** (desmarque as outras caixas de seleção) e, em seguida, clique em **adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5b93b-150">In the **Add View** dialog, make sure the check box is selected to **Use a layout or master page** (clear the other check boxes), and then click **Add**.</span></span>

    ![Adicionar uma exibição](tutorial-getting-started-with-signalr-and-mvc-4/_static/image8.png)
6. <span data-ttu-id="5b93b-152">Edite o novo arquivo de modo de exibição denominado **Chat.cshtml**.</span><span class="sxs-lookup"><span data-stu-id="5b93b-152">Edit the new view file named **Chat.cshtml**.</span></span> <span data-ttu-id="5b93b-153">Após o &lt;h2&gt; marca, cole o seguinte &lt;div&gt; seção e `@section scripts` bloco de código para a página.</span><span class="sxs-lookup"><span data-stu-id="5b93b-153">After the &lt;h2&gt; tag, paste the following &lt;div&gt; section and `@section scripts` code block into the page.</span></span> <span data-ttu-id="5b93b-154">Esse script permite que a página enviar mensagens de chat e exibir as mensagens do servidor.</span><span class="sxs-lookup"><span data-stu-id="5b93b-154">This script enables the page to send chat messages and display messages from the server.</span></span> <span data-ttu-id="5b93b-155">O código completo para o modo de exibição de bate-papo aparece no bloco de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="5b93b-155">The complete code for the chat view appears in the following code block.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5b93b-156">Quando você adiciona o SignalR e outras bibliotecas de script ao seu projeto do Visual Studio, o Gerenciador de pacotes pode instalar as versões dos scripts que são mais recentes do que as versões mostradas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="5b93b-156">When you add SignalR and other script libraries to your Visual Studio project, the Package Manager might install versions of the scripts that are more recent than the versions shown in this topic.</span></span> <span data-ttu-id="5b93b-157">Certifique-se de que as referências de script em seu código correspondem às versões das bibliotecas de script instaladas em seu projeto.</span><span class="sxs-lookup"><span data-stu-id="5b93b-157">Make sure that the script references in your code match the versions of the script libraries installed in your project.</span></span>

    [!code-cshtml[Main](tutorial-getting-started-with-signalr-and-mvc-4/samples/sample4.cshtml)]
7. <span data-ttu-id="5b93b-158">**Salvar todos os** para o projeto.</span><span class="sxs-lookup"><span data-stu-id="5b93b-158">**Save All** for the project.</span></span>

<a id="run"></a>

## <a name="run-the-sample"></a><span data-ttu-id="5b93b-159">Executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="5b93b-159">Run the Sample</span></span>

1. <span data-ttu-id="5b93b-160">Pressione F5 para executar o projeto no modo de depuração.</span><span class="sxs-lookup"><span data-stu-id="5b93b-160">Press F5 to run the project in debug mode.</span></span>
2. <span data-ttu-id="5b93b-161">Na linha de endereço do navegador, acrescente **inicial/bate-papo** para a URL da página padrão para o projeto.</span><span class="sxs-lookup"><span data-stu-id="5b93b-161">In the browser address line, append **/home/chat** to the URL of the default page for the project.</span></span> <span data-ttu-id="5b93b-162">A página de bate-papo carrega em uma instância do navegador e solicitará um nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="5b93b-162">The Chat page loads in a browser instance and prompts for a user name.</span></span>

    ![Insira o nome de usuário](tutorial-getting-started-with-signalr-and-mvc-4/_static/image9.png)
3. <span data-ttu-id="5b93b-164">Insira um nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="5b93b-164">Enter a user name.</span></span>
4. <span data-ttu-id="5b93b-165">Copie a URL da linha de endereço do navegador e usá-lo para abrir duas ou mais instâncias de navegador.</span><span class="sxs-lookup"><span data-stu-id="5b93b-165">Copy the URL from the address line of the browser and use it to open two more browser instances.</span></span> <span data-ttu-id="5b93b-166">Em cada instância do navegador, digite um nome de usuário exclusivo.</span><span class="sxs-lookup"><span data-stu-id="5b93b-166">In each browser instance, enter a unique user name.</span></span>
5. <span data-ttu-id="5b93b-167">Em cada instância do navegador, adicione um comentário e clique em **enviar**.</span><span class="sxs-lookup"><span data-stu-id="5b93b-167">In each browser instance, add a comment and click **Send**.</span></span> <span data-ttu-id="5b93b-168">Os comentários devem exibir em todas as instâncias do navegador.</span><span class="sxs-lookup"><span data-stu-id="5b93b-168">The comments should display in all browser instances.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b93b-169">Este aplicativo de chat simples não mantém o contexto de discussão no servidor.</span><span class="sxs-lookup"><span data-stu-id="5b93b-169">This simple chat application does not maintain the discussion context on the server.</span></span> <span data-ttu-id="5b93b-170">O hub transmite comentários para todos os usuários atuais.</span><span class="sxs-lookup"><span data-stu-id="5b93b-170">The hub broadcasts comments to all current users.</span></span> <span data-ttu-id="5b93b-171">Os usuários que entram no bate-papo posteriormente verá mensagens adicionadas desde o momento que entrarem.</span><span class="sxs-lookup"><span data-stu-id="5b93b-171">Users who join the chat later will see messages added from the time they join.</span></span>
6. <span data-ttu-id="5b93b-172">A captura de tela a seguir mostra o aplicativo de chat em execução em um navegador.</span><span class="sxs-lookup"><span data-stu-id="5b93b-172">The following screen shot shows the chat application running in a browser.</span></span>

    ![Navegadores de chat](tutorial-getting-started-with-signalr-and-mvc-4/_static/image11.png)
7. <span data-ttu-id="5b93b-174">Em **Solution Explorer**, inspecione o **documentos de Script** nó para o aplicativo em execução.</span><span class="sxs-lookup"><span data-stu-id="5b93b-174">In **Solution Explorer**, inspect the **Script Documents** node for the running application.</span></span> <span data-ttu-id="5b93b-175">Esse nó é visível no modo de depuração, se você estiver usando o Internet Explorer como navegador.</span><span class="sxs-lookup"><span data-stu-id="5b93b-175">This node is visible in debug mode if you are using Internet Explorer as your browser.</span></span> <span data-ttu-id="5b93b-176">Há um arquivo de script denominado **hubs** que a biblioteca de SignalR gera dinamicamente em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="5b93b-176">There is a script file named **hubs** that the SignalR library dynamically generates at runtime.</span></span> <span data-ttu-id="5b93b-177">Este arquivo gerencia a comunicação entre jQuery script e código do lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="5b93b-177">This file manages the communication between jQuery script and server-side code.</span></span> <span data-ttu-id="5b93b-178">Se você usar um navegador que não seja o Internet Explorer, você também pode acessar dinâmico **hubs** arquivo navegando até ele diretamente, por exemplo http://mywebsite/signalr/hubs.</span><span class="sxs-lookup"><span data-stu-id="5b93b-178">If you use a browser other than Internet Explorer, you can also access the dynamic **hubs** file by browsing to it directly, for example http://mywebsite/signalr/hubs.</span></span>

    ![Script de hub gerado](tutorial-getting-started-with-signalr-and-mvc-4/_static/image13.png)

<a id="code"></a>

## <a name="examine-the-code"></a><span data-ttu-id="5b93b-180">Examine o código</span><span class="sxs-lookup"><span data-stu-id="5b93b-180">Examine the Code</span></span>

<span data-ttu-id="5b93b-181">O aplicativo de chat SignalR demonstra duas tarefas básicas de desenvolvimento SignalR: Criando um hub de como o objeto de coordenação principal no servidor e, usando a biblioteca de jQuery SignalR para enviar e receber mensagens.</span><span class="sxs-lookup"><span data-stu-id="5b93b-181">The SignalR chat application demonstrates two basic SignalR development tasks: creating a hub as the main coordination object on the server, and using the SignalR jQuery library to send and receive messages.</span></span>

### <a name="signalr-hubs"></a><span data-ttu-id="5b93b-182">Hubs de SignalR</span><span class="sxs-lookup"><span data-stu-id="5b93b-182">SignalR Hubs</span></span>

<span data-ttu-id="5b93b-183">No exemplo de código a **ChatHub** classe deriva o **Microsoft.AspNet.SignalR.Hub** classe.</span><span class="sxs-lookup"><span data-stu-id="5b93b-183">In the code sample the **ChatHub** class derives from the **Microsoft.AspNet.SignalR.Hub** class.</span></span> <span data-ttu-id="5b93b-184">Derivando de **Hub** classe é uma maneira útil para criar um aplicativo do SignalR.</span><span class="sxs-lookup"><span data-stu-id="5b93b-184">Deriving from the **Hub** class is a useful way to build a SignalR application.</span></span> <span data-ttu-id="5b93b-185">Você pode criar métodos públicos em sua classe de hub e, em seguida, esses métodos de acesso chamando-los a partir de scripts jQuery em uma página da web.</span><span class="sxs-lookup"><span data-stu-id="5b93b-185">You can create public methods on your hub class and then access those methods by calling them from jQuery scripts in a web page.</span></span>

<span data-ttu-id="5b93b-186">No código de bate-papo, clientes chamar o **ChatHub.Send** para enviar uma nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="5b93b-186">In the chat code, clients call the **ChatHub.Send** method to send a new message.</span></span> <span data-ttu-id="5b93b-187">O hub por sua vez envia a mensagem a todos os clientes chamando **Clients.All.addNewMessageToPage**.</span><span class="sxs-lookup"><span data-stu-id="5b93b-187">The hub in turn sends the message to all clients by calling **Clients.All.addNewMessageToPage**.</span></span>

<span data-ttu-id="5b93b-188">O **enviar** método demonstra vários conceitos de hub:</span><span class="sxs-lookup"><span data-stu-id="5b93b-188">The **Send** method demonstrates several hub concepts :</span></span>

- <span data-ttu-id="5b93b-189">Declare métodos públicos em um hub para que os clientes podem chamá-los.</span><span class="sxs-lookup"><span data-stu-id="5b93b-189">Declare public methods on a hub so that clients can call them.</span></span>
- <span data-ttu-id="5b93b-190">Use o **Microsoft.AspNet.SignalR.Hub.Clients** propriedade para acessar todos os clientes conectados a esse hub.</span><span class="sxs-lookup"><span data-stu-id="5b93b-190">Use the **Microsoft.AspNet.SignalR.Hub.Clients** property to access all clients connected to this hub.</span></span>
- <span data-ttu-id="5b93b-191">Chamar uma função de jQuery no cliente (como o `addNewMessageToPage` função) para atualizar clientes.</span><span class="sxs-lookup"><span data-stu-id="5b93b-191">Call a jQuery function on the client (such as the `addNewMessageToPage` function) to update clients.</span></span>

    [!code-csharp[Main](tutorial-getting-started-with-signalr-and-mvc-4/samples/sample5.cs)]

### <a name="signalr-and-jquery"></a><span data-ttu-id="5b93b-192">SignalR e jQuery</span><span class="sxs-lookup"><span data-stu-id="5b93b-192">SignalR and jQuery</span></span>

<span data-ttu-id="5b93b-193">O **Chat.cshtml** exibir o arquivo no exemplo de código mostra como usar a biblioteca de jQuery SignalR para se comunicar com um hub SignalR.</span><span class="sxs-lookup"><span data-stu-id="5b93b-193">The **Chat.cshtml** view file in the code sample shows how to use the SignalR jQuery library to communicate with a SignalR hub.</span></span> <span data-ttu-id="5b93b-194">As tarefas essenciais no código estão criando uma referência para o proxy geradas automaticamente para o hub, declarar uma função que o servidor pode chamar para conteúdo por push aos clientes e iniciar uma conexão para enviar mensagens para o hub.</span><span class="sxs-lookup"><span data-stu-id="5b93b-194">The essential tasks in the code are creating a reference to the auto-generated proxy for the hub, declaring a function that the server can call to push content to clients, and starting a connection to send messages to the hub.</span></span>

<span data-ttu-id="5b93b-195">O código a seguir declara um proxy para um hub.</span><span class="sxs-lookup"><span data-stu-id="5b93b-195">The following code declares a proxy for a hub.</span></span>

[!code-javascript[Main](tutorial-getting-started-with-signalr-and-mvc-4/samples/sample6.js)]

> [!NOTE]
> <span data-ttu-id="5b93b-196">Em jQuery a referência para a classe de servidor e seus membros está em minúsculas concatenadas.</span><span class="sxs-lookup"><span data-stu-id="5b93b-196">In jQuery the reference to the server class and its members is in camel case.</span></span> <span data-ttu-id="5b93b-197">O exemplo de código referencia o c# **ChatHub** classe jQuery como **chatHub**.</span><span class="sxs-lookup"><span data-stu-id="5b93b-197">The code sample references the C# **ChatHub** class in jQuery as **chatHub**.</span></span> <span data-ttu-id="5b93b-198">Se você quiser fazer referência a `ChatHub` classe jQuery com Pascal convencional maiusculas e minúsculas como você faria no c#, editar o arquivo de classe ChatHub.cs.</span><span class="sxs-lookup"><span data-stu-id="5b93b-198">If you want to reference the `ChatHub` class in jQuery with conventional Pascal casing as you would in C#, edit the ChatHub.cs class file.</span></span> <span data-ttu-id="5b93b-199">Adicionar um `using` instrução para fazer referência a `Microsoft.AspNet.SignalR.Hubs` namespace.</span><span class="sxs-lookup"><span data-stu-id="5b93b-199">Add a `using` statement to reference the `Microsoft.AspNet.SignalR.Hubs` namespace.</span></span> <span data-ttu-id="5b93b-200">Em seguida, adicione o `HubName` de atributo para o `ChatHub` classe, por exemplo `[HubName("ChatHub")]`.</span><span class="sxs-lookup"><span data-stu-id="5b93b-200">Then add the `HubName` attribute to the `ChatHub` class, for example `[HubName("ChatHub")]`.</span></span> <span data-ttu-id="5b93b-201">Por fim, atualize sua referência jQuery para o `ChatHub` classe.</span><span class="sxs-lookup"><span data-stu-id="5b93b-201">Finally, update your jQuery reference to the `ChatHub` class.</span></span>


<span data-ttu-id="5b93b-202">O código a seguir mostra como criar uma função de retorno de chamada no script.</span><span class="sxs-lookup"><span data-stu-id="5b93b-202">The following code shows how to create a callback function in the script.</span></span> <span data-ttu-id="5b93b-203">A classe de hub no servidor chama esta função para enviar atualizações de conteúdo para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="5b93b-203">The hub class on the server calls this function to push content updates to each client.</span></span> <span data-ttu-id="5b93b-204">A chamada opcional para o `htmlEncode` função mostra uma maneira para HTML codifica o conteúdo da mensagem antes de exibi-lo na página, como uma maneira de impedir injeção de script.</span><span class="sxs-lookup"><span data-stu-id="5b93b-204">The optional call to the `htmlEncode` function shows a way to HTML encode the message content before displaying it in the page, as a way to prevent script injection.</span></span>

[!code-html[Main](tutorial-getting-started-with-signalr-and-mvc-4/samples/sample7.html)]

<span data-ttu-id="5b93b-205">O código a seguir mostra como abrir uma conexão com o hub.</span><span class="sxs-lookup"><span data-stu-id="5b93b-205">The following code shows how to open a connection with the hub.</span></span> <span data-ttu-id="5b93b-206">O código começa a conexão e, em seguida, passa uma função para manipular o evento de clique no **enviar** botão na página de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="5b93b-206">The code starts the connection and then passes it a function to handle the click event on the **Send** button in the Chat page.</span></span>

> [!NOTE]
> <span data-ttu-id="5b93b-207">Essa abordagem garante que a conexão seja estabelecida antes de executa o manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="5b93b-207">This approach ensures that the connection is established before the event handler executes.</span></span>


[!code-javascript[Main](tutorial-getting-started-with-signalr-and-mvc-4/samples/sample8.js)]

<a id="next"></a>

## <a name="next-steps"></a><span data-ttu-id="5b93b-208">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5b93b-208">Next Steps</span></span>

<span data-ttu-id="5b93b-209">Você aprendeu SignalR é uma estrutura para criar aplicativos web em tempo real.</span><span class="sxs-lookup"><span data-stu-id="5b93b-209">You learned that SignalR is a framework for building real-time web applications.</span></span> <span data-ttu-id="5b93b-210">Você também aprendeu diversas tarefas de desenvolvimento SignalR: como adicionar SignalR para um aplicativo ASP.NET, como criar uma classe de hub e como enviar e receber mensagens do hub.</span><span class="sxs-lookup"><span data-stu-id="5b93b-210">You also learned several SignalR development tasks: how to add SignalR to an ASP.NET application, how to create a hub class, and how to send and receive messages from the hub.</span></span>

<span data-ttu-id="5b93b-211">Para saber mais avançados conceitos de desenvolvimentos SignalR, visite os seguintes sites para SignalR código-fonte e recursos:</span><span class="sxs-lookup"><span data-stu-id="5b93b-211">To learn more advanced SignalR developments concepts, visit the following sites for SignalR source code and resources :</span></span>

- [<span data-ttu-id="5b93b-212">Projeto de SignalR</span><span class="sxs-lookup"><span data-stu-id="5b93b-212">SignalR Project</span></span>](http://signalr.net)
- [<span data-ttu-id="5b93b-213">SignalR Github e exemplos</span><span class="sxs-lookup"><span data-stu-id="5b93b-213">SignalR Github and Samples</span></span>](https://github.com/SignalR/SignalR)
- [<span data-ttu-id="5b93b-214">Wiki do SignalR</span><span class="sxs-lookup"><span data-stu-id="5b93b-214">SignalR Wiki</span></span>](https://github.com/SignalR/SignalR/wiki)