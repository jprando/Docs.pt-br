---
uid: signalr/overview/guide-to-the-api/hubs-api-guide-net-client
title: Guia de API de Hubs de SignalR do ASP.NET - cliente .NET (c#) | Microsoft Docs
author: pfletcher
description: "Este documento fornece uma introdução ao uso da API de Hubs de SignalR versão 2 em clientes .NET, como o armazenamento do Windows (WinRT), WPF, Silverlight e contras..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 06/10/2014
ms.topic: article
ms.assetid: 6d02d9f7-94e5-4140-9f51-5a6040f274f6
ms.technology: dotnet-signalr
ms.prod: .net-framework
msc.legacyurl: /signalr/overview/guide-to-the-api/hubs-api-guide-net-client
msc.type: authoredcontent
ms.openlocfilehash: a03c8c42622a768d706acf5ac1f23b37a830d426
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2017
---
<a name="aspnet-signalr-hubs-api-guide---net-client-c"></a><span data-ttu-id="19610-103">Guia de API de Hubs de SignalR do ASP.NET - cliente .NET (c#)</span><span class="sxs-lookup"><span data-stu-id="19610-103">ASP.NET SignalR Hubs API Guide - .NET Client (C#)</span></span>
====================
<span data-ttu-id="19610-104">por [Patrick Fletcher](https://github.com/pfletcher), [Tom Dykstra](https://github.com/tdykstra)</span><span class="sxs-lookup"><span data-stu-id="19610-104">by [Patrick Fletcher](https://github.com/pfletcher), [Tom Dykstra](https://github.com/tdykstra)</span></span>

> <span data-ttu-id="19610-105">Este documento fornece uma introdução ao uso da API de Hubs de SignalR versão 2 em clientes do .NET, como aplicativos de console, WPF, Silverlight e da Windows Store (WinRT).</span><span class="sxs-lookup"><span data-stu-id="19610-105">This document provides an introduction to using the Hubs API for SignalR version 2 in .NET clients, such as Windows Store (WinRT), WPF, Silverlight, and console applications.</span></span>
> 
> <span data-ttu-id="19610-106">A API de Hubs de SignalR permite fazer chamadas de procedimento remoto (RPCs) de um servidor para clientes conectados e de clientes para o servidor.</span><span class="sxs-lookup"><span data-stu-id="19610-106">The SignalR Hubs API enables you to make remote procedure calls (RPCs) from a server to connected clients and from clients to the server.</span></span> <span data-ttu-id="19610-107">No código do servidor, você define métodos que podem ser chamados por clientes e chamar os métodos que são executados no cliente.</span><span class="sxs-lookup"><span data-stu-id="19610-107">In server code, you define methods that can be called by clients, and you call methods that run on the client.</span></span> <span data-ttu-id="19610-108">No código do cliente, você define métodos que podem ser chamados do servidor e chamar os métodos que são executados no servidor.</span><span class="sxs-lookup"><span data-stu-id="19610-108">In client code, you define methods that can be called from the server, and you call methods that run on the server.</span></span> <span data-ttu-id="19610-109">SignalR cuida de todos os detalhes do cliente para servidor para você.</span><span class="sxs-lookup"><span data-stu-id="19610-109">SignalR takes care of all of the client-to-server plumbing for you.</span></span>
> 
> <span data-ttu-id="19610-110">O SignalR também oferece uma API de nível inferior chamada conexões persistentes.</span><span class="sxs-lookup"><span data-stu-id="19610-110">SignalR also offers a lower-level API called Persistent Connections.</span></span> <span data-ttu-id="19610-111">Para obter uma introdução para o SignalR, Hubs e conexões persistentes, ou para um tutorial que mostra como criar um aplicativo SignalR completo, consulte [SignalR - Introdução](../getting-started/index.md).</span><span class="sxs-lookup"><span data-stu-id="19610-111">For an introduction to SignalR, Hubs, and Persistent Connections, or for a tutorial that shows how to build a complete SignalR application, see [SignalR - Getting Started](../getting-started/index.md).</span></span>
> 
> ## <a name="software-versions-used-in-this-topic"></a><span data-ttu-id="19610-112">Versões de software usadas neste tópico</span><span class="sxs-lookup"><span data-stu-id="19610-112">Software versions used in this topic</span></span>
> 
> 
> - [<span data-ttu-id="19610-113">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="19610-113">Visual Studio 2013</span></span>](https://www.microsoft.com/visualstudio/eng/2013-downloads)
> - <span data-ttu-id="19610-114">.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="19610-114">.NET 4.5</span></span>
> - <span data-ttu-id="19610-115">SignalR versão 2</span><span class="sxs-lookup"><span data-stu-id="19610-115">SignalR version 2</span></span>
>   
> 
> 
> ## <a name="previous-versions-of-this-topic"></a><span data-ttu-id="19610-116">Versões anteriores deste tópico</span><span class="sxs-lookup"><span data-stu-id="19610-116">Previous versions of this topic</span></span>
> 
> <span data-ttu-id="19610-117">Para obter informações sobre versões anteriores do SignalR, consulte [versões mais antigas do SignalR](../older-versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="19610-117">For information about earlier versions of SignalR, see [SignalR Older Versions](../older-versions/index.md).</span></span>
> 
> ## <a name="questions-and-comments"></a><span data-ttu-id="19610-118">Perguntas e comentários</span><span class="sxs-lookup"><span data-stu-id="19610-118">Questions and comments</span></span>
> 
> <span data-ttu-id="19610-119">Deixe comentários em como você gostou neste tutorial e o que podemos melhorar nos comentários na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="19610-119">Please leave feedback on how you liked this tutorial and what we could improve in the comments at the bottom of the page.</span></span> <span data-ttu-id="19610-120">Se você tiver dúvidas que não estão diretamente relacionadas ao tutorial, você poderá postá-los para o [ASP.NET SignalR fórum](https://forums.asp.net/1254.aspx/1?ASP+NET+SignalR) ou [StackOverflow.com](http://stackoverflow.com/).</span><span class="sxs-lookup"><span data-stu-id="19610-120">If you have questions that are not directly related to the tutorial, you can post them to the [ASP.NET SignalR forum](https://forums.asp.net/1254.aspx/1?ASP+NET+SignalR) or [StackOverflow.com](http://stackoverflow.com/).</span></span>


## <a name="overview"></a><span data-ttu-id="19610-121">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="19610-121">Overview</span></span>

<span data-ttu-id="19610-122">Este documento contém as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="19610-122">This document contains the following sections:</span></span>

- [<span data-ttu-id="19610-123">Instalação do cliente</span><span class="sxs-lookup"><span data-stu-id="19610-123">Client Setup</span></span>](#clientsetup)
- [<span data-ttu-id="19610-124">Como estabelecer uma conexão</span><span class="sxs-lookup"><span data-stu-id="19610-124">How to establish a connection</span></span>](#establishconnection)

    - [<span data-ttu-id="19610-125">Conexões entre domínios de clientes do Silverlight</span><span class="sxs-lookup"><span data-stu-id="19610-125">Cross-domain connections from Silverlight clients</span></span>](#slcrossdomain)
- [<span data-ttu-id="19610-126">Como configurar a conexão</span><span class="sxs-lookup"><span data-stu-id="19610-126">How to configure the connection</span></span>](#configureconnection)

    - [<span data-ttu-id="19610-127">Como definir o número máximo de conexões simultâneas em clientes do WPF</span><span class="sxs-lookup"><span data-stu-id="19610-127">How to set the maximum number of concurrent connections in WPF clients</span></span>](#maxconnections)
    - [<span data-ttu-id="19610-128">Como especificar parâmetros de cadeia de caracteres de consulta</span><span class="sxs-lookup"><span data-stu-id="19610-128">How to specify query string parameters</span></span>](#querystring)
    - [<span data-ttu-id="19610-129">Como especificar o método de transporte</span><span class="sxs-lookup"><span data-stu-id="19610-129">How to specify the transport method</span></span>](#transport)
    - [<span data-ttu-id="19610-130">Como especificar cabeçalhos HTTP</span><span class="sxs-lookup"><span data-stu-id="19610-130">How to specify HTTP headers</span></span>](#httpheaders)
    - [<span data-ttu-id="19610-131">Como especificar os certificados de cliente</span><span class="sxs-lookup"><span data-stu-id="19610-131">How to specify client certificates</span></span>](#clientcertificate)
- [<span data-ttu-id="19610-132">Como criar o proxy do Hub</span><span class="sxs-lookup"><span data-stu-id="19610-132">How to create the Hub proxy</span></span>](#proxy)
- [<span data-ttu-id="19610-133">Como definir métodos no cliente que o servidor pode chamar</span><span class="sxs-lookup"><span data-stu-id="19610-133">How to define methods on the client that the server can call</span></span>](#callclient)

    - [<span data-ttu-id="19610-134">Métodos sem parâmetros</span><span class="sxs-lookup"><span data-stu-id="19610-134">Methods without parameters</span></span>](#clientmethodswithoutparms)
    - [<span data-ttu-id="19610-135">Métodos com parâmetros, especificando os tipos de parâmetro</span><span class="sxs-lookup"><span data-stu-id="19610-135">Methods with parameters, specifying parameter types</span></span>](#clientmethodswithparmtypes)
    - [<span data-ttu-id="19610-136">Métodos com parâmetros, especificando objetos dinâmicos para os parâmetros</span><span class="sxs-lookup"><span data-stu-id="19610-136">Methods with parameters, specifying dynamic objects for the parameters</span></span>](#clientmethodswithdynamparms)
    - [<span data-ttu-id="19610-137">Como remover um manipulador</span><span class="sxs-lookup"><span data-stu-id="19610-137">How to remove a handler</span></span>](#removehandler)
- [<span data-ttu-id="19610-138">Como chamar métodos do servidor do cliente</span><span class="sxs-lookup"><span data-stu-id="19610-138">How to call server methods from the client</span></span>](#callserver)
- [<span data-ttu-id="19610-139">Como manipular eventos de tempo de vida da conexão</span><span class="sxs-lookup"><span data-stu-id="19610-139">How to handle connection lifetime events</span></span>](#connectionlifetime)
- [<span data-ttu-id="19610-140">Como tratar erros</span><span class="sxs-lookup"><span data-stu-id="19610-140">How to handle errors</span></span>](#handleerrors)
- [<span data-ttu-id="19610-141">Como habilitar o registro de cliente</span><span class="sxs-lookup"><span data-stu-id="19610-141">How to enable client-side logging</span></span>](#logging)
- [<span data-ttu-id="19610-142">Exemplos de código de aplicativo de console para métodos de cliente que o servidor pode chamar, Silverlight e WPF</span><span class="sxs-lookup"><span data-stu-id="19610-142">WPF, Silverlight, and console application code samples for client methods that the server can call</span></span>](#wpfsl)

<span data-ttu-id="19610-143">Um exemplo .NET para projetos de cliente, consulte os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="19610-143">For a sample .NET client projects, see the following resources:</span></span>

- <span data-ttu-id="19610-144">[Gustavo armenta / SignalR exemplos](https://github.com/gustavo-armenta/SignalR-Samples) em GitHub.com (WinRT, Silverlight, exemplos de aplicativo de console).</span><span class="sxs-lookup"><span data-stu-id="19610-144">[gustavo-armenta / SignalR-Samples](https://github.com/gustavo-armenta/SignalR-Samples) on GitHub.com (WinRT, Silverlight, console app examples).</span></span>
- <span data-ttu-id="19610-145">[DamianEdwards / SignalR MoveShapeDemo / MoveShape.Desktop](https://github.com/DamianEdwards/SignalR-MoveShapeDemo/tree/master/MoveShape/MoveShape.Desktop) em GitHub.com (exemplo WPF).</span><span class="sxs-lookup"><span data-stu-id="19610-145">[DamianEdwards / SignalR-MoveShapeDemo / MoveShape.Desktop](https://github.com/DamianEdwards/SignalR-MoveShapeDemo/tree/master/MoveShape/MoveShape.Desktop) on GitHub.com (WPF example).</span></span>
- <span data-ttu-id="19610-146">[SignalR / Microsoft.AspNet.SignalR.Client.Samples](https://github.com/SignalR/SignalR/tree/master/samples/Microsoft.AspNet.SignalR.Client.Samples) em GitHub.com (exemplo de aplicativo de Console).</span><span class="sxs-lookup"><span data-stu-id="19610-146">[SignalR / Microsoft.AspNet.SignalR.Client.Samples](https://github.com/SignalR/SignalR/tree/master/samples/Microsoft.AspNet.SignalR.Client.Samples) on GitHub.com (Console app example).</span></span>

<span data-ttu-id="19610-147">Para obter a documentação sobre como programar o servidor ou os clientes JavaScript, consulte os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="19610-147">For documentation on how to program the server or JavaScript clients, see the following resources:</span></span>

- [<span data-ttu-id="19610-148">Guia de API de Hubs de SignalR - servidor</span><span class="sxs-lookup"><span data-stu-id="19610-148">SignalR Hubs API Guide - Server</span></span>](hubs-api-guide-server.md)
- [<span data-ttu-id="19610-149">Guia de API de Hubs de SignalR - cliente JavaScript</span><span class="sxs-lookup"><span data-stu-id="19610-149">SignalR Hubs API Guide - JavaScript Client</span></span>](hubs-api-guide-javascript-client.md)

<span data-ttu-id="19610-150">Links para tópicos de referência de API são para a versão do .NET 4.5 da API.</span><span class="sxs-lookup"><span data-stu-id="19610-150">Links to API Reference topics are to the .NET 4.5 version of the API.</span></span> <span data-ttu-id="19610-151">Se você estiver usando o .NET 4, consulte [a versão do .NET 4 dos tópicos da API](https://msdn.microsoft.com/en-us/library/jj891075(v=vs.100).aspx).</span><span class="sxs-lookup"><span data-stu-id="19610-151">If you're using .NET 4, see [the .NET 4 version of the API topics](https://msdn.microsoft.com/en-us/library/jj891075(v=vs.100).aspx).</span></span>

<a id="clientsetup"></a>

## <a name="client-setup"></a><span data-ttu-id="19610-152">Instalação do cliente</span><span class="sxs-lookup"><span data-stu-id="19610-152">Client setup</span></span>

<span data-ttu-id="19610-153">Instalar o [SignalR](http://nuget.org/packages/Microsoft.AspNet.SignalR.Client) pacote do NuGet (não o [SignalR](http://nuget.org/packages/microsoft.aspnet.signalr) pacote).</span><span class="sxs-lookup"><span data-stu-id="19610-153">Install the [Microsoft.AspNet.SignalR.Client](http://nuget.org/packages/Microsoft.AspNet.SignalR.Client) NuGet package (not the [Microsoft.AspNet.SignalR](http://nuget.org/packages/microsoft.aspnet.signalr) package).</span></span> <span data-ttu-id="19610-154">Este pacote suporta WinRT, Silverlight, WPF, aplicativo de console e os clientes do Windows Phone, para .NET 4 e o .NET 4.5.</span><span class="sxs-lookup"><span data-stu-id="19610-154">This package supports WinRT, Silverlight, WPF, console application, and Windows Phone clients, for both .NET 4 and .NET 4.5.</span></span>

<span data-ttu-id="19610-155">Se a versão do SignalR que têm o cliente é diferente da versão que você tem no servidor, SignalR geralmente é capaz de se adaptar à diferença.</span><span class="sxs-lookup"><span data-stu-id="19610-155">If the version of SignalR that you have on the client is different from the version that you have on the server, SignalR is often able to adapt to the difference.</span></span> <span data-ttu-id="19610-156">Por exemplo, um servidor que executa a versão 2 do SignalR suportará clientes que têm 1.1 instalado, bem como os clientes que têm a versão 2 instalado.</span><span class="sxs-lookup"><span data-stu-id="19610-156">For example, a server running SignalR version 2 will support clients that have 1.1.x installed as well as clients that have version 2 installed.</span></span> <span data-ttu-id="19610-157">Se a diferença entre a versão no servidor e a versão do cliente for muito grande, ou se o cliente for mais recente do que o servidor, SignalR lança um `InvalidOperationException` exceção quando o cliente tenta estabelecer uma conexão.</span><span class="sxs-lookup"><span data-stu-id="19610-157">If the difference between the version on the server and the version on the client is too great, or if the client is newer than the server, SignalR throws an `InvalidOperationException` exception when the client tries to establish a connection.</span></span> <span data-ttu-id="19610-158">A mensagem de erro é "`You are using a version of the client that isn't compatible with the server. Client version X.X, server version X.X`".</span><span class="sxs-lookup"><span data-stu-id="19610-158">The error message is "`You are using a version of the client that isn't compatible with the server. Client version X.X, server version X.X`".</span></span>

<a id="establishconnection"></a>

## <a name="how-to-establish-a-connection"></a><span data-ttu-id="19610-159">Como estabelecer uma conexão</span><span class="sxs-lookup"><span data-stu-id="19610-159">How to establish a connection</span></span>

<span data-ttu-id="19610-160">Antes de estabelecer uma conexão, você precisa criar um `HubConnection` de objeto e criar um proxy.</span><span class="sxs-lookup"><span data-stu-id="19610-160">Before you can establish a connection, you have to create a `HubConnection` object and create a proxy.</span></span> <span data-ttu-id="19610-161">Para estabelecer a conexão, chame o `Start` método sobre o `HubConnection` objeto.</span><span class="sxs-lookup"><span data-stu-id="19610-161">To establish the connection, call the `Start` method on the `HubConnection` object.</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample1.cs?highlight=1,4)]

> [!NOTE]
> <span data-ttu-id="19610-162">Para clientes JavaScript que você precisa registrar pelo menos um manipulador de eventos antes de chamar o `Start` método para estabelecer a conexão.</span><span class="sxs-lookup"><span data-stu-id="19610-162">For JavaScript clients you have to register at least one event handler before calling the `Start` method to establish the connection.</span></span> <span data-ttu-id="19610-163">Isso não é necessário para clientes do .NET.</span><span class="sxs-lookup"><span data-stu-id="19610-163">This is not necessary for .NET clients.</span></span> <span data-ttu-id="19610-164">Para clientes de JavaScript, o código de proxy gerado automaticamente cria proxies para todos os Hubs que existem no servidor e registrar um manipulador é como você indicar quais Hubs o cliente pretende usar.</span><span class="sxs-lookup"><span data-stu-id="19610-164">For JavaScript clients, the generated proxy code automatically creates proxies for all Hubs that exist on the server, and registering a handler is how you indicate which Hubs your client intends to use.</span></span> <span data-ttu-id="19610-165">Mas para um cliente .NET criar proxies Hub manualmente, para que o SignalR pressupõe que você usará qualquer Hub que você criar um proxy para.</span><span class="sxs-lookup"><span data-stu-id="19610-165">But for a .NET client you create Hub proxies manually, so SignalR assumes that you will be using any Hub that you create a proxy for.</span></span>


<span data-ttu-id="19610-166">O código de exemplo usa o padrão "/ signalr" URL para se conectar ao seu serviço SignalR.</span><span class="sxs-lookup"><span data-stu-id="19610-166">The sample code uses the default "/signalr" URL to connect to your SignalR service.</span></span> <span data-ttu-id="19610-167">Para obter informações sobre como especificar uma URL base diferente, consulte [ASP.NET SignalR Hubs API guia - Server - a URL /signalr](hubs-api-guide-server.md#signalrurl).</span><span class="sxs-lookup"><span data-stu-id="19610-167">For information about how to specify a different base URL, see [ASP.NET SignalR Hubs API Guide - Server - The /signalr URL](hubs-api-guide-server.md#signalrurl).</span></span>

<span data-ttu-id="19610-168">O `Start` método é executado de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="19610-168">The `Start` method executes asynchronously.</span></span> <span data-ttu-id="19610-169">Para certificar-se de que as linhas subsequentes de código não executar até depois que a conexão é estabelecida, use `await` em um método assíncrono do ASP.NET 4.5 ou `.Wait()` em um método síncrono.</span><span class="sxs-lookup"><span data-stu-id="19610-169">To make sure that subsequent lines of code don't execute until after the connection is established, use `await` in an ASP.NET 4.5 asynchronous method or `.Wait()` in a synchronous method.</span></span> <span data-ttu-id="19610-170">Não use `.Wait()` em um cliente do WinRT.</span><span class="sxs-lookup"><span data-stu-id="19610-170">Don't use `.Wait()` in a WinRT client.</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample2.cs?highlight=1)]

[!code-css[Main](hubs-api-guide-net-client/samples/sample3.css?highlight=1)]

<a id="slcrossdomain"></a>

### <a name="cross-domain-connections-from-silverlight-clients"></a><span data-ttu-id="19610-171">Conexões entre domínios de clientes do Silverlight</span><span class="sxs-lookup"><span data-stu-id="19610-171">Cross-domain connections from Silverlight clients</span></span>

<span data-ttu-id="19610-172">Para obter informações sobre como habilitar conexões entre domínios de clientes do Silverlight, consulte [tornando um serviço disponível através dos limites do domínio](https://msdn.microsoft.com/en-us/library/cc197955(v=vs.95).aspx).</span><span class="sxs-lookup"><span data-stu-id="19610-172">For information about how to enable cross-domain connections from Silverlight clients, see [Making a Service Available Across Domain Boundaries](https://msdn.microsoft.com/en-us/library/cc197955(v=vs.95).aspx).</span></span>

<a id="configureconnection"></a>

## <a name="how-to-configure-the-connection"></a><span data-ttu-id="19610-173">Como configurar a conexão</span><span class="sxs-lookup"><span data-stu-id="19610-173">How to configure the connection</span></span>

<span data-ttu-id="19610-174">Antes de estabelecer uma conexão, você pode especificar qualquer uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="19610-174">Before you establish a connection, you can specify any of the following options:</span></span>

- <span data-ttu-id="19610-175">Limite de conexões simultâneas.</span><span class="sxs-lookup"><span data-stu-id="19610-175">Concurrent connections limit.</span></span>
- <span data-ttu-id="19610-176">Parâmetros de cadeia de caracteres de consulta.</span><span class="sxs-lookup"><span data-stu-id="19610-176">Query string parameters.</span></span>
- <span data-ttu-id="19610-177">O método de transporte.</span><span class="sxs-lookup"><span data-stu-id="19610-177">The transport method.</span></span>
- <span data-ttu-id="19610-178">Cabeçalhos HTTP.</span><span class="sxs-lookup"><span data-stu-id="19610-178">HTTP headers.</span></span>
- <span data-ttu-id="19610-179">Certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="19610-179">Client certificates.</span></span>

<a id="maxconnections"></a>

### <a name="how-to-set-the-maximum-number-of-concurrent-connections-in-wpf-clients"></a><span data-ttu-id="19610-180">Como definir o número máximo de conexões simultâneas em clientes do WPF</span><span class="sxs-lookup"><span data-stu-id="19610-180">How to set the maximum number of concurrent connections in WPF clients</span></span>

<span data-ttu-id="19610-181">Em clientes do WPF, você talvez precise aumentar o número máximo de conexões simultâneas de seu valor padrão de 2.</span><span class="sxs-lookup"><span data-stu-id="19610-181">In WPF clients, you might have to increase the maximum number of concurrent connections from its default value of 2.</span></span> <span data-ttu-id="19610-182">O valor recomendado é 10.</span><span class="sxs-lookup"><span data-stu-id="19610-182">The recommended value is 10.</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample4.cs?highlight=4)]

<span data-ttu-id="19610-183">Para obter mais informações, consulte [ServicePointManager.DefaultConnectionLimit](https://msdn.microsoft.com/en-us/library/system.net.servicepointmanager.defaultconnectionlimit.aspx).</span><span class="sxs-lookup"><span data-stu-id="19610-183">For more information, see [ServicePointManager.DefaultConnectionLimit](https://msdn.microsoft.com/en-us/library/system.net.servicepointmanager.defaultconnectionlimit.aspx).</span></span>

<a id="querystring"></a>

### <a name="how-to-specify-query-string-parameters"></a><span data-ttu-id="19610-184">Como especificar parâmetros de cadeia de caracteres de consulta</span><span class="sxs-lookup"><span data-stu-id="19610-184">How to specify query string parameters</span></span>

<span data-ttu-id="19610-185">Se você deseja enviar dados para o servidor quando o cliente se conecta, você pode adicionar parâmetros de cadeia de caracteres de consulta para o objeto de conexão.</span><span class="sxs-lookup"><span data-stu-id="19610-185">If you want to send data to the server when the client connects, you can add query string parameters to the connection object.</span></span> <span data-ttu-id="19610-186">O exemplo a seguir mostra como definir um parâmetro de cadeia de caracteres de consulta no código do cliente.</span><span class="sxs-lookup"><span data-stu-id="19610-186">The following example shows how to set a query string parameter in client code.</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample5.cs)]

<span data-ttu-id="19610-187">O exemplo a seguir mostra como ler um parâmetro de cadeia de caracteres de consulta no código do servidor.</span><span class="sxs-lookup"><span data-stu-id="19610-187">The following example shows how to read a query string parameter in server code.</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample6.cs?highlight=5)]

<a id="transport"></a>

### <a name="how-to-specify-the-transport-method"></a><span data-ttu-id="19610-188">Como especificar o método de transporte</span><span class="sxs-lookup"><span data-stu-id="19610-188">How to specify the transport method</span></span>

<span data-ttu-id="19610-189">Como parte do processo de conexão, um cliente SignalR normalmente negocia com o servidor para determinar o melhor transporte com suporte pelo servidor e cliente.</span><span class="sxs-lookup"><span data-stu-id="19610-189">As part of the process of connecting, a SignalR client normally negotiates with the server to determine the best transport that is supported by both server and client.</span></span> <span data-ttu-id="19610-190">Se você já souber qual transporte você deseja usar, você pode ignorar esse processo de negociação.</span><span class="sxs-lookup"><span data-stu-id="19610-190">If you already know which transport you want to use, you can bypass this negotiation process.</span></span> <span data-ttu-id="19610-191">Para especificar o método de transporte, passe um objeto de transporte para o método Start.</span><span class="sxs-lookup"><span data-stu-id="19610-191">To specify the transport method, pass in a transport object to the Start method.</span></span> <span data-ttu-id="19610-192">O exemplo a seguir mostra como especificar o método de transporte no código do cliente.</span><span class="sxs-lookup"><span data-stu-id="19610-192">The following example shows how to specify the transport method in client code.</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample7.cs?highlight=4)]

<span data-ttu-id="19610-193">O [Transports](https://msdn.microsoft.com/en-us/library/jj918090(v=vs.111).aspx) namespace inclui as seguintes classes que você pode usar para especificar o transporte.</span><span class="sxs-lookup"><span data-stu-id="19610-193">The [Microsoft.AspNet.SignalR.Client.Transports](https://msdn.microsoft.com/en-us/library/jj918090(v=vs.111).aspx) namespace includes the following classes that you can use to specify the transport.</span></span>

- <span data-ttu-id="19610-194">[LongPollingTransport](https://msdn.microsoft.com/en-us/library/microsoft.aspnet.signalr.client.transports.longpollingtransport(v=vs.111).aspx)</span><span class="sxs-lookup"><span data-stu-id="19610-194">[LongPollingTransport](https://msdn.microsoft.com/en-us/library/microsoft.aspnet.signalr.client.transports.longpollingtransport(v=vs.111).aspx)</span></span>
- <span data-ttu-id="19610-195">[ServerSentEventsTransport](https://msdn.microsoft.com/en-us/library/microsoft.aspnet.signalr.client.transports.serversenteventstransport(v=vs.111).aspx)</span><span class="sxs-lookup"><span data-stu-id="19610-195">[ServerSentEventsTransport](https://msdn.microsoft.com/en-us/library/microsoft.aspnet.signalr.client.transports.serversenteventstransport(v=vs.111).aspx)</span></span>
- <span data-ttu-id="19610-196">[WebSocketTransport](https://msdn.microsoft.com/en-us/library/microsoft.aspnet.signalr.client.transports.websockettransport(v=vs.111).aspx) (disponível somente quando o servidor e o cliente usam o .NET 4.5).</span><span class="sxs-lookup"><span data-stu-id="19610-196">[WebSocketTransport](https://msdn.microsoft.com/en-us/library/microsoft.aspnet.signalr.client.transports.websockettransport(v=vs.111).aspx) (Available only when both server and client use .NET 4.5.)</span></span>
- <span data-ttu-id="19610-197">[AutoTransport](https://msdn.microsoft.com/en-us/library/microsoft.aspnet.signalr.client.transports.autotransport(v=vs.111).aspx) (escolhe automaticamente o melhor transporte com suporte pelo cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="19610-197">[AutoTransport](https://msdn.microsoft.com/en-us/library/microsoft.aspnet.signalr.client.transports.autotransport(v=vs.111).aspx) (Automatically chooses the best transport that is supported by both the client and the server.</span></span> <span data-ttu-id="19610-198">Este é o transporte padrão.</span><span class="sxs-lookup"><span data-stu-id="19610-198">This is the default transport.</span></span> <span data-ttu-id="19610-199">Transmitindo-para o `Start` método tem o mesmo efeito que não está transmitindo nada.)</span><span class="sxs-lookup"><span data-stu-id="19610-199">Passing this in to the `Start` method has the same effect as not passing in anything.)</span></span>

<span data-ttu-id="19610-200">O transporte ForeverFrame não está incluído nesta lista porque ele é usado somente por navegadores.</span><span class="sxs-lookup"><span data-stu-id="19610-200">The ForeverFrame transport is not included in this list because it is used only by browsers.</span></span>

<span data-ttu-id="19610-201">Para obter informações sobre como verificar o método de transporte no código do servidor, consulte [guia de API de Hubs do ASP.NET SignalR - Server - como obter informações sobre o cliente da propriedade de contexto](hubs-api-guide-server.md#contextproperty).</span><span class="sxs-lookup"><span data-stu-id="19610-201">For information about how to check the transport method in server code, see [ASP.NET SignalR Hubs API Guide - Server - How to get information about the client from the Context property](hubs-api-guide-server.md#contextproperty).</span></span> <span data-ttu-id="19610-202">Para obter mais informações sobre os transportes e restaurações, consulte [Introdução ao SignalR - transportes e Fallbacks](../getting-started/introduction-to-signalr.md#transports).</span><span class="sxs-lookup"><span data-stu-id="19610-202">For more information about transports and fallbacks, see [Introduction to SignalR - Transports and Fallbacks](../getting-started/introduction-to-signalr.md#transports).</span></span>

<a id="httpheaders"></a>

### <a name="how-to-specify-http-headers"></a><span data-ttu-id="19610-203">Como especificar cabeçalhos HTTP</span><span class="sxs-lookup"><span data-stu-id="19610-203">How to specify HTTP headers</span></span>

<span data-ttu-id="19610-204">Para definir cabeçalhos HTTP, use o `Headers` propriedade no objeto de conexão.</span><span class="sxs-lookup"><span data-stu-id="19610-204">To set HTTP headers, use the `Headers` property on the connection object.</span></span> <span data-ttu-id="19610-205">O exemplo a seguir mostra como adicionar um cabeçalho HTTP.</span><span class="sxs-lookup"><span data-stu-id="19610-205">The following example shows how to add an HTTP header.</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample8.cs?highlight=2)]

<a id="clientcertificate"></a>

### <a name="how-to-specify-client-certificates"></a><span data-ttu-id="19610-206">Como especificar os certificados de cliente</span><span class="sxs-lookup"><span data-stu-id="19610-206">How to specify client certificates</span></span>

<span data-ttu-id="19610-207">Para adicionar certificados de cliente, use o `AddClientCertificate` método no objeto de conexão.</span><span class="sxs-lookup"><span data-stu-id="19610-207">To add client certificates, use the `AddClientCertificate` method on the connection object.</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample9.cs?highlight=2)]

<a id="proxy"></a>

## <a name="how-to-create-the-hub-proxy"></a><span data-ttu-id="19610-208">Como criar o proxy do Hub</span><span class="sxs-lookup"><span data-stu-id="19610-208">How to create the Hub proxy</span></span>

<span data-ttu-id="19610-209">Para definir métodos no cliente que pode chamar um Hub do servidor e para invocar métodos em um Hub no servidor, crie um proxy para o Hub chamando `CreateHubProxy` no objeto de conexão.</span><span class="sxs-lookup"><span data-stu-id="19610-209">In order to define methods on the client that a Hub can call from the server, and to invoke methods on a Hub at the server, create a proxy for the Hub by calling `CreateHubProxy` on the connection object.</span></span> <span data-ttu-id="19610-210">A cadeia de caracteres para o qual você passar `CreateHubProxy` é o nome da classe do Hub ou o nome especificado pelo `HubName` atributo se estava sendo usado no servidor.</span><span class="sxs-lookup"><span data-stu-id="19610-210">The string you pass in to `CreateHubProxy` is the name of your Hub class, or the name specified by the `HubName` attribute if one was used on the server.</span></span> <span data-ttu-id="19610-211">Correspondência de nome diferencia maiusculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="19610-211">Name matching is case-insensitive.</span></span>

<span data-ttu-id="19610-212">**Classe de Hub no servidor**</span><span class="sxs-lookup"><span data-stu-id="19610-212">**Hub class on server**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample10.cs?highlight=1)]

<span data-ttu-id="19610-213">**Criar proxy de cliente para a classe de Hub**</span><span class="sxs-lookup"><span data-stu-id="19610-213">**Create client proxy for the Hub class**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample11.cs?highlight=2)]

<span data-ttu-id="19610-214">Se você decora sua classe de Hub com um `HubName` de atributo, use esse nome.</span><span class="sxs-lookup"><span data-stu-id="19610-214">If you decorate your Hub class with a `HubName` attribute, use that name.</span></span>

<span data-ttu-id="19610-215">**Classe de Hub no servidor**</span><span class="sxs-lookup"><span data-stu-id="19610-215">**Hub class on server**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample12.cs)]

<span data-ttu-id="19610-216">**Criar proxy de cliente para a classe de Hub**</span><span class="sxs-lookup"><span data-stu-id="19610-216">**Create client proxy for the Hub class**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample13.cs?highlight=2)]

<span data-ttu-id="19610-217">Se você chamar `HubConnection.CreateHubProxy` várias vezes com o mesmo `hubName`, você obtém a mesma em cache `IHubProxy` objeto.</span><span class="sxs-lookup"><span data-stu-id="19610-217">If you call `HubConnection.CreateHubProxy` multiple times with the same `hubName`, you get the same cached `IHubProxy` object.</span></span>

<a id="callclient"></a>

## <a name="how-to-define-methods-on-the-client-that-the-server-can-call"></a><span data-ttu-id="19610-218">Como definir métodos no cliente que o servidor pode chamar</span><span class="sxs-lookup"><span data-stu-id="19610-218">How to define methods on the client that the server can call</span></span>

<span data-ttu-id="19610-219">Para definir um método que o servidor pode chamar, use o proxy `On` método para registrar um manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="19610-219">To define a method that the server can call, use the proxy's `On` method to register an event handler.</span></span>

<span data-ttu-id="19610-220">Correspondência de nome do método diferencia maiusculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="19610-220">Method name matching is case-insensitive.</span></span> <span data-ttu-id="19610-221">Por exemplo, `Clients.All.UpdateStockPrice` no servidor executará `updateStockPrice`, `updatestockprice`, ou `UpdateStockPrice` no cliente.</span><span class="sxs-lookup"><span data-stu-id="19610-221">For example, `Clients.All.UpdateStockPrice` on the server will execute `updateStockPrice`, `updatestockprice`, or `UpdateStockPrice` on the client.</span></span>

<span data-ttu-id="19610-222">Plataformas de cliente diferentes têm requisitos diferentes como escrever o código do método para atualizar a interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="19610-222">Different client platforms have different requirements for how you write method code to update the UI.</span></span> <span data-ttu-id="19610-223">Os exemplos mostrados são para clientes do WinRT (Windows Store .NET).</span><span class="sxs-lookup"><span data-stu-id="19610-223">The examples shown are for WinRT (Windows Store .NET) clients.</span></span> <span data-ttu-id="19610-224">WPF, Silverlight e exemplos de aplicativos de console são fornecidos nos [uma seção separada neste tópico](#wpfsl).</span><span class="sxs-lookup"><span data-stu-id="19610-224">WPF, Silverlight, and console application examples are provided in [a separate section later in this topic](#wpfsl).</span></span>

<a id="clientmethodswithoutparms"></a>

### <a name="methods-without-parameters"></a><span data-ttu-id="19610-225">Métodos sem parâmetros</span><span class="sxs-lookup"><span data-stu-id="19610-225">Methods without parameters</span></span>

<span data-ttu-id="19610-226">Se o método que você está tratando não tiver parâmetros, use a sobrecarga de não-genérica do `On` método:</span><span class="sxs-lookup"><span data-stu-id="19610-226">If the method you're handling does not have parameters, use the non-generic overload of the `On` method:</span></span>

<span data-ttu-id="19610-227">**Código do servidor chamando o método de cliente sem parâmetros**</span><span class="sxs-lookup"><span data-stu-id="19610-227">**Server code calling client method without parameters**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample14.cs?highlight=5)]

<span data-ttu-id="19610-228">**Código do cliente do WinRT para método de chamada do servidor sem parâmetros ([consulte WPF e Silverlight exemplos mais adiante neste tópico](#wpfsl))**</span><span class="sxs-lookup"><span data-stu-id="19610-228">**WinRT Client code for method called from server without parameters ([see WPF and Silverlight examples later in this topic](#wpfsl))**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample15.cs)]

<a id="clientmethodswithparmtypes"></a>

### <a name="methods-with-parameters-specifying-the-parameter-types"></a><span data-ttu-id="19610-229">Métodos com parâmetros, especificando os tipos de parâmetro</span><span class="sxs-lookup"><span data-stu-id="19610-229">Methods with parameters, specifying the parameter types</span></span>

<span data-ttu-id="19610-230">Se o método que você está lidando com tiver parâmetros, especifique os tipos dos parâmetros como os tipos genéricos do `On` método.</span><span class="sxs-lookup"><span data-stu-id="19610-230">If the method you're handling has parameters, specify the types of the parameters as the generic types of the `On` method.</span></span> <span data-ttu-id="19610-231">Há sobrecargas genéricas do `On` método para permitir que você especifique parâmetros até 8 (4 no Windows Phone 7).</span><span class="sxs-lookup"><span data-stu-id="19610-231">There are generic overloads of the `On` method to enable you to specify up to 8 parameters (4 on Windows Phone 7).</span></span> <span data-ttu-id="19610-232">No exemplo a seguir, um parâmetro é enviado para o `UpdateStockPrice` método.</span><span class="sxs-lookup"><span data-stu-id="19610-232">In the following example, one parameter is sent to the `UpdateStockPrice` method.</span></span>

<span data-ttu-id="19610-233">**Chamar o método de cliente com um parâmetro de código do servidor**</span><span class="sxs-lookup"><span data-stu-id="19610-233">**Server code calling client method with a parameter**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample16.cs?highlight=3)]

<span data-ttu-id="19610-234">**A classe de estoque usada para o parâmetro**</span><span class="sxs-lookup"><span data-stu-id="19610-234">**The Stock class used for the parameter**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample17.cs)]

<span data-ttu-id="19610-235">**Código do cliente do WinRT para um método de chamada do servidor com um parâmetro ([consulte WPF e Silverlight exemplos mais adiante neste tópico](#wpfsl))**</span><span class="sxs-lookup"><span data-stu-id="19610-235">**WinRT Client code for a method called from server with a parameter ([see WPF and Silverlight examples later in this topic](#wpfsl))**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample18.cs?highlight=1,5)]

<a id="clientmethodswithdynamparms"></a>

### <a name="methods-with-parameters-specifying-dynamic-objects-for-the-parameters"></a><span data-ttu-id="19610-236">Métodos com parâmetros, especificando objetos dinâmicos para os parâmetros</span><span class="sxs-lookup"><span data-stu-id="19610-236">Methods with parameters, specifying dynamic objects for the parameters</span></span>

<span data-ttu-id="19610-237">Como uma alternativa para especificar parâmetros como tipos genéricos do `On` método, você pode especificar parâmetros como objetos dinâmicos:</span><span class="sxs-lookup"><span data-stu-id="19610-237">As an alternative to specifying parameters as generic types of the `On` method, you can specify parameters as dynamic objects:</span></span>

<span data-ttu-id="19610-238">**Chamar o método de cliente com um parâmetro de código do servidor**</span><span class="sxs-lookup"><span data-stu-id="19610-238">**Server code calling client method with a parameter**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample19.cs?highlight=3)]

<span data-ttu-id="19610-239">**A classe de estoque usada para o parâmetro**</span><span class="sxs-lookup"><span data-stu-id="19610-239">**The Stock class used for the parameter**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample20.cs)]

<span data-ttu-id="19610-240">**Código do cliente do WinRT para um método chamado a partir do servidor com um parâmetro, usando um objeto dinâmico para o parâmetro ([consulte WPF e Silverlight exemplos mais adiante neste tópico](#wpfsl))**</span><span class="sxs-lookup"><span data-stu-id="19610-240">**WinRT Client code for a method called from server with a parameter, using a dynamic object for the parameter ([see WPF and Silverlight examples later in this topic](#wpfsl))**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample21.cs?highlight=1,5)]

<a id="removehandler"></a>

### <a name="how-to-remove-a-handler"></a><span data-ttu-id="19610-241">Como remover um manipulador</span><span class="sxs-lookup"><span data-stu-id="19610-241">How to remove a handler</span></span>

<span data-ttu-id="19610-242">Para remover um manipulador, chame seu `Dispose` método.</span><span class="sxs-lookup"><span data-stu-id="19610-242">To remove a handler, call its `Dispose` method.</span></span>

<span data-ttu-id="19610-243">**Código do cliente para um método chamado a partir do servidor**</span><span class="sxs-lookup"><span data-stu-id="19610-243">**Client code for a method called from server**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample22.cs?highlight=1)]

<span data-ttu-id="19610-244">**Código do cliente para remover o manipulador**</span><span class="sxs-lookup"><span data-stu-id="19610-244">**Client code to remove the handler**</span></span>

[!code-css[Main](hubs-api-guide-net-client/samples/sample23.css?highlight=1)]

<a id="callserver"></a>

## <a name="how-to-call-server-methods-from-the-client"></a><span data-ttu-id="19610-245">Como chamar métodos do servidor do cliente</span><span class="sxs-lookup"><span data-stu-id="19610-245">How to call server methods from the client</span></span>

<span data-ttu-id="19610-246">Para chamar um método no servidor, use o `Invoke` método no proxy do Hub.</span><span class="sxs-lookup"><span data-stu-id="19610-246">To call a method on the server, use the `Invoke` method on the Hub proxy.</span></span>

<span data-ttu-id="19610-247">Se o método de servidor não tem valor retornado, use a sobrecarga de não-genérica do `Invoke` método.</span><span class="sxs-lookup"><span data-stu-id="19610-247">If the server method has no return value, use the non-generic overload of the `Invoke` method.</span></span>

<span data-ttu-id="19610-248">**Código do servidor para um método que não tem nenhum valor de retorno**</span><span class="sxs-lookup"><span data-stu-id="19610-248">**Server code for a method that has no return value**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample24.cs?highlight=3)]

<span data-ttu-id="19610-249">**Código do cliente chamar um método que não tem nenhum valor de retorno**</span><span class="sxs-lookup"><span data-stu-id="19610-249">**Client code calling a method that has no return value**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample25.cs?highlight=1)]

<span data-ttu-id="19610-250">Se o método de servidor tem um valor de retorno, especifique o tipo de retorno do tipo genérico do `Invoke` método.</span><span class="sxs-lookup"><span data-stu-id="19610-250">If the server method has a return value, specify the return type as the generic type of the `Invoke` method.</span></span>

<span data-ttu-id="19610-251">**Código do servidor para um método que tem um valor de retorno e usa um parâmetro de tipo complexo**</span><span class="sxs-lookup"><span data-stu-id="19610-251">**Server code for a method that has a return value and takes a complex type parameter**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample26.cs?highlight=1)]

<span data-ttu-id="19610-252">**A classe de estoque usada para o parâmetro e valor de retorno**</span><span class="sxs-lookup"><span data-stu-id="19610-252">**The Stock class used for the parameter and return value**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample27.cs)]

<span data-ttu-id="19610-253">**Código do cliente chamar um método que tem um valor de retorno e usa um parâmetro de tipo complexo, em um método assíncrono de ASP.NET 4.5**</span><span class="sxs-lookup"><span data-stu-id="19610-253">**Client code calling a method that has a return value and takes a complex type parameter, in an ASP.NET 4.5 async method**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample28.cs?highlight=1-2)]

<span data-ttu-id="19610-254">**Código do cliente chamar um método que tem um valor de retorno e usa um parâmetro de tipo complexo, em um método síncrono**</span><span class="sxs-lookup"><span data-stu-id="19610-254">**Client code calling a method that has a return value and takes a complex type parameter, in a synchronous method**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample29.cs?highlight=1-2)]

<span data-ttu-id="19610-255">O `Invoke` método executa de forma assíncrona e retorna um `Task` objeto.</span><span class="sxs-lookup"><span data-stu-id="19610-255">The `Invoke` method executes asynchronously and returns a `Task` object.</span></span> <span data-ttu-id="19610-256">Se você não especificar `await` ou `.Wait()`, a próxima linha de código será executado antes do método que você chamar concluiu a execução.</span><span class="sxs-lookup"><span data-stu-id="19610-256">If you don't specify `await` or `.Wait()`, the next line of code will execute before the method that you invoke has finished executing.</span></span>

<a id="connectionlifetime"></a>

## <a name="how-to-handle-connection-lifetime-events"></a><span data-ttu-id="19610-257">Como manipular eventos de tempo de vida da conexão</span><span class="sxs-lookup"><span data-stu-id="19610-257">How to handle connection lifetime events</span></span>

<span data-ttu-id="19610-258">O SignalR fornece a seguinte conexão eventos de tempo de vida que você pode manipular:</span><span class="sxs-lookup"><span data-stu-id="19610-258">SignalR provides the following connection lifetime events that you can handle:</span></span>

- <span data-ttu-id="19610-259">`Received`: Gerado quando nenhum dado é recebido na conexão.</span><span class="sxs-lookup"><span data-stu-id="19610-259">`Received`: Raised when any data is received on the connection.</span></span> <span data-ttu-id="19610-260">Fornece os dados recebidos.</span><span class="sxs-lookup"><span data-stu-id="19610-260">Provides the received data.</span></span>
- <span data-ttu-id="19610-261">`ConnectionSlow`: Gerado quando o cliente detecta uma conexão lenta ou remoção com frequência.</span><span class="sxs-lookup"><span data-stu-id="19610-261">`ConnectionSlow`: Raised when the client detects a slow or frequently dropping connection.</span></span>
- <span data-ttu-id="19610-262">`Reconnecting`: Gerado quando o transporte subjacente inicia a reconexão.</span><span class="sxs-lookup"><span data-stu-id="19610-262">`Reconnecting`: Raised when the underlying transport begins reconnecting.</span></span>
- <span data-ttu-id="19610-263">`Reconnected`: Gerado quando o transporte subjacente foi reconectada.</span><span class="sxs-lookup"><span data-stu-id="19610-263">`Reconnected`: Raised when the underlying transport has reconnected.</span></span>
- <span data-ttu-id="19610-264">`StateChanged`: Gerado quando o estado da conexão é alterado.</span><span class="sxs-lookup"><span data-stu-id="19610-264">`StateChanged`: Raised when the connection state changes.</span></span> <span data-ttu-id="19610-265">Fornece o estado antigo e o novo estado.</span><span class="sxs-lookup"><span data-stu-id="19610-265">Provides the old state and the new state.</span></span> <span data-ttu-id="19610-266">Para obter informações sobre conexão consulte valores de estado [enumeração ConnectionState](https://msdn.microsoft.com/en-us/library/microsoft.aspnet.signalr.client.connectionstate(v=vs.111).aspx).</span><span class="sxs-lookup"><span data-stu-id="19610-266">For information about connection state values see [ConnectionState Enumeration](https://msdn.microsoft.com/en-us/library/microsoft.aspnet.signalr.client.connectionstate(v=vs.111).aspx).</span></span>
- <span data-ttu-id="19610-267">`Closed`: Gerado quando a conexão foi desconectado.</span><span class="sxs-lookup"><span data-stu-id="19610-267">`Closed`: Raised when the connection has disconnected.</span></span>

<span data-ttu-id="19610-268">Por exemplo, se você quiser exibir mensagens de aviso para erros não fatais mas causam problemas intermitentes de conexão, como lentidão ou frequentes descartando de conexão, tratar o `ConnectionSlow` evento.</span><span class="sxs-lookup"><span data-stu-id="19610-268">For example, if you want to display warning messages for errors that are not fatal but cause intermittent connection problems, such as slowness or frequent dropping of the connection, handle the `ConnectionSlow` event.</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample30.cs)]

<span data-ttu-id="19610-269">Para obter mais informações, consulte [compreensão e tratamento de eventos de tempo de vida de Conexão no SignalR](handling-connection-lifetime-events.md).</span><span class="sxs-lookup"><span data-stu-id="19610-269">For more information, see [Understanding and Handling Connection Lifetime Events in SignalR](handling-connection-lifetime-events.md).</span></span>

<a id="handleerrors"></a>

## <a name="how-to-handle-errors"></a><span data-ttu-id="19610-270">Como tratar erros</span><span class="sxs-lookup"><span data-stu-id="19610-270">How to handle errors</span></span>

<span data-ttu-id="19610-271">Se você não habilitar explicitamente as mensagens de erro detalhadas no servidor, o objeto de exceção SignalR retorna após um erro contém algumas informações sobre o erro.</span><span class="sxs-lookup"><span data-stu-id="19610-271">If you don't explicitly enable detailed error messages on the server, the exception object that SignalR returns after an error contains minimal information about the error.</span></span> <span data-ttu-id="19610-272">Por exemplo, se uma chamada para `newContosoChatMessage` falhar, a mensagem de erro no objeto de erro contém "`There was an error invoking Hub method 'contosoChatHub.newContosoChatMessage'.`" enviar mensagens de erro detalhadas para clientes de produção não é recomendado por motivos de segurança, mas se você deseja habilitar as mensagens de erro detalhadas para solução de problemas, use o seguinte código no servidor.</span><span class="sxs-lookup"><span data-stu-id="19610-272">For example, if a call to `newContosoChatMessage` fails, the error message in the error object contains "`There was an error invoking Hub method 'contosoChatHub.newContosoChatMessage'.`" Sending detailed error messages to clients in production is not recommended for security reasons, but if you want to enable detailed error messages for troubleshooting purposes, use the following code on the server.</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample31.cs?highlight=2)]

<a id="handleerrors"></a>

<span data-ttu-id="19610-273">Para tratar erros que gera o SignalR, você pode adicionar um manipulador para o `Error` evento no objeto de conexão.</span><span class="sxs-lookup"><span data-stu-id="19610-273">To handle errors that SignalR raises, you can add a handler for the `Error` event on the connection object.</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample32.cs)]

<span data-ttu-id="19610-274">Para tratar erros de invocações do método, encapsule o código em um bloco try-catch.</span><span class="sxs-lookup"><span data-stu-id="19610-274">To handle errors from method invocations, wrap the code in a try-catch block.</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample33.cs)]

<a id="logging"></a>

## <a name="how-to-enable-client-side-logging"></a><span data-ttu-id="19610-275">Como habilitar o registro de cliente</span><span class="sxs-lookup"><span data-stu-id="19610-275">How to enable client-side logging</span></span>

<span data-ttu-id="19610-276">Para habilitar o registro em log do lado do cliente, defina o `TraceLevel` e `TraceWriter` propriedades no objeto de conexão.</span><span class="sxs-lookup"><span data-stu-id="19610-276">To enable client-side logging, set the `TraceLevel` and `TraceWriter` properties on the connection object.</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample34.cs?highlight=2-3)]

<a id="wpfsl"></a>

## <a name="wpf-silverlight-and-console-application-code-samples-for-client-methods-that-the-server-can-call"></a><span data-ttu-id="19610-277">Exemplos de código de aplicativo de console para métodos de cliente que o servidor pode chamar, Silverlight e WPF</span><span class="sxs-lookup"><span data-stu-id="19610-277">WPF, Silverlight, and console application code samples for client methods that the server can call</span></span>

<span data-ttu-id="19610-278">Os exemplos de código mostrados anteriormente para definir métodos de cliente que o servidor pode chamar se aplicam aos clientes do WinRT.</span><span class="sxs-lookup"><span data-stu-id="19610-278">The code samples shown earlier for defining client methods that the server can call apply to WinRT clients.</span></span> <span data-ttu-id="19610-279">Os exemplos a seguir mostram o código equivalente para WPF, Silverlight e clientes de aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="19610-279">The following samples show the equivalent code for WPF, Silverlight, and console application clients.</span></span>

### <a name="methods-without-parameters"></a><span data-ttu-id="19610-280">Métodos sem parâmetros</span><span class="sxs-lookup"><span data-stu-id="19610-280">Methods without parameters</span></span>

<span data-ttu-id="19610-281">**Código do cliente WPF para o método chamado a partir do servidor sem parâmetros**</span><span class="sxs-lookup"><span data-stu-id="19610-281">**WPF client code for method called from server without parameters**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample35.cs?highlight=1)]

<span data-ttu-id="19610-282">**Código do cliente Silverlight para o método chamado a partir do servidor sem parâmetros**</span><span class="sxs-lookup"><span data-stu-id="19610-282">**Silverlight client code for method called from server without parameters**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample36.cs?highlight=1)]

<span data-ttu-id="19610-283">**Código de cliente do aplicativo de console para o método chamado a partir do servidor sem parâmetros**</span><span class="sxs-lookup"><span data-stu-id="19610-283">**Console application client code for method called from server without parameters**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample37.cs?highlight=1)]

### <a name="methods-with-parameters-specifying-the-parameter-types"></a><span data-ttu-id="19610-284">Métodos com parâmetros, especificando os tipos de parâmetro</span><span class="sxs-lookup"><span data-stu-id="19610-284">Methods with parameters, specifying the parameter types</span></span>

<span data-ttu-id="19610-285">**Código de cliente do WPF para um método chamado a partir do servidor com um parâmetro**</span><span class="sxs-lookup"><span data-stu-id="19610-285">**WPF client code for a method called from server with a parameter**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample38.cs?highlight=1,4)]

<span data-ttu-id="19610-286">**Código do cliente Silverlight para um método chamado a partir do servidor com um parâmetro**</span><span class="sxs-lookup"><span data-stu-id="19610-286">**Silverlight client code for a method called from server with a parameter**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample39.cs?highlight=1,5)]

<span data-ttu-id="19610-287">**Código de cliente do aplicativo de console para um método chamado a partir do servidor com um parâmetro**</span><span class="sxs-lookup"><span data-stu-id="19610-287">**Console application client code for a method called from server with a parameter**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample40.cs?highlight=1-2)]

### <a name="methods-with-parameters-specifying-dynamic-objects-for-the-parameters"></a><span data-ttu-id="19610-288">Métodos com parâmetros, especificando objetos dinâmicos para os parâmetros</span><span class="sxs-lookup"><span data-stu-id="19610-288">Methods with parameters, specifying dynamic objects for the parameters</span></span>

<span data-ttu-id="19610-289">**Código de cliente do WPF para um método chamado a partir do servidor com um parâmetro, usando um objeto dinâmico para o parâmetro**</span><span class="sxs-lookup"><span data-stu-id="19610-289">**WPF client code for a method called from server with a parameter, using a dynamic object for the parameter**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample41.cs?highlight=1,4)]

<span data-ttu-id="19610-290">**Código do cliente Silverlight para um método chamado a partir do servidor com um parâmetro, usando um objeto dinâmico para o parâmetro**</span><span class="sxs-lookup"><span data-stu-id="19610-290">**Silverlight client code for a method called from server with a parameter, using a dynamic object for the parameter**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample42.cs?highlight=1,5)]

<span data-ttu-id="19610-291">**Código de cliente do aplicativo de console para um método chamado a partir do servidor com um parâmetro, usando um objeto dinâmico para o parâmetro**</span><span class="sxs-lookup"><span data-stu-id="19610-291">**Console application client code for a method called from server with a parameter, using a dynamic object for the parameter**</span></span>

[!code-csharp[Main](hubs-api-guide-net-client/samples/sample43.cs?highlight=1-2)]