---
uid: web-pages/overview/ui-layouts-and-themes/twitter-helper
title: "Auxiliar com páginas da Web ASP.NET do Twitter | Microsoft Docs"
author: tfitzmac
description: "Este tópico e o aplicativo mostram como adicionar um auxiliar do Twitter ao seu projeto do WebMatrix 3. Ele contém o código auxiliar do Twitter e mostra como chamar o auxiliar..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 02/07/2014
ms.topic: article
ms.assetid: c1a1244e-b9c8-42e6-a00b-8456a4ec027c
ms.technology: dotnet-webpages
ms.prod: .net-framework
msc.legacyurl: /web-pages/overview/ui-layouts-and-themes/twitter-helper
msc.type: authoredcontent
ms.openlocfilehash: 07d9c4d485c42b78a42c54c9740af5f67cb44763
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2017
---
<a name="twitter-helper-with-aspnet-web-pages"></a><span data-ttu-id="1aa8b-104">Auxiliar do Twitter com páginas da Web do ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1aa8b-104">Twitter Helper with ASP.NET Web Pages</span></span>
====================
<span data-ttu-id="1aa8b-105">por [Tom FitzMacken](https://github.com/tfitzmac)</span><span class="sxs-lookup"><span data-stu-id="1aa8b-105">by [Tom FitzMacken](https://github.com/tfitzmac)</span></span>

> <span data-ttu-id="1aa8b-106">Este tópico e o aplicativo mostram como adicionar um auxiliar do Twitter ao seu projeto do WebMatrix 3.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-106">This topic and application show how to add a Twitter Helper to your WebMatrix 3 project.</span></span> <span data-ttu-id="1aa8b-107">Ele contém o código auxiliar do Twitter e mostra como chamar os métodos auxiliares.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-107">It contains the Twitter Helper code and shows how to call the helper methods.</span></span>
> 
> <span data-ttu-id="1aa8b-108">Este código para o arquivo Twitter.cshtml foi desenvolvido por **Tian panorâmica** da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-108">This code for the Twitter.cshtml file was developed by **Tian Pan** of Microsoft.</span></span>
> 
> ## <a name="software-versions-used-in-the-tutorial"></a><span data-ttu-id="1aa8b-109">Versões de software usadas no tutorial</span><span class="sxs-lookup"><span data-stu-id="1aa8b-109">Software versions used in the tutorial</span></span>
> 
> 
> - <span data-ttu-id="1aa8b-110">Páginas da Web do ASP.NET (Razor) 3</span><span class="sxs-lookup"><span data-stu-id="1aa8b-110">ASP.NET Web Pages (Razor) 3</span></span>
>   
> 
> <span data-ttu-id="1aa8b-111">Este tutorial também funciona com 2 de páginas da Web do ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-111">This tutorial also works with ASP.NET Web Pages 2.</span></span>


## <a name="introduction"></a><span data-ttu-id="1aa8b-112">Introdução</span><span class="sxs-lookup"><span data-stu-id="1aa8b-112">Introduction</span></span>

<span data-ttu-id="1aa8b-113">Este tópico demonstra como adicionar um auxiliar do Twitter para o seu aplicativo e usar a sintaxe do Razor para chamar os métodos auxiliares.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-113">This topic demonstrates how to add a Twitter Helper to your application and use Razor syntax to call the helper methods.</span></span> <span data-ttu-id="1aa8b-114">O auxiliar do Twitter facilita a incorporar botões do Twitter e widgets em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-114">The Twitter Helper makes it easy to incorporate Twitter buttons and widgets in your application.</span></span> <span data-ttu-id="1aa8b-115">Para usar um widget do Twitter, como a linha de tempo do usuário ou os resultados da pesquisa para um hashtag, você deve primeiro criar o [widget no Twitter](https://twitter.com/settings/widgets).</span><span class="sxs-lookup"><span data-stu-id="1aa8b-115">To use a Twitter widget, such as a user's timeline or the search results for a hashtag, you must first create the [widget on Twitter](https://twitter.com/settings/widgets).</span></span> <span data-ttu-id="1aa8b-116">Depois de criar o widget, você receberá uma identificação de widget. Você pode passar essa id de widget como um parâmetro ao chamar os métodos auxiliares que mostram o widget.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-116">After creating your widget, you will receive a widget id. You pass this widget id as a parameter when calling the helper methods that show widget.</span></span>

<span data-ttu-id="1aa8b-117">Este tópico foi gravado para a versão 1.1 da API do Twitter.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-117">This topic was written for version 1.1 of the Twitter API.</span></span> <span data-ttu-id="1aa8b-118">Adicionando diretamente o código auxiliar do Twitter ao seu projeto, você pode atualizar o código auxiliar se altera de API do Twitter.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-118">By directly adding the Twitter Helper code to your project, you can update the helper code if the Twitter API changes.</span></span>

<span data-ttu-id="1aa8b-119">Para obter informações sobre como instalar o WebMatrix, consulte [Introdução ao ASP.NET páginas da Web 2 - Introdução](../getting-started/introducing-aspnet-web-pages-2/getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="1aa8b-119">For information about installing WebMatrix, see [Introducing ASP.NET Web Pages 2 - Getting Started](../getting-started/introducing-aspnet-web-pages-2/getting-started.md).</span></span>

## <a name="add-twitter-helper-to-your-project"></a><span data-ttu-id="1aa8b-120">Adicionar auxiliar do Twitter ao seu projeto</span><span class="sxs-lookup"><span data-stu-id="1aa8b-120">Add Twitter Helper to your project</span></span>

<span data-ttu-id="1aa8b-121">Para adicionar o auxiliar do Twitter, primeiro, adicione uma pasta denominada **aplicativo\_código** ao seu projeto.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-121">To add the Twitter Helper, first, add a folder named **App\_Code** to your project.</span></span> <span data-ttu-id="1aa8b-122">Em seguida, crie um arquivo chamado **Twitter.cshtml**.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-122">Then, create a file named **Twitter.cshtml**.</span></span>

![Pasta App_Code](twitter-helper/_static/image1.png)

<span data-ttu-id="1aa8b-124">Substitua o código no Twitter.cshtml com o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-124">Replace the default code in Twitter.cshtml with the following code.</span></span>

[!code-cshtml[Main](twitter-helper/samples/sample1.cshtml)]

## <a name="call-twitter-methods-from-your-web-pages"></a><span data-ttu-id="1aa8b-125">Chamar os métodos do Twitter de suas páginas da web</span><span class="sxs-lookup"><span data-stu-id="1aa8b-125">Call Twitter methods from your web pages</span></span>

<span data-ttu-id="1aa8b-126">O exemplo a seguir mostra como usar os métodos auxiliares do Twitter de uma página em seu projeto.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-126">The following example shows how to use the Twitter Helper methods from a page in your project.</span></span> <span data-ttu-id="1aa8b-127">No seu projeto, você desejará substituir os valores de parâmetro com valores que são relevantes para suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-127">In your project, you will want to replace the parameter values with values that are relevant to your needs.</span></span> <span data-ttu-id="1aa8b-128">Você pode usar as ids de widget fornecido para explorar como os métodos funcionam, mas você deve gerar seus próprios widgets para seu projeto.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-128">You can use the provided widget ids to explore how the methods work, but you will want to generate your own widgets for your project.</span></span>

<span data-ttu-id="1aa8b-129">Nem todos os parâmetros mostrados abaixo são necessários.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-129">Not all of the parameters shown below are required.</span></span> <span data-ttu-id="1aa8b-130">Os parâmetros opcionais são usados para personalizar como o botão ou o widget é exibido.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-130">The optional parameters are used to customize how the button or widget is displayed.</span></span> <span data-ttu-id="1aa8b-131">Por exemplo, o botão siga requer somente o nome de usuário a seguir, mas o exemplo mostra como incluir o número de seguidores e como especificar o tamanho do botão e o idioma.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-131">For example, the Follow Button only requires the user name to follow, but the example shows how to include the number of followers, and how specify the size of the button and the language.</span></span>

[!code-html[Main](twitter-helper/samples/sample2.html)]

## <a name="see-the-results"></a><span data-ttu-id="1aa8b-132">Ver os resultados</span><span class="sxs-lookup"><span data-stu-id="1aa8b-132">See the results</span></span>

<span data-ttu-id="1aa8b-133">O código acima produz os seguintes botões e widgets.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-133">The above code produces the following buttons and widgets.</span></span> <span data-ttu-id="1aa8b-134">Esses botões e widgets são totalmente funcional, não capturas de tela.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-134">These buttons and widgets are fully-functional, not screenshots.</span></span> <span data-ttu-id="1aa8b-135">Botão a seguir é exibido em espanhol porque o parâmetro de idioma foi definido como **es**.</span><span class="sxs-lookup"><span data-stu-id="1aa8b-135">The Follow Button is displayed in Spanish because the language parameter was set to **es**.</span></span>

### <a name="follow-button"></a><span data-ttu-id="1aa8b-136">Siga o botão</span><span class="sxs-lookup"><span data-stu-id="1aa8b-136">Follow Button</span></span>

<span data-ttu-id="1aa8b-137">[Execute @aspnet)](https://twitter.com/aspnet)<script>! função (d, s, id) {var js, fjs = d.getElementsByTagName(s) [0], p = /^http:/.test(d.location)? 'http': 'https'. Se (! d.getElementById(id)) {js = d.createElement(s); js.id = id; js.src = p + ': / / platform.twitter.com/widgets.js'; fjs.parentNode.insertBefore (js, fjs);}} (documento, 'script', 'twitter wjs');</script></span><span class="sxs-lookup"><span data-stu-id="1aa8b-137">[Follow @aspnet)](https://twitter.com/aspnet)<script>!function (d, s, id) { var js, fjs = d.getElementsByTagName(s)[0], p = /^http:/.test(d.location) ? 'http' : 'https'; if (!d.getElementById(id)) { js = d.createElement(s); js.id = id; js.src = p + '://platform.twitter.com/widgets.js'; fjs.parentNode.insertBefore(js, fjs); } }(document, 'script', 'twitter-wjs');</script></span></span>

### <a name="tweet-button"></a><span data-ttu-id="1aa8b-138">Botão Tweet</span><span class="sxs-lookup"><span data-stu-id="1aa8b-138">Tweet Button</span></span>

<span data-ttu-id="1aa8b-139">[Tweet](https://twitter.com/share)<script>! função (d, s, id) {var js, fjs = d.getElementsByTagName(s) [0], p = /^http:/.test(d.location)? 'http': 'https'. Se (! d.getElementById(id)) {js = d.createElement(s); js.id = id; js.src = p + ': / / platform.twitter.com/widgets.js'; fjs.parentNode.insertBefore (js, fjs);}} (documento, 'script', 'twitter wjs');</script></span><span class="sxs-lookup"><span data-stu-id="1aa8b-139">[Tweet](https://twitter.com/share)<script>!function (d, s, id) { var js, fjs = d.getElementsByTagName(s)[0], p = /^http:/.test(d.location) ? 'http' : 'https'; if (!d.getElementById(id)) { js = d.createElement(s); js.id = id; js.src = p + '://platform.twitter.com/widgets.js'; fjs.parentNode.insertBefore(js, fjs); } }(document, 'script', 'twitter-wjs');</script></span></span>

### <a name="user-timeline-profile"></a><span data-ttu-id="1aa8b-140">Linha do tempo do usuário (perfil)</span><span class="sxs-lookup"><span data-stu-id="1aa8b-140">User Timeline (Profile)</span></span>

<span data-ttu-id="1aa8b-141">[TWEETS por @aspnet ](https://twitter.com/aspnet) <script>! função (d, s, id) {var js, fjs = d.getElementsByTagName(s) [0], p = /^http:/.test(d.location)? 'http': 'https'. Se (! d.getElementById(id)) {js = d.createElement(s); js.id = id; js.src = p + ": / / platform.twitter.com/widgets.js"; fjs.parentNode.insertBefore (js, fjs);}} (documento, "script", "wjs twitter");</script></span><span class="sxs-lookup"><span data-stu-id="1aa8b-141">[Tweets by @aspnet](https://twitter.com/aspnet)<script>!function (d, s, id) { var js, fjs = d.getElementsByTagName(s)[0], p = /^http:/.test(d.location) ? 'http' : 'https'; if (!d.getElementById(id)) { js = d.createElement(s); js.id = id; js.src = p + "://platform.twitter.com/widgets.js"; fjs.parentNode.insertBefore(js, fjs); } }(document, "script", "twitter-wjs");</script></span></span>

### <a name="favorites"></a><span data-ttu-id="1aa8b-142">Favoritos</span><span class="sxs-lookup"><span data-stu-id="1aa8b-142">Favorites</span></span>

<span data-ttu-id="1aa8b-143">[Tweets favorito por @Microsoft ](https://twitter.com/Microsoft/favorites) <script>! função (d, s, id) {var js, fjs = d.getElementsByTagName(s) [0], p = /^http:/.test(d.location)? 'http': 'https'. Se (! d.getElementById(id)) {js = d.createElement(s); js.id = id; js.src = p + ": / / platform.twitter.com/widgets.js"; fjs.parentNode.insertBefore (js, fjs);}} (documento, "script", "wjs twitter");</script></span><span class="sxs-lookup"><span data-stu-id="1aa8b-143">[Favorite Tweets by @Microsoft](https://twitter.com/Microsoft/favorites)<script>!function (d, s, id) { var js, fjs = d.getElementsByTagName(s)[0], p = /^http:/.test(d.location) ? 'http' : 'https'; if (!d.getElementById(id)) { js = d.createElement(s); js.id = id; js.src = p + "://platform.twitter.com/widgets.js"; fjs.parentNode.insertBefore(js, fjs); } }(document, "script", "twitter-wjs");</script></span></span>

### <a name="list"></a><span data-ttu-id="1aa8b-144">Lista</span><span class="sxs-lookup"><span data-stu-id="1aa8b-144">List</span></span>

<span data-ttu-id="1aa8b-145">[TWEETS de @Microsoft/MS \_consumidor\_faixas](https://twitter.com/microsoft/ms-consumer-brands/)<script>! função (d, s, id) {var js, fjs = d.getElementsByTagName(s) [0], p = /^http:/.test(d.location)? 'http': 'https'. Se (! d.getElementById(id)) {js = d.createElement(s); js.id = id; js.src = p + ": / / platform.twitter.com/widgets.js"; fjs.parentNode.insertBefore (js, fjs);}} (documento, "script", "wjs twitter");</script></span><span class="sxs-lookup"><span data-stu-id="1aa8b-145">[Tweets from @Microsoft/MS\_Consumer\_Bands](https://twitter.com/microsoft/ms-consumer-brands/)<script>!function (d, s, id) { var js, fjs = d.getElementsByTagName(s)[0], p = /^http:/.test(d.location) ? 'http' : 'https'; if (!d.getElementById(id)) { js = d.createElement(s); js.id = id; js.src = p + "://platform.twitter.com/widgets.js"; fjs.parentNode.insertBefore(js, fjs); } }(document, "script", "twitter-wjs");</script></span></span>

### <a name="search"></a><span data-ttu-id="1aa8b-146">Pesquisar</span><span class="sxs-lookup"><span data-stu-id="1aa8b-146">Search</span></span>

<span data-ttu-id="1aa8b-147">[TWEETS sobre &quot;#asp.net&quot;](https://twitter.com/search?q=%23asp.net)<script>! função (d, s, id) {var js, fjs = d.getElementsByTagName(s) [0], p = /^http:/.test(d.location)? 'http': 'https'. Se (! d.getElementById(id)) {js = d.createElement(s); js.id = id; js.src = p + ": / / platform.twitter.com/widgets.js"; fjs.parentNode.insertBefore (js, fjs);}} (documento, "script", "wjs twitter");</script></span><span class="sxs-lookup"><span data-stu-id="1aa8b-147">[Tweets about &quot;#asp.net&quot;](https://twitter.com/search?q=%23asp.net)<script>!function (d, s, id) { var js, fjs = d.getElementsByTagName(s)[0], p = /^http:/.test(d.location) ? 'http' : 'https'; if (!d.getElementById(id)) { js = d.createElement(s); js.id = id; js.src = p + "://platform.twitter.com/widgets.js"; fjs.parentNode.insertBefore(js, fjs); } }(document, "script", "twitter-wjs");</script></span></span>