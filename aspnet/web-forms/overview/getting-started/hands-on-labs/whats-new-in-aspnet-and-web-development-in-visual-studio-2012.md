---
uid: web-forms/overview/getting-started/hands-on-labs/whats-new-in-aspnet-and-web-development-in-visual-studio-2012
title: "O que há de novo no ASP.NET e desenvolvimento da Web no Visual Studio 2012 | Microsoft Docs"
author: rick-anderson
description: "A nova versão do Visual Studio apresenta uma série de melhorias que se concentrou em melhorar a experiência e o desempenho ao trabalhar com tecnologias da Web..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 02/18/2013
ms.topic: article
ms.assetid: 6d40d276-1642-4a77-b6c9-02ac914f6805
ms.technology: dotnet-webforms
ms.prod: .net-framework
msc.legacyurl: /web-forms/overview/getting-started/hands-on-labs/whats-new-in-aspnet-and-web-development-in-visual-studio-2012
msc.type: authoredcontent
ms.openlocfilehash: f0818cce2a82ede80556b3471cec9d965c3e987f
ms.sourcegitcommit: 060879fcf3f73d2366b5c811986f8695fff65db8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2018
---
<a name="whats-new-in-aspnet-and-web-development-in-visual-studio-2012"></a><span data-ttu-id="55a2e-103">O que há de novo no ASP.NET e desenvolvimento da Web no Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="55a2e-103">What's New in ASP.NET and Web Development in Visual Studio 2012</span></span>
====================
<span data-ttu-id="55a2e-104">por [Web Camps Team](https://twitter.com/webcamps)</span><span class="sxs-lookup"><span data-stu-id="55a2e-104">by [Web Camps Team](https://twitter.com/webcamps)</span></span>

> <span data-ttu-id="55a2e-105">A nova versão do Visual Studio apresenta uma série de melhorias que se concentrou em melhorar a experiência e o desempenho ao trabalhar com tecnologias da Web.</span><span class="sxs-lookup"><span data-stu-id="55a2e-105">The new version of Visual Studio introduces a number of enhancements focused on improving the experience and performance when working with Web technologies.</span></span> <span data-ttu-id="55a2e-106">Editores de CSS, JavaScript e HTML do Visual Studio foi completamente reformuladas para incluir muitas os auxílios de código mais acessado, como IntelliSense e recuo automático.</span><span class="sxs-lookup"><span data-stu-id="55a2e-106">Visual Studio Editors for CSS, JavaScript and HTML have been completely revamped to include many of the most in-demand code aids, such as IntelliSense and automatic indentation.</span></span> <span data-ttu-id="55a2e-107">Em relação ao desempenho, empacotamento e minimização agora estão integrados como tempo de carregamento de recursos internos para reduzir facilmente a página.</span><span class="sxs-lookup"><span data-stu-id="55a2e-107">Regarding performance, bundling and minification are now integrated as built-in features to easily reduce page load time.</span></span>
> 
> <span data-ttu-id="55a2e-108">O Visual Studio permite que você trabalhe com as tecnologias mais recentes do site.</span><span class="sxs-lookup"><span data-stu-id="55a2e-108">Visual Studio enables you to work with the latest website technologies.</span></span> <span data-ttu-id="55a2e-109">Você pode usar vários navegadores CSS3 trechos para certificar-se de que seu site funciona independentemente da plataforma de cliente e também aproveitar os novos recursos e elementos de HTML5.</span><span class="sxs-lookup"><span data-stu-id="55a2e-109">You can use cross-browser CSS3 Snippets to make sure your site works regardless of the client platform while also taking advantage of the new HTML5 elements and features.</span></span>
> 
> <span data-ttu-id="55a2e-110">Gravação e criação de perfil de código JavaScript devem ser mais fácil com esta versão do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="55a2e-110">Writing and profiling JavaScript code should be easier with this Visual Studio version.</span></span> <span data-ttu-id="55a2e-111">Listas do IntelliSense, recursos integrados de navegação e de documentação XML agora estão disponíveis para o código JavaScript.</span><span class="sxs-lookup"><span data-stu-id="55a2e-111">IntelliSense lists, integrated XML documentation and navigation features are now available for JavaScript code.</span></span> <span data-ttu-id="55a2e-112">Agora você tem o catálogo de JavaScript ao seu alcance.</span><span class="sxs-lookup"><span data-stu-id="55a2e-112">You now have the JavaScript catalog at your fingertips.</span></span> <span data-ttu-id="55a2e-113">Além disso, você pode verificar a conformidade da ECMAScript5 com seus scripts e detectar erros de sintaxe em uma etapa inicial.</span><span class="sxs-lookup"><span data-stu-id="55a2e-113">Additionally, you can check ECMAScript5 compliance with your scripts and detect syntax errors at an early stage.</span></span>
> 
> <span data-ttu-id="55a2e-114">Por último, mas não menos importante, esta versão do Visual Studio implementa internos de empacotamento e minimização.</span><span class="sxs-lookup"><span data-stu-id="55a2e-114">Last but not least, this Visual Studio version implements built-in bundling and minification.</span></span> <span data-ttu-id="55a2e-115">Arquivos de script e folhas de estilo serão compactadas e compactadas para que o site executa com mais rapidez.</span><span class="sxs-lookup"><span data-stu-id="55a2e-115">Your script files and style sheets will be packed and compressed so that the site performs faster.</span></span>
> 
> <span data-ttu-id="55a2e-116">Este laboratório orienta os aperfeiçoamentos e novos recursos descritos anteriormente, aplicando alterações secundárias a um aplicativo da Web de exemplo fornecido na pasta de origem.</span><span class="sxs-lookup"><span data-stu-id="55a2e-116">This lab walks you through the enhancements and new features previously described by applying minor changes to a sample Web application provided in the Source folder.</span></span>
> 
> <span data-ttu-id="55a2e-117">Todo o código de exemplo e trechos de código são incluídos no Web Camps treinamento Kit, disponíveis em [https://go.microsoft.com/fwlink/?LinkID=248297&clcid=0x409](https://go.microsoft.com/fwlink/?LinkID=248297&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="55a2e-117">All sample code and snippets are included in the Web Camps Training Kit, available at [https://go.microsoft.com/fwlink/?LinkID=248297&clcid=0x409](https://go.microsoft.com/fwlink/?LinkID=248297&clcid=0x409).</span></span>


<a id="Objectives"></a>

<a id="Objectives"></a>
### <a name="objectives"></a><span data-ttu-id="55a2e-118">Objetivos</span><span class="sxs-lookup"><span data-stu-id="55a2e-118">Objectives</span></span>

<span data-ttu-id="55a2e-119">Este laboratório prático, você aprenderá como:</span><span class="sxs-lookup"><span data-stu-id="55a2e-119">In this hands on lab, you will learn how to:</span></span>

- <span data-ttu-id="55a2e-120">Use os novos recursos e aprimoramentos no editor de CSS</span><span class="sxs-lookup"><span data-stu-id="55a2e-120">Use the new features and improvements in the CSS editor</span></span>
- <span data-ttu-id="55a2e-121">Use os novos recursos e aprimoramentos no editor de HTML</span><span class="sxs-lookup"><span data-stu-id="55a2e-121">Use the new features and improvements in the HTML editor</span></span>
- <span data-ttu-id="55a2e-122">Use os novos recursos e aprimoramentos no editor de JavaScript</span><span class="sxs-lookup"><span data-stu-id="55a2e-122">Use the new features and improvements in the JavaScript editor</span></span>
- <span data-ttu-id="55a2e-123">Configurar e usar o empacotamento e minimização</span><span class="sxs-lookup"><span data-stu-id="55a2e-123">Configure and use bundling and minification</span></span>

<a id="Prerequisites"></a>

<a id="Prerequisites"></a>
### <a name="prerequisites"></a><span data-ttu-id="55a2e-124">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="55a2e-124">Prerequisites</span></span>

- <span data-ttu-id="55a2e-125">[Microsoft Visual Studio Express 2012 para Web](https://www.microsoft.com/visualstudio/eng/products/visual-studio-express-for-web) ou superior (leitura [Apêndice A](#AppendixA) para obter instruções sobre como instalá-lo).</span><span class="sxs-lookup"><span data-stu-id="55a2e-125">[Microsoft Visual Studio Express 2012 for Web](https://www.microsoft.com/visualstudio/eng/products/visual-studio-express-for-web) or superior (read [Appendix A](#AppendixA) for instructions on how to install it).</span></span>
- <span data-ttu-id="55a2e-126">[O Windows PowerShell](https://support.microsoft.com/kb/968930/) (para scripts de instalação - já instalados no Windows 8 e Windows Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="55a2e-126">[Windows PowerShell](https://support.microsoft.com/kb/968930/) (for setup scripts - already installed on Windows 8 and Windows Server 2008 R2)</span></span>
- <span data-ttu-id="55a2e-127">[O Internet Explorer 10](https://windows.microsoft.com/internet-explorer/products/ie/home) - ou um navegador compatível com HTML5</span><span class="sxs-lookup"><span data-stu-id="55a2e-127">[Internet Explorer 10](https://windows.microsoft.com/internet-explorer/products/ie/home) - or an HTML5 compliant browser</span></span>

<a id="Exercises"></a>

<a id="Exercises"></a>
## <a name="exercises"></a><span data-ttu-id="55a2e-128">Exercícios</span><span class="sxs-lookup"><span data-stu-id="55a2e-128">Exercises</span></span>

<span data-ttu-id="55a2e-129">Este laboratório prático inclui os seguintes exercícios:</span><span class="sxs-lookup"><span data-stu-id="55a2e-129">This hands on lab includes the following exercises:</span></span>

1. [<span data-ttu-id="55a2e-130">Exercício 1: O que há de novo no Editor de CSS</span><span class="sxs-lookup"><span data-stu-id="55a2e-130">Exercise 1: What's New in the CSS Editor</span></span>](#Exercise1)
2. [<span data-ttu-id="55a2e-131">Exercício 2: O que há de novo no Editor de HTML</span><span class="sxs-lookup"><span data-stu-id="55a2e-131">Exercise 2: What's New in the HTML Editor</span></span>](#Exercise2)
3. [<span data-ttu-id="55a2e-132">Exercício 3: O que há de novo no Editor de JavaScript</span><span class="sxs-lookup"><span data-stu-id="55a2e-132">Exercise 3: What's New in the JavaScript Editor</span></span>](#Exercise3)
4. [<span data-ttu-id="55a2e-133">Exercício 4: Empacotamento e minimização</span><span class="sxs-lookup"><span data-stu-id="55a2e-133">Exercise 4: Bundling and Minification</span></span>](#Exercise4)

<span data-ttu-id="55a2e-134">Tempo estimado para concluir este laboratório: **60 minutos**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-134">Estimated time to complete this lab: **60 minutes**.</span></span>

<a id="Exercise1"></a>

<a id="Exercise_1_Whats_New_in_the_CSS_Editor"></a>
### <a name="exercise-1-whats-new-in-the-css-editor"></a><span data-ttu-id="55a2e-135">Exercício 1: O que há de novo no Editor de CSS</span><span class="sxs-lookup"><span data-stu-id="55a2e-135">Exercise 1: What's New in the CSS Editor</span></span>

<span data-ttu-id="55a2e-136">Os desenvolvedores da Web devem estar familiarizados com muitas das dificuldades relacionadas à edição de CSS.</span><span class="sxs-lookup"><span data-stu-id="55a2e-136">Web developers should be familiar with many of the difficulties related to CSS editing.</span></span> <span data-ttu-id="55a2e-137">Uma das maiores questões de folhas de estilos é compatibilidade entre navegadores.</span><span class="sxs-lookup"><span data-stu-id="55a2e-137">One of the biggest issues of CSS styling is cross-browser compatibility.</span></span> <span data-ttu-id="55a2e-138">Isso geralmente acontece que, depois de aplicar estilos a seu site, você notar que parece diferente se você abri-lo em outro dispositivo ou navegador.</span><span class="sxs-lookup"><span data-stu-id="55a2e-138">It often happens that, after applying styles to your site, you notice that it looks different if you open it in another browser or device.</span></span> <span data-ttu-id="55a2e-139">Portanto, você pode gastar um tempo considerável para corrigir esses problemas visual para perceber que, quando você finalmente utilizá-lo em um navegador, ela é quebrada em outros.</span><span class="sxs-lookup"><span data-stu-id="55a2e-139">Therefore, you may spend a considerable time on fixing those visual issues to realize that, when you finally make it work in one browser, it is broken in the others.</span></span>

<span data-ttu-id="55a2e-140">O Visual Studio agora inclui recursos que ajudam os desenvolvedores acessar, trabalhar e organizar folhas de estilos CSS de forma eficiente.</span><span class="sxs-lookup"><span data-stu-id="55a2e-140">Visual Studio now includes features that help developers access, work and organize CSS style sheets effectively.</span></span> <span data-ttu-id="55a2e-141">Ao longo deste exercício, você atende os novos recursos para uma organização efetivada e a edição, bem como os trechos de código CSS3 para compatibilidade entre navegadores.</span><span class="sxs-lookup"><span data-stu-id="55a2e-141">Throughout this exercise, you will meet the new features for an effective organization and edition, as well as the CSS3 Code Snippets for cross-browser compatibility.</span></span>

<a id="Ex1Task1"></a>

<a id="Task_1_-_New_Editor_Features"></a>
#### <a name="task-1---new-editor-features"></a><span data-ttu-id="55a2e-142">Tarefa 1 - novos recursos do Editor</span><span class="sxs-lookup"><span data-stu-id="55a2e-142">Task 1 - New Editor Features</span></span>

<span data-ttu-id="55a2e-143">Nesta tarefa, você descobrirá que os novos recursos do Editor de CSS.</span><span class="sxs-lookup"><span data-stu-id="55a2e-143">In this task, you will discover the new features of the CSS Editor.</span></span> <span data-ttu-id="55a2e-144">Este novo editor ajudará você a aumentar sua produtividade, aproveitando o recuo inteligente novo, os comentários de código aperfeiçoada e a lista aprimorada do IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="55a2e-144">This new editor will help you increase your productivity by taking advantage of the new smart indentation, the improved code comments and the enhanced IntelliSense list.</span></span>

1. <span data-ttu-id="55a2e-145">Iniciar **Visual Studio** e abra o **WhatsNewASPNET.sln** solução localizada no **Source\WhatsNewASPNET** pasta deste laboratório.</span><span class="sxs-lookup"><span data-stu-id="55a2e-145">Start **Visual Studio** and open the **WhatsNewASPNET.sln** solution located in the **Source\WhatsNewASPNET** folder of this lab.</span></span>
2. <span data-ttu-id="55a2e-146">No Solution Explorer, abra o **Site.css** arquivo localizado sob o **estilos** pasta.</span><span class="sxs-lookup"><span data-stu-id="55a2e-146">In Solution Explorer, open the **Site.css** file located under the **Styles** folder.</span></span> <span data-ttu-id="55a2e-147">Verifique se o **Editor de texto** ferramentas são visíveis na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="55a2e-147">Make sure the **Text Editor** tools are visible on the toolbar.</span></span> <span data-ttu-id="55a2e-148">Para fazer isso, selecione o **exibição** | **barras de ferramentas** opção de menu e verifique o **Editor de texto** opções.</span><span class="sxs-lookup"><span data-stu-id="55a2e-148">To do that, select the **View** | **Toolbars** menu option, and check the **Text Editor** options.</span></span> <span data-ttu-id="55a2e-149">Você observará que, desde que essa nova versão, o **comentário** botão (![botão comentário](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image1.png) ) e o **Uncomment** botão (![Descomente-botão](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image2.png)) também serão habilitados para o editor de CSS.</span><span class="sxs-lookup"><span data-stu-id="55a2e-149">You will notice that, since this new version, the **Comment** button (![comment-button](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image1.png) ) and the **Uncomment** button (![uncomment-button](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image2.png) ) are also enabled for the CSS editor.</span></span>

    <span data-ttu-id="55a2e-150">![Habilitando o Editor e ferramentas CSS](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image3.png "habilitando o Editor e ferramentas CSS")</span><span class="sxs-lookup"><span data-stu-id="55a2e-150">![Enabling Editor and CSS Tools](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image3.png "Enabling Editor and CSS Tools")</span></span>

    <span data-ttu-id="55a2e-151">*Habilitando o Editor e ferramentas CSS*</span><span class="sxs-lookup"><span data-stu-id="55a2e-151">*Enabling Editor and CSS Tools*</span></span>
3. <span data-ttu-id="55a2e-152">Role o código e selecione qualquer definição de classe CSS.</span><span class="sxs-lookup"><span data-stu-id="55a2e-152">Scroll the code and select any CSS class definition.</span></span> <span data-ttu-id="55a2e-153">Clique o **comentário** (![botão comentário](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image4.png) ) botão para comentar as linhas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="55a2e-153">Click the **Comment** (![comment-button](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image4.png) ) button to comment the selected lines.</span></span> <span data-ttu-id="55a2e-154">Em seguida, clique no **Uncomment** (![botão Descomente](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image5.png) ) botão Desfazer as alterações.</span><span class="sxs-lookup"><span data-stu-id="55a2e-154">Then, click the **Uncomment** (![uncomment-button](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image5.png) ) button to undo the changes.</span></span>
4. <span data-ttu-id="55a2e-155">Clique o **recolher** (![recolher](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image6.png) ) e **expandir** (![expanda](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image7.png) ) botões localizados na margem esquerda do texto.</span><span class="sxs-lookup"><span data-stu-id="55a2e-155">Click the **Collapse** (![collapse](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image6.png) ) and **Expand** (![expand](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image7.png) ) buttons located on the left margin of the text.</span></span> <span data-ttu-id="55a2e-156">Observe que agora você pode ocultar os estilos que você não usar para ter uma exibição de limpeza.</span><span class="sxs-lookup"><span data-stu-id="55a2e-156">Notice that you can now hide the styles you don't use to have a cleaner view.</span></span>

    <span data-ttu-id="55a2e-157">![Recolhendo classes CSS](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image8.png "classes CSS recolhendo")</span><span class="sxs-lookup"><span data-stu-id="55a2e-157">![Collapsing CSS classes](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image8.png "Collapsing CSS classes")</span></span>

    <span data-ttu-id="55a2e-158">*Recolhendo classes CSS*</span><span class="sxs-lookup"><span data-stu-id="55a2e-158">*Collapsing CSS classes*</span></span>
5. <span data-ttu-id="55a2e-159">Certifique-se de que o recurso de recuo inteligente está habilitado.</span><span class="sxs-lookup"><span data-stu-id="55a2e-159">Make sure that the smart indentation feature is enabled.</span></span> <span data-ttu-id="55a2e-160">Selecione o **ferramentas** | **opções** opção de menu e selecione o **Editor de texto** | **CSS**  |  **Formatação** página no painel esquerdo da tela.</span><span class="sxs-lookup"><span data-stu-id="55a2e-160">Select the **Tools** | **Options** menu option, and then select the **Text Editor** | **CSS** | **Formatting** page in the left pane of the screen.</span></span> <span data-ttu-id="55a2e-161">Verifique o **recuo hierárquico** opção.</span><span class="sxs-lookup"><span data-stu-id="55a2e-161">Check the **Hierarchical indentation** option.</span></span>

    <span data-ttu-id="55a2e-162">![Habilitando o recuo hierárquico](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image9.png "habilitando recuo hierárquico")</span><span class="sxs-lookup"><span data-stu-id="55a2e-162">![Enabling hierarchical indentation](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image9.png "Enabling hierarchical indentation")</span></span>

    <span data-ttu-id="55a2e-163">*Habilitando o recuo hierárquico*</span><span class="sxs-lookup"><span data-stu-id="55a2e-163">*Enabling hierarchical indentation*</span></span>
6. <span data-ttu-id="55a2e-164">Localize a definição de classe principal (. Main) e acrescente um estilo para elementos div.</span><span class="sxs-lookup"><span data-stu-id="55a2e-164">Locate the main class definition (.main) and append a style to the div elements.</span></span> <span data-ttu-id="55a2e-165">Você observará que o código automaticamente, alinha ajudar os usuários para localizar o pai classes em um relance.</span><span class="sxs-lookup"><span data-stu-id="55a2e-165">You will notice that the code aligns automatically, helping users to find the parent classes at a glance.</span></span>

    <span data-ttu-id="55a2e-166">CSS</span><span class="sxs-lookup"><span data-stu-id="55a2e-166">CSS</span></span>

    [!code-css[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample1.css)]

    <span data-ttu-id="55a2e-167">![Alinhamento hierárquico em CSS](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image10.png "alinhamento hierárquico em CSS")</span><span class="sxs-lookup"><span data-stu-id="55a2e-167">![Hierarchical alignment in CSS](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image10.png "Hierarchical alignment in CSS")</span></span>

    <span data-ttu-id="55a2e-168">*Alinhamento hierárquico em CSS*</span><span class="sxs-lookup"><span data-stu-id="55a2e-168">*Hierarchical alignment in CSS*</span></span>
7. <span data-ttu-id="55a2e-169">Dentro de **. Main div** classe, localize o cursor no final do **border: 0px;** e pressione **Enter** para exibir a lista do IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="55a2e-169">Inside **.main div** class, locate the cursor at the end of **border: 0px;** and press **Enter** to display the IntelliSense list.</span></span> <span data-ttu-id="55a2e-170">Comece a digitar **superior** e observe como a lista é filtrada conforme você digita.</span><span class="sxs-lookup"><span data-stu-id="55a2e-170">Start typing **top** and notice how the list is filtered as you type.</span></span> <span data-ttu-id="55a2e-171">A lista exibirá os elementos que contêm **superior** em qualquer parte da palavra (nas versões anteriores do Visual Studio, a lista é filtrada pelos itens que *começar* com o termo).</span><span class="sxs-lookup"><span data-stu-id="55a2e-171">The list will display the elements that contain **top** at any part of the word (In prior versions of Visual Studio, the list is filtered by the items that *begin* with the term).</span></span>

    <span data-ttu-id="55a2e-172">![Aprimoramentos de IntelliSense no CSS](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image11.png "aprimoramentos de IntelliSense no CSS")</span><span class="sxs-lookup"><span data-stu-id="55a2e-172">![IntelliSense enhancements in CSS](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image11.png "IntelliSense enhancements in CSS")</span></span>

    <span data-ttu-id="55a2e-173">*Aprimoramentos de IntelliSense no CSS*</span><span class="sxs-lookup"><span data-stu-id="55a2e-173">*IntelliSense enhancements in CSS*</span></span>

<a id="Ex1Task2"></a>

<a id="Task_2_-_The_Color_Picker"></a>
#### <a name="task-2---the-color-picker"></a><span data-ttu-id="55a2e-174">Tarefa 2 - o seletor de cores</span><span class="sxs-lookup"><span data-stu-id="55a2e-174">Task 2 - The Color Picker</span></span>

<span data-ttu-id="55a2e-175">Nesta tarefa, você descobrirá que o novo seletor de cores CSS integrado ao Visual Studio IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="55a2e-175">In this task, you will discover the new CSS Color Picker integrated into Visual Studio IntelliSense.</span></span>

1. <span data-ttu-id="55a2e-176">Em **Site.css,** localize a definição de classe de cabeçalho (.header) e coloque o cursor ao lado **cor de plano de fundo** atributo entre o &quot;:&quot; e &quot; # &quot; caracteres na linha de código **.**</span><span class="sxs-lookup"><span data-stu-id="55a2e-176">In **Site.css,** locate the header class definition (.header) and place the cursor next to **background-color** attribute, between the &quot;:&quot; and &quot;#&quot; characters on that line of code **.**</span></span>

    <span data-ttu-id="55a2e-177">![Localizando o cursor](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image12.png "localizando o cursor")</span><span class="sxs-lookup"><span data-stu-id="55a2e-177">![Locating the cursor](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image12.png "Locating the cursor")</span></span>

    <span data-ttu-id="55a2e-178">*Localizando o cursor*</span><span class="sxs-lookup"><span data-stu-id="55a2e-178">*Locating the cursor*</span></span>
2. <span data-ttu-id="55a2e-179">Excluir o **vírgula** (:) e gravá-la novamente para exibir o seletor de cores.</span><span class="sxs-lookup"><span data-stu-id="55a2e-179">Delete the **colon** (:) and write it again to display the color picker.</span></span> <span data-ttu-id="55a2e-180">Observe que as cores primeiro, que você verá as cores mais frequentes do seu site.</span><span class="sxs-lookup"><span data-stu-id="55a2e-180">Notice that the first colors you will see are the most frequent colors of your site.</span></span> <span data-ttu-id="55a2e-181">Se você clicar na cor branca, seu código de cor HTML (#fff) substitui o código de cor atual na folha de estilos.</span><span class="sxs-lookup"><span data-stu-id="55a2e-181">If you click the white color, its HTML color code (#fff) will replace the current color code in the stylesheet.</span></span>

    <span data-ttu-id="55a2e-182">![Seletor de cores](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image13.png "seletor de cores")</span><span class="sxs-lookup"><span data-stu-id="55a2e-182">![Color picker](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image13.png "Color picker")</span></span>

    <span data-ttu-id="55a2e-183">*Seletor de cores*</span><span class="sxs-lookup"><span data-stu-id="55a2e-183">*Color picker*</span></span>
3. <span data-ttu-id="55a2e-184">Pressione a **expandir** (![com](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image14.png) ) botão seletor de cores para exibir o gradiente de cores e, em seguida, arraste o cursor gradiente para selecionar uma cor diferente.</span><span class="sxs-lookup"><span data-stu-id="55a2e-184">Press the **Expand** (![com](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image14.png) ) button on the color picker to display the color gradient, and then drag the gradient cursor to select a different color.</span></span> <span data-ttu-id="55a2e-185">Em seguida, clique o **conta-gotas** botão e selecione todas as cores da tela.</span><span class="sxs-lookup"><span data-stu-id="55a2e-185">After that, click the **Eyedropper** button and select any color from the screen.</span></span> <span data-ttu-id="55a2e-186">Observe que o valor de cor do plano de fundo muda dinamicamente enquanto você move o cursor.</span><span class="sxs-lookup"><span data-stu-id="55a2e-186">Notice that background color value changes dynamically while you move the cursor.</span></span>

    <span data-ttu-id="55a2e-187">![Gradiente de seletor de cores](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image15.png "gradiente do seletor de cores")</span><span class="sxs-lookup"><span data-stu-id="55a2e-187">![Color picker gradient](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image15.png "Color picker gradient")</span></span>

    <span data-ttu-id="55a2e-188">*Gradiente de seletor de cores*</span><span class="sxs-lookup"><span data-stu-id="55a2e-188">*Color picker gradient*</span></span>
4. <span data-ttu-id="55a2e-189">No **opacidade** controle deslizante, mova o seletor para o centro da barra para reduzir a opacidade.</span><span class="sxs-lookup"><span data-stu-id="55a2e-189">In the **Opacity** slider, move the selector to the center of the bar to reduce the opacity.</span></span> <span data-ttu-id="55a2e-190">Observe que o valor de cor de plano de fundo agora altera sua escala para RGBA.</span><span class="sxs-lookup"><span data-stu-id="55a2e-190">Notice that background-color value now changes its scale to RGBA.</span></span>

    <span data-ttu-id="55a2e-191">![Seletor de cores opacidade](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image16.png "opacidade do seletor de cores")</span><span class="sxs-lookup"><span data-stu-id="55a2e-191">![Color picker Opacity](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image16.png "Color picker Opacity")</span></span>

    <span data-ttu-id="55a2e-192">*Opacidade do seletor de cores*</span><span class="sxs-lookup"><span data-stu-id="55a2e-192">*Color picker Opacity*</span></span>

    > [!NOTE]
    > <span data-ttu-id="55a2e-193">A definição de cor RGBA (vermelho, verde, azul, Alpha) no CSS3 permite que você defina o valor da opacidade da cor de um único item.</span><span class="sxs-lookup"><span data-stu-id="55a2e-193">The RGBA (Red, Green, Blue, Alpha) color definition in CSS3 enables you to define the color opacity value for a single item.</span></span> <span data-ttu-id="55a2e-194">Ao contrário de **opacidade -** um atributo CSS semelhante  **-**  RGBA cores também são compatíveis com os navegadores mais recentes.</span><span class="sxs-lookup"><span data-stu-id="55a2e-194">Unlike **opacity -** a similar CSS attribute **-** RGBA colors are also compatible with the latest browsers.</span></span>

<a id="Ex1Task3"></a>

<a id="Task_3_-_CSS_Compatible_Code_Snippets"></a>
#### <a name="task-3---css-compatible-code-snippets"></a><span data-ttu-id="55a2e-195">Tarefa 3 - trechos de código compatível de CSS</span><span class="sxs-lookup"><span data-stu-id="55a2e-195">Task 3 - CSS Compatible Code Snippets</span></span>

<span data-ttu-id="55a2e-196">Nesta tarefa, você aprenderá como usar trechos de CSS3 compatíveis entre navegadores para implementar alguns recursos no seu site.</span><span class="sxs-lookup"><span data-stu-id="55a2e-196">In this task, you will learn how to use cross-browser compatible CSS3 snippets in order to implement some features in your website.</span></span>

1. <span data-ttu-id="55a2e-197">No **Site.css** de arquivo, localize o **cabeçalho** CSS (.header) de definição de classe e coloque o cursor abaixo o  **/ \*raio de borda\* /**  espaço reservado para adicionar um novo trecho de código.</span><span class="sxs-lookup"><span data-stu-id="55a2e-197">In the **Site.css** file, locate the **header** CSS class definition (.header) and place the cursor below the **/\*border radius\*/** placeholder to add a new snippet.</span></span> <span data-ttu-id="55a2e-198">Pressione **Enter** para exibir a lista do IntelliSense e o tipo **radius** para filtrar a lista.</span><span class="sxs-lookup"><span data-stu-id="55a2e-198">Press **Enter** to display the IntelliSense list and type **radius** to filter the list.</span></span> <span data-ttu-id="55a2e-199">Selecione o **border-radius** opção da lista com um clique duplo e, em seguida, pressione a **guia** chave para inserir o trecho de código.</span><span class="sxs-lookup"><span data-stu-id="55a2e-199">Select the **border-radius** option from the list with a double click, and then press the **TAB** key to insert the snippet.</span></span> <span data-ttu-id="55a2e-200">Em seguida, digite um tamanho de radius em pixels e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-200">Then, type a radius size in pixels and press **Enter**.</span></span> <span data-ttu-id="55a2e-201">Por exemplo, digite **15px**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-201">For instance, type **15px**.</span></span>

    <span data-ttu-id="55a2e-202">Os atributos de CSS3 adicionados pelo trecho de código serão renderizado bordas arredondadas na maioria dos navegadores de conformidade do HTML5, incluindo Mozilla e navegadores com base em WebKit.</span><span class="sxs-lookup"><span data-stu-id="55a2e-202">The CSS3 attributes added by the snippet will render rounded borders in most HTML5 compliance browsers, including Mozilla and WebKit-based browsers.</span></span>

    <span data-ttu-id="55a2e-203">![Usando um trecho de código border-radius](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image17.png "usando um trecho de código border-radius")</span><span class="sxs-lookup"><span data-stu-id="55a2e-203">![Using a border-radius snippet](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image17.png "Using a border-radius snippet")</span></span>

    <span data-ttu-id="55a2e-204">*Usando um trecho de código border-radius*</span><span class="sxs-lookup"><span data-stu-id="55a2e-204">*Using a border-radius snippet*</span></span>
2. <span data-ttu-id="55a2e-205">Aplicar a mesma **borda** trechos de código no estilo de página (.page).</span><span class="sxs-lookup"><span data-stu-id="55a2e-205">Apply the same **border** snippets in the page style (.page).</span></span>

    <span data-ttu-id="55a2e-206">CSS</span><span class="sxs-lookup"><span data-stu-id="55a2e-206">CSS</span></span>

    [!code-css[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample2.css)]
3. <span data-ttu-id="55a2e-207">Pressione **F5** para executar a solução.</span><span class="sxs-lookup"><span data-stu-id="55a2e-207">Press **F5** to run the solution.</span></span> <span data-ttu-id="55a2e-208">Observe que cada página agora tem arredondados bordas.</span><span class="sxs-lookup"><span data-stu-id="55a2e-208">Notice that each page now has rounded borders.</span></span>

    <span data-ttu-id="55a2e-209">![Cantos arredondados](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image18.png "cantos arredondados")</span><span class="sxs-lookup"><span data-stu-id="55a2e-209">![Rounded corners](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image18.png "Rounded corners")</span></span>

    <span data-ttu-id="55a2e-210">*Cantos arredondados*</span><span class="sxs-lookup"><span data-stu-id="55a2e-210">*Rounded corners*</span></span>
4. <span data-ttu-id="55a2e-211">Feche o navegador e retorne ao Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="55a2e-211">Close the browser and return to Visual Studio.</span></span>
5. <span data-ttu-id="55a2e-212">Abrir o **Custom.css** arquivo localizado sob o **estilos** pasta e coloque o cursor dentro **img de li ul div.images** definição da classe.</span><span class="sxs-lookup"><span data-stu-id="55a2e-212">Open the **Custom.css** file located under the **Styles** folder and place the cursor inside **div.images ul li img** class definition.</span></span>
6. <span data-ttu-id="55a2e-213">Pressione enter para exibir a lista do IntelliSense, tipo **caixa sombra** e pressione a **guia** chave duas vezes para inserir o trecho de código de sombra padrão dentro da definição de classe.</span><span class="sxs-lookup"><span data-stu-id="55a2e-213">Press enter to display the IntelliSense list, type **box-shadow** and press the **TAB** key twice to insert the default shadow code snippet inside the class definition.</span></span> <span data-ttu-id="55a2e-214">Defina os valores de sombra para **10px 10px 5px &#888;**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-214">Set the shadow values to **10px 10px 5px #888**.</span></span> <span data-ttu-id="55a2e-215">Em seguida, digite **border-radius** e inserir o trecho de código.</span><span class="sxs-lookup"><span data-stu-id="55a2e-215">Then, type **border-radius** and insert the code snippet.</span></span> <span data-ttu-id="55a2e-216">Tipo **15px** para definir o tamanho de radius e pressione **ENTER**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-216">Type **15px** to set radius size and press **ENTER**.</span></span>

    <span data-ttu-id="55a2e-217">![Arredondar os cantos com sombra](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image19.png "arredondado cantos com sombra")</span><span class="sxs-lookup"><span data-stu-id="55a2e-217">![Rounded corners with shadow](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image19.png "Rounded corners with shadow")</span></span>

    <span data-ttu-id="55a2e-218">*Cantos arredondados com sombra*</span><span class="sxs-lookup"><span data-stu-id="55a2e-218">*Rounded corners with shadow*</span></span>

    > [!NOTE]
    > <span data-ttu-id="55a2e-219">Neste momento, o atributo de sombra é inserido com o prefixo correspondente (moz webkit, s) para dar suporte ao Mozilla e navegadores Webkit (Chrome, Safari, Konkeror).</span><span class="sxs-lookup"><span data-stu-id="55a2e-219">At this moment, the shadow attribute is inserted with the corresponding prefix (moz, webkit, o) to support Mozilla and Webkit (Chrome, Safari, Konkeror) browsers.</span></span>
7. <span data-ttu-id="55a2e-220">Criar uma nova classe **img:hover de li ul div.images** abaixo o **img de li ul div.images** definição da classe e coloque o cursor dentro dos colchetes **.**</span><span class="sxs-lookup"><span data-stu-id="55a2e-220">Create a new class **div.images ul li img:hover** below the **div.images ul li img** class definition and place the cursor inside the brackets **.**</span></span>

    <span data-ttu-id="55a2e-221">CSS</span><span class="sxs-lookup"><span data-stu-id="55a2e-221">CSS</span></span>

    [!code-css[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample3.css)]
8. <span data-ttu-id="55a2e-222">Tipo **transformação** e pressione a **guia** chave duas vezes para inserir o trecho de código de transformação.</span><span class="sxs-lookup"><span data-stu-id="55a2e-222">Type **transform** and press the **TAB** key twice in order to insert the transform snippet.</span></span> <span data-ttu-id="55a2e-223">Em seguida, insira **rotate(-15deg)** para alterar o valor do ângulo de rotação quando imagens são colocadas.</span><span class="sxs-lookup"><span data-stu-id="55a2e-223">Then, enter **rotate(-15deg)** to change the rotation angle value when images are hovered.</span></span>

    <span data-ttu-id="55a2e-224">CSS</span><span class="sxs-lookup"><span data-stu-id="55a2e-224">CSS</span></span>

    [!code-css[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample4.css)]
9. <span data-ttu-id="55a2e-225">Pressione **F5** para executar a solução e navegue até a página CSS3.</span><span class="sxs-lookup"><span data-stu-id="55a2e-225">Press **F5** to run the solution and browse to the CSS3 page.</span></span> <span data-ttu-id="55a2e-226">Observe que as imagens tem cantos arredondados e sombras de caixa.</span><span class="sxs-lookup"><span data-stu-id="55a2e-226">Notice that the images have rounded corners and box shadows.</span></span> <span data-ttu-id="55a2e-227">Passe o mouse sobre as imagens e assista a girar.</span><span class="sxs-lookup"><span data-stu-id="55a2e-227">Hover the mouse over the images and watch them rotate.</span></span>

    <span data-ttu-id="55a2e-228">![Girar uma imagem de trecho de código de transformação](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image20.png "transformação trecho girar uma imagem")</span><span class="sxs-lookup"><span data-stu-id="55a2e-228">![Transform snippet rotating an image](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image20.png "Transform snippet rotating an image")</span></span>

    <span data-ttu-id="55a2e-229">*Transformar o trecho de rotação de uma imagem*</span><span class="sxs-lookup"><span data-stu-id="55a2e-229">*Transform snippet rotating an image*</span></span>

    > [!NOTE]
    > <span data-ttu-id="55a2e-230">Se você estiver usando o Internet Explorer 10 e não pode ver as sombras, verifique se que o modo de documento é definido como padrões do IE10.</span><span class="sxs-lookup"><span data-stu-id="55a2e-230">If you are using Internet Explorer 10 and cannot see the shadows, make sure the document mode is set to IE10 standards.</span></span> <span data-ttu-id="55a2e-231">Pressione **F12** para abrir as ferramentas de desenvolvedor do Internet Explorer e clique em **modo de documento** para alterar para padrões do IE10.</span><span class="sxs-lookup"><span data-stu-id="55a2e-231">Press **F12** to open Internet Explorer developer tools and click **Document Mode** to change to IE10 standards.</span></span>

    ![sobre-us](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image21.png)

<a id="Exercise2"></a>

<a id="Exercise_2_Whats_New_in_the_HTML_Editor"></a>
### <a name="exercise-2-whats-new-in-the-html-editor"></a><span data-ttu-id="55a2e-233">Exercício 2: O que há de novo no Editor de HTML</span><span class="sxs-lookup"><span data-stu-id="55a2e-233">Exercise 2: What's New in the HTML Editor</span></span>

<span data-ttu-id="55a2e-234">O Visual Studio tem um editor de HTML aprimorado.</span><span class="sxs-lookup"><span data-stu-id="55a2e-234">Visual Studio has an improved HTML editor.</span></span> <span data-ttu-id="55a2e-235">Algumas das melhorias incluídas nesta versão são recuo inteligente em documentos HTML, trechos de código do HTML5, início HTML e correspondência de marca de fim e validação de HTML.</span><span class="sxs-lookup"><span data-stu-id="55a2e-235">Some of the enhancements included in this version are smart indentation in HTML documents, HTML5 snippets, HTML start and end tag matching, and HTML validation.</span></span> <span data-ttu-id="55a2e-236">Ao longo deste exercício, você verá como essas alterações melhorar seu fluência ao trabalhar na marcação de site.</span><span class="sxs-lookup"><span data-stu-id="55a2e-236">Throughout this exercise, you will see how these changes improve your fluency when working in the website markup.</span></span>

<span data-ttu-id="55a2e-237">Como o editor de CSS, editor de HTML também foi aprimorado.</span><span class="sxs-lookup"><span data-stu-id="55a2e-237">Like the CSS editor, the HTML editor was also improved.</span></span> <span data-ttu-id="55a2e-238">A maioria dessas melhorias é pequenos que facilitam a vida do desenvolvedor da Web.</span><span class="sxs-lookup"><span data-stu-id="55a2e-238">Most of these improvements are small ones that make the Web developer's life easier.</span></span> <span data-ttu-id="55a2e-239">Coisas como mais trechos de código para HTML5, recuo inteligente, correspondência de marcas de início e término quando edição e validação direcionando o documento HTML DOCTYPE são algumas dessas melhorias.</span><span class="sxs-lookup"><span data-stu-id="55a2e-239">Things like more code snippets for HTML5, smart indentation, matching start and end tags when editing and validation targeting the HTML document DOCTYPE are some of these improvements.</span></span>

<a id="Ex2Task1"></a>

<a id="Task_1_-_Improved_DOCTYPE_Validation"></a>
#### <a name="task-1---improved-doctype-validation"></a><span data-ttu-id="55a2e-240">Tarefa 1 - validação de DOCTYPE aprimorado</span><span class="sxs-lookup"><span data-stu-id="55a2e-240">Task 1 - Improved DOCTYPE Validation</span></span>

<span data-ttu-id="55a2e-241">O editor de HTML agora tem a capacidade de verificar o tipo de documento da página, mesmo que a definição possa ser na página mestra.</span><span class="sxs-lookup"><span data-stu-id="55a2e-241">The HTML editor now has the ability to check the DOCTYPE of your page, even though the definition might be in the master page.</span></span> <span data-ttu-id="55a2e-242">Dependendo do DOCTYPE da página, o editor de HTML será validado com o conjunto correto de regras e filtra a lista de IntelliSense considerando os elementos de tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="55a2e-242">Depending on the DOCTYPE of your page, the HTML editor will validate with the correct set of rules and will filter the IntelliSense list considering the DOCTYPE elements.</span></span>

<span data-ttu-id="55a2e-243">Nesta tarefa, você alterará o tipo de documento de uma página para ver como o comportamento do editor de HTML alterada de acordo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-243">In this task, you will change the DOCTYPE of a page to see how the HTML editor behavior changes accordingly.</span></span>

1. <span data-ttu-id="55a2e-244">Se ainda não estiver aberto, inicie **Visual Studio** e abra o **WhatsNewASPNET.sln** solução localizada no **Source\WhatsNewASPNET** pasta deste laboratório.</span><span class="sxs-lookup"><span data-stu-id="55a2e-244">If not already opened, start **Visual Studio** and open the **WhatsNewASPNET.sln** solution located in the **Source\WhatsNewASPNET** folder of this lab.</span></span>
2. <span data-ttu-id="55a2e-245">Abra o **Site.Master** página.</span><span class="sxs-lookup"><span data-stu-id="55a2e-245">Open the **Site.Master** page.</span></span>
3. <span data-ttu-id="55a2e-246">Observe o esquema de destino para a barra de ferramentas de validação.</span><span class="sxs-lookup"><span data-stu-id="55a2e-246">Notice the Target Schema for Validation Toolbar.</span></span> <span data-ttu-id="55a2e-247">O comportamento do editor de HTML (validação, IntelliSense, etc.) será alterado corretamente de acordo com o tipo de documento selecionado.</span><span class="sxs-lookup"><span data-stu-id="55a2e-247">The way the HTML editor behaves (Validation, IntelliSense, etc.) will properly change to fit the Doctype selected.</span></span>

    <span data-ttu-id="55a2e-248">![Use o Doctype na barra de ferramentas de edição de código HTML](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image22.png "Doctype Use na barra de ferramentas de edição de código HTML")</span><span class="sxs-lookup"><span data-stu-id="55a2e-248">![Use Doctype in HTML Source Editing toolbar](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image22.png "Use Doctype in HTML Source Editing toolbar")</span></span>

    <span data-ttu-id="55a2e-249">*Use o Doctype na barra de ferramentas de edição de código HTML*</span><span class="sxs-lookup"><span data-stu-id="55a2e-249">*Use Doctype in HTML Source Editing toolbar*</span></span>
4. <span data-ttu-id="55a2e-250">Altere o esquema de destino para HTML 4.01.</span><span class="sxs-lookup"><span data-stu-id="55a2e-250">Change the Target Schema to HTML 4.01.</span></span>

    <span data-ttu-id="55a2e-251">![Alterando tipo de documento na barra de ferramentas de edição de código HTML](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image23.png "alterando o tipo de documento na barra de ferramentas de edição de código HTML")</span><span class="sxs-lookup"><span data-stu-id="55a2e-251">![Changing Doctype in HTML Source Editing toolbar](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image23.png "Changing Doctype in HTML Source Editing toolbar")</span></span>

    <span data-ttu-id="55a2e-252">*Alterando tipo de documento na barra de ferramentas de edição de código HTML*</span><span class="sxs-lookup"><span data-stu-id="55a2e-252">*Changing Doctype in HTML Source Editing toolbar*</span></span>
5. <span data-ttu-id="55a2e-253">Posicione o cursor sob o **corpo** elemento e comece a digitar o nome de um elemento de HTML5 (por exemplo, **vídeo**).</span><span class="sxs-lookup"><span data-stu-id="55a2e-253">Place the cursor under the **body** element, and start typing the name of an HTML5 element (for example, **video**).</span></span> <span data-ttu-id="55a2e-254">Observe que o elemento não está disponível na lista do IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="55a2e-254">Notice that the element is not available in the IntelliSense list.</span></span>

    <span data-ttu-id="55a2e-255">![Elementos de HTML5 não listados](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image24.png "elementos HTML5 não listados")</span><span class="sxs-lookup"><span data-stu-id="55a2e-255">![HTML5 elements not listed](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image24.png "HTML5 elements not listed")</span></span>

    <span data-ttu-id="55a2e-256">*Elementos de HTML5 não listados*</span><span class="sxs-lookup"><span data-stu-id="55a2e-256">*HTML5 elements not listed*</span></span>
6. <span data-ttu-id="55a2e-257">Desfazer as alterações no esquema de destino para validação de ferramentas, escolhendo o tipo de documento: XHTML5 na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="55a2e-257">Undo the changes to the Target Schema for Validation Toolbar, picking DOCTYPE: XHTML5 from the dropdown list.</span></span>

    <span data-ttu-id="55a2e-258">![Use o Doctype na barra de ferramentas de edição de código HTML](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image25.png "Doctype Use na barra de ferramentas de edição de código HTML")</span><span class="sxs-lookup"><span data-stu-id="55a2e-258">![Use Doctype in HTML Source Editing toolbar](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image25.png "Use Doctype in HTML Source Editing toolbar")</span></span>

    <span data-ttu-id="55a2e-259">*Redefinir Doctype na barra de ferramentas de edição de código HTML*</span><span class="sxs-lookup"><span data-stu-id="55a2e-259">*Reset Doctype in HTML Source Editing toolbar*</span></span>
7. <span data-ttu-id="55a2e-260">Colocar o cursor sob o **corpo** elemento e comece a digitar um elemento HTML5 novamente (por exemplo, como **vídeo**).</span><span class="sxs-lookup"><span data-stu-id="55a2e-260">Place the cursor under the **body** element and start typing an HTML5 element again (For example, like **video**).</span></span> <span data-ttu-id="55a2e-261">Observe que os elementos do HTML5 agora estão disponíveis na lista do IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="55a2e-261">Notice that the HTML5 elements are now available in the IntelliSense list.</span></span>

    <span data-ttu-id="55a2e-262">![Elementos de HTML5 sendo listados](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image26.png "elementos HTML5 sendo listados")</span><span class="sxs-lookup"><span data-stu-id="55a2e-262">![HTML5 elements being listed](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image26.png "HTML5 elements being listed")</span></span>

    <span data-ttu-id="55a2e-263">*Elementos de HTML5 sendo listados*</span><span class="sxs-lookup"><span data-stu-id="55a2e-263">*HTML5 elements being listed*</span></span>

<a id="Ex2Task2"></a>

<a id="Task_2_-_StartEnd_Tags_Automatic_Update"></a>
#### <a name="task-2---startend-tags-automatic-update"></a><span data-ttu-id="55a2e-264">Tarefa 2 - início/término atualização automática de marcas</span><span class="sxs-lookup"><span data-stu-id="55a2e-264">Task 2 - Start/End Tags Automatic Update</span></span>

<span data-ttu-id="55a2e-265">Agora, o Visual Studio atualiza o HTML abrir ou fechar marcas do elemento que você está editando para corresponder um ao outro.</span><span class="sxs-lookup"><span data-stu-id="55a2e-265">Visual Studio now updates the HTML opening or closing tags of the element that you are editing to match each other.</span></span> <span data-ttu-id="55a2e-266">Esse novo recurso melhora a sua produtividade ao editar marcas HTML.</span><span class="sxs-lookup"><span data-stu-id="55a2e-266">This new feature will improve your productivity when editing HTML tags.</span></span>

1. <span data-ttu-id="55a2e-267">Sobre o **Default.aspx** página, adicione um **H3** elemento com um título (por exemplo, o Visual Studio 2012 Rocks!).</span><span class="sxs-lookup"><span data-stu-id="55a2e-267">On the **Default.aspx** page, add an **H3** element with a title (for example, Visual Studio 2012 Rocks!).</span></span>


    [!code-aspx[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample5.aspx)]
2. <span data-ttu-id="55a2e-268">Alterar o **H3** marca e o tipo **H2** ou **H1.**</span><span class="sxs-lookup"><span data-stu-id="55a2e-268">Change the **H3** tag and type **H2** or **H1.**</span></span>

    <span data-ttu-id="55a2e-269">Observe que a marca de fim atualiza automaticamente.</span><span class="sxs-lookup"><span data-stu-id="55a2e-269">Notice that the end tag automatically updates.</span></span> <span data-ttu-id="55a2e-270">Você também pode modificar a marca de fim para ver se a marca de início atualiza muito.</span><span class="sxs-lookup"><span data-stu-id="55a2e-270">You can also modify the end tag to see that the start tag updates accordingly too.</span></span>

    <span data-ttu-id="55a2e-271">![Atualização automática da marca de fim](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image27.png "atualização automática da marca de fim")</span><span class="sxs-lookup"><span data-stu-id="55a2e-271">![Automatic update of the end tag](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image27.png "Automatic update of the end tag")</span></span>

    <span data-ttu-id="55a2e-272">*Atualização automática da marca de fim*</span><span class="sxs-lookup"><span data-stu-id="55a2e-272">*Automatic update of the end tag*</span></span>

<a id="Ex2Task3"></a>

<a id="Task_3_-_New_HTML5_Code_Snippets"></a>
#### <a name="task-3---new-html5-code-snippets"></a><span data-ttu-id="55a2e-273">Tarefa 3 - novos trechos de código do HTML5</span><span class="sxs-lookup"><span data-stu-id="55a2e-273">Task 3 - New HTML5 Code Snippets</span></span>

<span data-ttu-id="55a2e-274">O Visual Studio agora inclui vários trechos de código do HTML5.</span><span class="sxs-lookup"><span data-stu-id="55a2e-274">Visual Studio now includes several HTML5 code snippets.</span></span> <span data-ttu-id="55a2e-275">Nesta tarefa, você irá usar alguns dos trechos de código.</span><span class="sxs-lookup"><span data-stu-id="55a2e-275">In this task, you will use some of these snippets.</span></span>

1. <span data-ttu-id="55a2e-276">Adicionar uma nova pasta chamada **áudio** para a raiz da pasta do site.</span><span class="sxs-lookup"><span data-stu-id="55a2e-276">Add a new folder named **audio** to the root of the web site folder.</span></span> <span data-ttu-id="55a2e-277">Abra o Windows Explorer e copie qualquer arquivo de áudio para o **áudio** pasta o **WhatsNewASPNET.sln** solução.</span><span class="sxs-lookup"><span data-stu-id="55a2e-277">Open Windows Explorer and copy any audio file into the **audio** folder of the **WhatsNewASPNET.sln** solution.</span></span>
2. <span data-ttu-id="55a2e-278">No **Default.aspx** , localize o cursor sob o Rocks Web11!!</span><span class="sxs-lookup"><span data-stu-id="55a2e-278">In the **Default.aspx** page, locate the cursor under the Web11 Rocks!!</span></span> <span data-ttu-id="55a2e-279">Cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="55a2e-279">Header.</span></span> <span data-ttu-id="55a2e-280">Tipo **áudio** e pressione a tecla TAB.</span><span class="sxs-lookup"><span data-stu-id="55a2e-280">Type **audio** and press the TAB key.</span></span>

    <span data-ttu-id="55a2e-281">O novo editor de HTML inclui trechos de código para o conteúdo do HTML5.</span><span class="sxs-lookup"><span data-stu-id="55a2e-281">The new HTML editor includes code snippets for HTML5 content.</span></span> <span data-ttu-id="55a2e-282">Lembre-se de usar a definição de DOCTYPE adequada para habilitar os trechos de código do HTML5.</span><span class="sxs-lookup"><span data-stu-id="55a2e-282">Remember to use the proper DOCTYPE definition to enable the HTML5 snippets.</span></span>

    <span data-ttu-id="55a2e-283">![Inserir trechos de código do HTML5](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image28.png "inserir trechos de código do HTML5")</span><span class="sxs-lookup"><span data-stu-id="55a2e-283">![Inserting HTML5 Code Snippets](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image28.png "Inserting HTML5 Code Snippets")</span></span>

    <span data-ttu-id="55a2e-284">*Inserir trechos de código do HTML5*</span><span class="sxs-lookup"><span data-stu-id="55a2e-284">*Inserting HTML5 Code Snippets*</span></span>
3. <span data-ttu-id="55a2e-285">Atualize a fonte de áudio para apontar para um arquivo de áudio existente.</span><span class="sxs-lookup"><span data-stu-id="55a2e-285">Update the audio source to point to an existing audio file.</span></span>


    [!code-aspx[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample6.aspx)]

    > [!NOTE]
    > <span data-ttu-id="55a2e-286">Você precisará adicionar o arquivo de áudio para a solução.</span><span class="sxs-lookup"><span data-stu-id="55a2e-286">You will need to add the audio file to the solution.</span></span>
4. <span data-ttu-id="55a2e-287">Pressione **F5** para executar o site e executar o áudio.</span><span class="sxs-lookup"><span data-stu-id="55a2e-287">Press **F5** to run the site and play the audio.</span></span>

    <span data-ttu-id="55a2e-288">![Executar o controle de áudio](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image29.png "executando o controle de áudio")</span><span class="sxs-lookup"><span data-stu-id="55a2e-288">![Running the audio control](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image29.png "Running the audio control")</span></span>

    <span data-ttu-id="55a2e-289">*Executar o controle de áudio*</span><span class="sxs-lookup"><span data-stu-id="55a2e-289">*Running the audio control*</span></span>

    > [!NOTE]
    > <span data-ttu-id="55a2e-290">Você também pode tentar trechos de código mais incluídos no Visual Studio, como vídeo figura, etc.</span><span class="sxs-lookup"><span data-stu-id="55a2e-290">You can also try more snippets included in Visual Studio, such as video, figure, etc.</span></span>
5. <span data-ttu-id="55a2e-291">Agora, tente inserir um controle em alguma parte da página.</span><span class="sxs-lookup"><span data-stu-id="55a2e-291">Now, try to insert a control in some part of the page.</span></span> <span data-ttu-id="55a2e-292">Por exemplo, tente inserir uma **GridView** controle, mas em vez de digitar  **&lt;Gri,** comece a digitar  **&lt;GV**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-292">For example, try to insert a **GridView** control, but instead of typing **&lt;Gri,** start typing **&lt;GV**.</span></span> <span data-ttu-id="55a2e-293">Observe que a lista de IntelliSense mostra o **asp: GridView** controle.</span><span class="sxs-lookup"><span data-stu-id="55a2e-293">Notice that the IntelliSense list shows the **asp:GridView** control.</span></span>

    <span data-ttu-id="55a2e-294">Agora, o IntelliSense no Editor de HTML fornece pesquisa de título de maiusculas e minúsculas, bem como parcial correspondente (recuperação de todos os elementos que contém o termo).</span><span class="sxs-lookup"><span data-stu-id="55a2e-294">IntelliSense in the HTML Editor now provides title-casing search, as well as partial matching (retrieving all elements that contains the term).</span></span>

    <span data-ttu-id="55a2e-295">![Inserindo um GridView com listas do IntelliSense](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image30.png "inserindo um GridView com listas do IntelliSense")</span><span class="sxs-lookup"><span data-stu-id="55a2e-295">![Inserting a GridView with IntelliSense lists](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image30.png "Inserting a GridView with IntelliSense lists")</span></span>

    <span data-ttu-id="55a2e-296">*Inserindo um GridView com listas do IntelliSense*</span><span class="sxs-lookup"><span data-stu-id="55a2e-296">*Inserting a GridView with IntelliSense lists*</span></span>

    <span data-ttu-id="55a2e-297">Se você digitar  **&lt;grade** você obterá todos os itens que correspondem ao termo, mas o Visual Studio irá sugerir o **gridview** controle:</span><span class="sxs-lookup"><span data-stu-id="55a2e-297">If you type **&lt;grid** you will get all the items that match the term, but Visual Studio will suggest the **gridview** control:</span></span>

    <span data-ttu-id="55a2e-298">![Inserindo um GridView com listas do IntelliSense e a correspondência parcial](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image31.png "inserindo um GridView com listas do IntelliSense e a correspondência parcial")</span><span class="sxs-lookup"><span data-stu-id="55a2e-298">![Inserting a GridView with IntelliSense lists and partial matching](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image31.png "Inserting a GridView with IntelliSense lists and partial matching")</span></span>

    <span data-ttu-id="55a2e-299">*Inserindo um GridView com listas do IntelliSense e a correspondência parcial*</span><span class="sxs-lookup"><span data-stu-id="55a2e-299">*Inserting a GridView with IntelliSense lists and partial matching*</span></span>

<a id="Ex2Task4"></a>

<a id="Task_4_-_HTML_Editor_Smart_Tags"></a>
#### <a name="task-4---html-editor-smart-tags"></a><span data-ttu-id="55a2e-300">Tarefa 4 - marcas inteligentes de Editor de HTML</span><span class="sxs-lookup"><span data-stu-id="55a2e-300">Task 4 - HTML Editor Smart Tags</span></span>

<span data-ttu-id="55a2e-301">Outro aprimoramento no Editor de HTML é o recurso de marcas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="55a2e-301">Another improvement in the HTML Editor is the Smart Tags feature.</span></span> <span data-ttu-id="55a2e-302">Marcas inteligentes tornam mais fácil executar tarefas de desenvolvimento comuns ou repetitivas em uma base por controle.</span><span class="sxs-lookup"><span data-stu-id="55a2e-302">Smart tags make it easy to perform common or repetitive development tasks on a per-control basis.</span></span> <span data-ttu-id="55a2e-303">Esse recurso já estava disponível no Designer de HTML, mas não no Editor de HTML.</span><span class="sxs-lookup"><span data-stu-id="55a2e-303">This feature was already available in the HTML Designer, but not in the HTML Editor.</span></span>

1. <span data-ttu-id="55a2e-304">Abra **Site.Master** e localize o **asp: Menu** elemento.</span><span class="sxs-lookup"><span data-stu-id="55a2e-304">Open **Site.Master** and locate the **asp:Menu** element.</span></span> <span data-ttu-id="55a2e-305">Posicione o cursor na marca de início e observe que o glifo pequeno exibido na parte inferior do elemento - clique nele para abrir o menu de tarefas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="55a2e-305">Place the cursor on the start tag and notice that the small glyph displayed at the bottom of the element - click it to open the smart tasks menu.</span></span> <span data-ttu-id="55a2e-306">Observe que você tem acesso rápido a algumas tarefas relacionadas ao controle de Menu.</span><span class="sxs-lookup"><span data-stu-id="55a2e-306">Notice that you have quick access to some tasks related to the Menu control.</span></span>

    <span data-ttu-id="55a2e-307">![Inteligentes de tarefas para o controle de Menu](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image32.png "inteligentes de tarefas para o controle de Menu")</span><span class="sxs-lookup"><span data-stu-id="55a2e-307">![Smart tasks for the Menu control](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image32.png "Smart tasks for the Menu control")</span></span>

    <span data-ttu-id="55a2e-308">*Tarefas inteligentes para o controle de Menu*</span><span class="sxs-lookup"><span data-stu-id="55a2e-308">*Smart tasks for the Menu control*</span></span>

<a id="Ex2Task5"></a>

<a id="Task_5_-_Smart_Indentation"></a>
#### <a name="task-5---smart-indentation"></a><span data-ttu-id="55a2e-309">Tarefa 5: recuo inteligente</span><span class="sxs-lookup"><span data-stu-id="55a2e-309">Task 5 - Smart Indentation</span></span>

<span data-ttu-id="55a2e-310">Uma das melhores práticas em HTML é recuo dos elementos aninhados para manter o código legível.</span><span class="sxs-lookup"><span data-stu-id="55a2e-310">One of the best practices in HTML is indenting the nested elements to keep the code readable.</span></span> <span data-ttu-id="55a2e-311">No Visual Studio 2012, você observará que o editor recua automaticamente os elementos enquanto você estiver escrevendo o código.</span><span class="sxs-lookup"><span data-stu-id="55a2e-311">In Visual Studio 2012, you will notice that the editor automatically indents the elements while you are writing the code.</span></span>

> [!NOTE]
> <span data-ttu-id="55a2e-312">Na versão anterior do Visual Studio, o recuo inteligente estava disponível no editor de XML, mas não no editor de HTML.</span><span class="sxs-lookup"><span data-stu-id="55a2e-312">In previous version of Visual Studio, smart indentation was available in the XML editor but not in the HTML editor.</span></span>


1. <span data-ttu-id="55a2e-313">Certifique-se de que a configuração de recuo no Editor de HTML é definida como o recuo inteligente.</span><span class="sxs-lookup"><span data-stu-id="55a2e-313">Make sure that the Indenting configuration on the HTML Editor is set to Smart Indentation.</span></span> <span data-ttu-id="55a2e-314">Para fazer isso, selecione o **ferramentas | Opções de** opção de menu e selecione o **Editor de texto | HTML | Guias** página no painel esquerdo da tela.</span><span class="sxs-lookup"><span data-stu-id="55a2e-314">To do that, select the **Tools | Options** menu option and then select the **Text Editor | HTML | Tabs** page in the left pane of the screen.</span></span> <span data-ttu-id="55a2e-315">Selecione a opção de recuo inteligente.</span><span class="sxs-lookup"><span data-stu-id="55a2e-315">Select the Smart indentation option.</span></span>

    <span data-ttu-id="55a2e-316">![Configurações do Editor de HTML](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image33.png "configurações do Editor de HTML")</span><span class="sxs-lookup"><span data-stu-id="55a2e-316">![HTML Editor settings](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image33.png "HTML Editor settings")</span></span>

    <span data-ttu-id="55a2e-317">*Configurações do Editor de HTML*</span><span class="sxs-lookup"><span data-stu-id="55a2e-317">*HTML Editor settings*</span></span>
2. <span data-ttu-id="55a2e-318">Sobre o **Default.aspx** página, remova todo o conteúdo sob o elemento de áudio.</span><span class="sxs-lookup"><span data-stu-id="55a2e-318">On the **Default.aspx** page, remove all the content under the audio element.</span></span>
3. <span data-ttu-id="55a2e-319">Posicione o cursor no final da abertura **áudio** elemento e pressione **ENTER**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-319">Place the cursor at the end of the opening **audio** element and hit **ENTER**.</span></span>

    <span data-ttu-id="55a2e-320">Observe que a nova posição do cursor tem um nível de recuo adicional.</span><span class="sxs-lookup"><span data-stu-id="55a2e-320">Notice that the new position of cursor has an additional indentation level.</span></span>

    <span data-ttu-id="55a2e-321">![Inteligente recuo no Editor de HTML](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image34.png "inteligente recuo no Editor de HTML")</span><span class="sxs-lookup"><span data-stu-id="55a2e-321">![Smart indentation in the HTML Editor](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image34.png "Smart indentation in the HTML Editor")</span></span>

    <span data-ttu-id="55a2e-322">*Recuo inteligente no Editor de HTML*</span><span class="sxs-lookup"><span data-stu-id="55a2e-322">*Smart indentation in the HTML Editor*</span></span>
4. <span data-ttu-id="55a2e-323">Restaurar a marca de áudio com o conteúdo que você tenha removido, ou feche **Default.aspx** sem salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="55a2e-323">Restore the audio tag with the content you have removed, or close **Default.aspx** without saving the changes.</span></span>

<a id="Ex2Task6"></a>

<a id="Task_6_-_Extract_to_User_Control"></a>
#### <a name="task-6---extract-to-user-control"></a><span data-ttu-id="55a2e-324">Tarefa 6 - extrair para controle de usuário</span><span class="sxs-lookup"><span data-stu-id="55a2e-324">Task 6 - Extract to User Control</span></span>

<span data-ttu-id="55a2e-325">As ferramentas de refatoração incluídas no Visual Studio, como extrair uma parte do código para uma função, são ótimos recursos que facilitam o aprimoramento e a refatoração do código existente.</span><span class="sxs-lookup"><span data-stu-id="55a2e-325">The Refactoring tools included in Visual Studio, such as extracting a portion of code to a function, are great features that facilitate the improvement and the refactoring the existing code.</span></span> <span data-ttu-id="55a2e-326">O representante para páginas ASP.NET seria a extração de código HTML a um controle de usuário.</span><span class="sxs-lookup"><span data-stu-id="55a2e-326">The counterpart for ASP.NET pages would be the extraction of HTML code to a User Control.</span></span> <span data-ttu-id="55a2e-327">Manualmente envolve várias etapas, como criar um novo controle de usuário, mover a seção de código para o controle de usuário, registrando um prefixo de marca do controle de usuário e, finalmente, criando o controle de usuário nas páginas.</span><span class="sxs-lookup"><span data-stu-id="55a2e-327">Doing it manually would involve several steps, like creating a new User Control, moving the code section to the User Control, registering a tag prefix for the User Control, and, finally, instantiating the User Control on the pages.</span></span> <span data-ttu-id="55a2e-328">Agora, o novo *extrair para controle de usuário* ferramenta executa automaticamente todas as etapas para você.</span><span class="sxs-lookup"><span data-stu-id="55a2e-328">Now, the new *Extract to User Control* tool automatically performs all those steps for you.</span></span>

<span data-ttu-id="55a2e-329">Nesta tarefa, você usará o novo extrair a operação de controle de usuário contextual para gerar um novo controle de usuário do código selecionado.</span><span class="sxs-lookup"><span data-stu-id="55a2e-329">In this task, you will use the new Extract to User Control contextual operation to generate a new user control from the selected code.</span></span>

1. <span data-ttu-id="55a2e-330">Sobre o **Default.aspx** página, selecione o **H2** e **áudio** elementos.</span><span class="sxs-lookup"><span data-stu-id="55a2e-330">On the **Default.aspx** page, select the **H2** and **audio** elements.</span></span>
2. <span data-ttu-id="55a2e-331">Clique com o botão direito do mouse e selecione **extrair para controle de usuário**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-331">Right click and select **Extract to User Control**.</span></span>

    <span data-ttu-id="55a2e-332">![Extrair a opção de menu de controle de usuário](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image35.png "extrair a opção de menu de controle de usuário")</span><span class="sxs-lookup"><span data-stu-id="55a2e-332">![Extract to User Control menu option](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image35.png "Extract to User Control menu option")</span></span>

    <span data-ttu-id="55a2e-333">*Extrair a opção de menu de controle de usuário*</span><span class="sxs-lookup"><span data-stu-id="55a2e-333">*Extract to User Control menu option*</span></span>
3. <span data-ttu-id="55a2e-334">Digite um nome para o novo controle de usuário.</span><span class="sxs-lookup"><span data-stu-id="55a2e-334">Type a name for the new user control.</span></span> <span data-ttu-id="55a2e-335">Por exemplo, **Jukebox.ascx**e, em seguida, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-335">For instance, **Jukebox.ascx**, and then click **OK**.</span></span>

    <span data-ttu-id="55a2e-336">![Salvando o controle de usuário extraídos](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image36.png "salvando o controle de usuário extraídos")</span><span class="sxs-lookup"><span data-stu-id="55a2e-336">![Saving the extracted user control](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image36.png "Saving the extracted user control")</span></span>

    <span data-ttu-id="55a2e-337">*Salvando o controle de usuário extraídos*</span><span class="sxs-lookup"><span data-stu-id="55a2e-337">*Saving the extracted user control*</span></span>
4. <span data-ttu-id="55a2e-338">Observe que o código selecionado foi extraído para um controle de usuário e o local original do código selecionado foi substituído por uma instância do novo controle de usuário.</span><span class="sxs-lookup"><span data-stu-id="55a2e-338">Notice that the selected code was extracted to a user control and the original location of the selected code was replaced with an instance of the new user control.</span></span>

    <span data-ttu-id="55a2e-339">![Página é atualizada automaticamente para usar o novo controle de usuário](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image37.png "página é atualizada automaticamente para usar o novo controle de usuário")</span><span class="sxs-lookup"><span data-stu-id="55a2e-339">![Page automatically updated to use the new user control](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image37.png "Page automatically updated to use the new user control")</span></span>

    <span data-ttu-id="55a2e-340">*Página é atualizada automaticamente para usar o novo controle de usuário*</span><span class="sxs-lookup"><span data-stu-id="55a2e-340">*Page automatically updated to use the new user control*</span></span>
5. <span data-ttu-id="55a2e-341">Pressione **F5** para executar a página e verifique se o controle funciona.</span><span class="sxs-lookup"><span data-stu-id="55a2e-341">Press **F5** to run the page and verify that the control works.</span></span>

<a id="Exercise3"></a>

<a id="Exercise_3_Whats_New_in_the_JavaScript_Editor"></a>
### <a name="exercise-3-whats-new-in-the-javascript-editor"></a><span data-ttu-id="55a2e-342">Exercício 3: O que há de novo no Editor de JavaScript</span><span class="sxs-lookup"><span data-stu-id="55a2e-342">Exercise 3: What's New in the JavaScript Editor</span></span>

<span data-ttu-id="55a2e-343">Gravar ou editar o código JavaScript não é uma tarefa fácil, especialmente quando o aplicativo começa a crescem em tamanho e você estiver lidando com longos de arquivos e centenas de funções.</span><span class="sxs-lookup"><span data-stu-id="55a2e-343">Writing or editing JavaScript code is not an easy task, especially when your application starts to grow in size and you find yourself dealing with long files and hundreds of functions.</span></span> <span data-ttu-id="55a2e-344">Os desenvolvedores de script normalmente precisam realizar algum trabalho adicional para manter a legibilidade do código e navegar em arquivos.</span><span class="sxs-lookup"><span data-stu-id="55a2e-344">Script developers usually have to do some extra work to maintain code legibility and navigate across files.</span></span> <span data-ttu-id="55a2e-345">Com a inclusão das bibliotecas JavaScript como jQuery, navegação de script se tornou um desafio devido o comprimento do código.</span><span class="sxs-lookup"><span data-stu-id="55a2e-345">With the inclusion of JavaScript libraries like jQuery, script navigation has become a challenge itself because of the code length.</span></span>

<span data-ttu-id="55a2e-346">O Visual Studio renovou o editor do JavaScript com a promessa de tornar o modo código organizados e acessível.</span><span class="sxs-lookup"><span data-stu-id="55a2e-346">Visual Studio has renewed the JavaScript editor with the promise to make the code mode accessible and organized.</span></span> <span data-ttu-id="55a2e-347">Muitos recursos do Visual Studio que já existiam no c# ou VB editores agora são implementados no editor de JavaScript: Ir para definição, recuo automático, documentação e validação quando você estiver escrevendo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-347">Many Visual Studio features that already existed in C# or VB editors are now implemented in the JavaScript editor: Go To Definition, automatic indentation, documentation and validation when you are writing.</span></span> <span data-ttu-id="55a2e-348">Com a lista do IntelliSense renovada, você terá o catálogo de função JavaScript em suas mãos.</span><span class="sxs-lookup"><span data-stu-id="55a2e-348">With the renewed IntelliSense list you will have the JavaScript function catalog at your fingertips.</span></span>

<span data-ttu-id="55a2e-349">Neste exercício, você aprenderá alguns dos novos recursos e aprimoramentos do editor de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="55a2e-349">In this exercise, you will learn some of the new features and improvements of JavaScript editor.</span></span> <span data-ttu-id="55a2e-350">Você irá procurar arquivos de exemplo e descobrir cada uma das novas características que tornam sua programação JavaScript mais eficiente no Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="55a2e-350">You will browse sample files and discover each of the new characteristics that will make your JavaScript programming more efficient within Visual Studio 2012.</span></span>

<a id="Ex3Task1"></a>

<a id="Task_1_-_JavaScript_Editor_New_Features"></a>
#### <a name="task-1---javascript-editor-new-features"></a><span data-ttu-id="55a2e-351">Tarefa 1: novos recursos do Editor de JavaScript</span><span class="sxs-lookup"><span data-stu-id="55a2e-351">Task 1 - JavaScript Editor New Features</span></span>

<span data-ttu-id="55a2e-352">Essa tarefa apresentará os novos recursos de editor JavaScript, que se concentrar na organização do código e colocar uma melhor experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="55a2e-352">This task will introduce you to some of the new JavaScript editor features, which focus on organizing your code and bringing a better user experience.</span></span>

1. <span data-ttu-id="55a2e-353">Se ainda não estiver aberto, inicie **Visual Studio** e abra o **WhatsNewASPNET.sln** solução localizada no **Source\WhatsNewASPNET** pasta deste laboratório.</span><span class="sxs-lookup"><span data-stu-id="55a2e-353">If not already opened, start **Visual Studio** and open the **WhatsNewASPNET.sln** solution located in the **Source\WhatsNewASPNET** folder of this lab.</span></span>
2. <span data-ttu-id="55a2e-354">Pressione **F5** para executar o aplicativo, em seguida, clique no link de JavaScript, na barra de navegação.</span><span class="sxs-lookup"><span data-stu-id="55a2e-354">Press **F5** to run the application, then click the JavaScript link in the navigation bar.</span></span> <span data-ttu-id="55a2e-355">Atualize a página várias vezes e verificar como os incrementos de contador.</span><span class="sxs-lookup"><span data-stu-id="55a2e-355">Refresh the page several times and check how the counter increments.</span></span>

    <span data-ttu-id="55a2e-356">![Contador de página](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image38.png "contador de página")</span><span class="sxs-lookup"><span data-stu-id="55a2e-356">![Page counter](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image38.png "Page counter")</span></span>

    <span data-ttu-id="55a2e-357">*Contador de página*</span><span class="sxs-lookup"><span data-stu-id="55a2e-357">*Page counter*</span></span>
3. <span data-ttu-id="55a2e-358">Feche o navegador e volte para o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="55a2e-358">Close the browser and go back to Visual Studio.</span></span>
4. <span data-ttu-id="55a2e-359">Abra o **JavaScript.aspx** página e localize o  **&lt;script&gt;**  bloco (mostrado abaixo).</span><span class="sxs-lookup"><span data-stu-id="55a2e-359">Open the **JavaScript.aspx** page and locate the **&lt;script&gt;** block (shown below).</span></span>

    <span data-ttu-id="55a2e-360">O código a seguir usa o armazenamento local do HTML5 para armazenar um *pageLoadCount* variável que armazena o número de vezes que a página foi visitada pelo usuário atual.</span><span class="sxs-lookup"><span data-stu-id="55a2e-360">The following code uses HTML5 local storage to store a *pageLoadCount* variable that stores the number of times the page has been visited by the current user.</span></span> <span data-ttu-id="55a2e-361">Armazenamento local é um banco de dados de chave-valor do lado do cliente introduzido com o padrão de HTML5.</span><span class="sxs-lookup"><span data-stu-id="55a2e-361">Local Storage is a client-side key-value database introduced with the HTML5 standard.</span></span> <span data-ttu-id="55a2e-362">Os dados são salvos no computador local, dentro do navegador do usuário.</span><span class="sxs-lookup"><span data-stu-id="55a2e-362">The data is saved on the local machine, inside the user's browser.</span></span>

    [!code-html[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample7.html)]

    > [!NOTE]
    > <span data-ttu-id="55a2e-363">Certifique-se de que o DOCTYPE é definido para XHTML5 antes de continuar com as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="55a2e-363">Ensure the DOCTYPE is set to XHTML5 before proceeding with the next steps.</span></span>
5. <span data-ttu-id="55a2e-364">Editar o código e observe que o IntelliSense para JavaScript inclui recursos de HTML5, como armazenamento local e seus métodos internos.</span><span class="sxs-lookup"><span data-stu-id="55a2e-364">Edit the code and notice that IntelliSense for JavaScript includes HTML5 features, like local storage, and their inner methods.</span></span>

    <span data-ttu-id="55a2e-365">![Recursos de JavaScript HTML5 em JavaScript](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image39.png "recursos JavaScript HTML5 em JavaScript")</span><span class="sxs-lookup"><span data-stu-id="55a2e-365">![HTML5 JavaScript features in JavaScript](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image39.png "HTML5 JavaScript features in JavaScript")</span></span>

    <span data-ttu-id="55a2e-366">*Recursos de JavaScript HTML5 em JavaScript*</span><span class="sxs-lookup"><span data-stu-id="55a2e-366">*HTML5 JavaScript features in JavaScript*</span></span>
6. <span data-ttu-id="55a2e-367">Clique em qualquer colchete de abertura (**{**) o script de código e observe que os colchetes são realçados.</span><span class="sxs-lookup"><span data-stu-id="55a2e-367">Click any opening bracket (**{**) from the scripting code and notice that the brackets are highlighted.</span></span>

    <span data-ttu-id="55a2e-368">![Colchetes são realçados](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image40.png "colchetes são realçados")</span><span class="sxs-lookup"><span data-stu-id="55a2e-368">![Brackets are highlighted](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image40.png "Brackets are highlighted")</span></span>

    <span data-ttu-id="55a2e-369">*Colchetes são realçados*</span><span class="sxs-lookup"><span data-stu-id="55a2e-369">*Brackets are highlighted*</span></span>
7. <span data-ttu-id="55a2e-370">Remova a função **testAutoAlign()** (selecione as três linhas e você pode usar **CTRL** + **K**; **CTRL** + **U**) e localize o cursor dentro do código de função.</span><span class="sxs-lookup"><span data-stu-id="55a2e-370">Uncomment the function **testAutoAlign()** (select the three lines and you can use **CTRL** + **K**; **CTRL** + **U**) and locate the cursor inside the function code.</span></span> <span data-ttu-id="55a2e-371">Pressione enter para acrescentar uma segunda linha.</span><span class="sxs-lookup"><span data-stu-id="55a2e-371">Press enter to append a second line.</span></span> <span data-ttu-id="55a2e-372">Observe que o código é agora **alinhado** e **recuada automaticamente**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-372">Notice that the code is now **aligned** and **auto-indented**.</span></span>

    <span data-ttu-id="55a2e-373">![O código JavaScript é automaticamente alinhado](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image41.png "código JavaScript é automaticamente alinhado")</span><span class="sxs-lookup"><span data-stu-id="55a2e-373">![JavaScript code is auto aligned](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image41.png "JavaScript code is auto aligned")</span></span>

    <span data-ttu-id="55a2e-374">*O código JavaScript é automaticamente alinhado*</span><span class="sxs-lookup"><span data-stu-id="55a2e-374">*JavaScript code is auto aligned*</span></span>

<a id="Ex3Task2"></a>

<a id="Task_2_-_Validating_JavaScript"></a>
#### <a name="task-2---validating-javascript"></a><span data-ttu-id="55a2e-375">Tarefa 2 - validação de JavaScript</span><span class="sxs-lookup"><span data-stu-id="55a2e-375">Task 2 - Validating JavaScript</span></span>

<span data-ttu-id="55a2e-376">Nesta tarefa, você descobrirá que a nova validação de JavaScript para o padrão de ECMAScript5.</span><span class="sxs-lookup"><span data-stu-id="55a2e-376">In this task, you will discover the new JavaScript validation for the ECMAScript5 standard.</span></span> <span data-ttu-id="55a2e-377">Esse recurso ajudará você a escrevem compatível com código JavaScript, evitando problemas de script antes da implantação do site.</span><span class="sxs-lookup"><span data-stu-id="55a2e-377">This feature will help you to write compliant JavaScript code, while preventing scripting issues before site deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="55a2e-378">Visual Studio 2010 implementado ECMAStript3 conformidade, enquanto o Visual Studio 2012 fornece ECMAScript5 conformidade.</span><span class="sxs-lookup"><span data-stu-id="55a2e-378">Visual Studio 2010 implemented ECMAStript3 compliance, while Visual Studio 2012 provides ECMAScript5 compliance.</span></span>


1. <span data-ttu-id="55a2e-379">Abra **ECMA5script5.js** localizado sob o **Scripts\custom** pasta do projeto.</span><span class="sxs-lookup"><span data-stu-id="55a2e-379">Open **ECMA5script5.js** located under the **Scripts\custom** project folder.</span></span> <span data-ttu-id="55a2e-380">Agora, você testará a validação para ECMAScript5 padrão.</span><span class="sxs-lookup"><span data-stu-id="55a2e-380">You will now test validation for ECMAScript5 standard.</span></span>

    [!code-html[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample8.html)]

    <span data-ttu-id="55a2e-381">Você pode consultar o &quot; **uso estrito** &quot; direção na primeira linha do arquivo, que permite ECMAScript5 **modo estrito**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-381">You can check out the &quot; **use strict** &quot; direction in the first line of the file, which enables ECMAScript5 **strict mode**.</span></span> <span data-ttu-id="55a2e-382">Esse modo consiste em um subconjunto da linguagem que esclarece ambiguidades da edição anterior e adiciona alguns novos recursos, como getters e setters, suporte de biblioteca para JSON e mais completa reflexão em Propriedades do objeto.</span><span class="sxs-lookup"><span data-stu-id="55a2e-382">This mode consists in a subset of the language that clarifies ambiguities from the past edition, and adds some new features, such as getters and setters, library support for JSON, and more complete reflection on object properties.</span></span>
2. <span data-ttu-id="55a2e-383">Abra o **lista de erros** se ainda não estiver aberto (**exibição** menu | **Lista de erros**).</span><span class="sxs-lookup"><span data-stu-id="55a2e-383">Open the **Error List** if not already opened (**View** menu | **Error List**).</span></span> <span data-ttu-id="55a2e-384">Observe o **função** declaração está sublinhada.</span><span class="sxs-lookup"><span data-stu-id="55a2e-384">Notice the **function** declaration is underlined.</span></span> <span data-ttu-id="55a2e-385">Isso ocorre porque no ECMA5 funções padrão não podem ser aninhadas dentro de estruturas de idioma.</span><span class="sxs-lookup"><span data-stu-id="55a2e-385">This is because in ECMA5 standard functions cannot be nested inside language structures.</span></span> <span data-ttu-id="55a2e-386">O erro lista abaixo, você verá os detalhes de aviso.</span><span class="sxs-lookup"><span data-stu-id="55a2e-386">In the error list below you will see the warning details.</span></span>

    <span data-ttu-id="55a2e-387">![Mensagem de erro de validação de JavaScript](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image42.png "mensagem de erro de validação de JavaScript")</span><span class="sxs-lookup"><span data-stu-id="55a2e-387">![JavaScript validation error message](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image42.png "JavaScript validation error message")</span></span>

    <span data-ttu-id="55a2e-388">*Mensagem de erro de validação de JavaScript*</span><span class="sxs-lookup"><span data-stu-id="55a2e-388">*JavaScript validation error message*</span></span>
3. <span data-ttu-id="55a2e-389">Comente o  **&quot;uso estrito&quot;**  direção e observe que desaparecem erros, mas permanecem os avisos.</span><span class="sxs-lookup"><span data-stu-id="55a2e-389">Comment out the **&quot;use strict&quot;** direction and notice that errors disappear, but the warnings remain.</span></span>
4. <span data-ttu-id="55a2e-390">Na última linha do arquivo, gravar qualquer cadeia de caracteres como  **&quot;teste&quot;**  (incluir as aspas para indicar que ela é como cadeia de caracteres).</span><span class="sxs-lookup"><span data-stu-id="55a2e-390">In the last line of the file, write any string like **&quot;test&quot;** (include the quotation marks to indicate it is as string).</span></span> <span data-ttu-id="55a2e-391">Gravar um período próximo a cadeia de caracteres para exibir a lista do IntelliSense e selecione o **trim** opção.</span><span class="sxs-lookup"><span data-stu-id="55a2e-391">Write a period next to the string to display the IntelliSense list, and select the **trim** option.</span></span>

    <span data-ttu-id="55a2e-392">No padrão de ECMAScript5, variáveis e valores de cadeia de caracteres também tem os métodos de cadeia de caracteres definidos, como cortar, letras maiusculas, pesquisar e substituir.</span><span class="sxs-lookup"><span data-stu-id="55a2e-392">In ECMAScript5 standard, string values and variables also have string methods defined, like trim, uppercase, search and replace.</span></span>

    <span data-ttu-id="55a2e-393">![Lista JavaScript IntelliSense](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image43.png "lista JavaScript IntelliSense")</span><span class="sxs-lookup"><span data-stu-id="55a2e-393">![IntelliSense list in JavaScript](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image43.png "IntelliSense list in JavaScript")</span></span>

    <span data-ttu-id="55a2e-394">*Lista do IntelliSense em JavaScript*</span><span class="sxs-lookup"><span data-stu-id="55a2e-394">*IntelliSense list in JavaScript*</span></span>

<a id="Ex3Task3"></a>

<a id="Task_3_-_XML_Documentation_for_JavaScript"></a>
#### <a name="task-3---xml-documentation-for-javascript"></a><span data-ttu-id="55a2e-395">Tarefa 3 - documentação XML para JavaScript</span><span class="sxs-lookup"><span data-stu-id="55a2e-395">Task 3 - XML Documentation for JavaScript</span></span>

<span data-ttu-id="55a2e-396">Nesta tarefa, você irá explorar os recursos do Visual Studio para obter a documentação XML em JavaScript.</span><span class="sxs-lookup"><span data-stu-id="55a2e-396">In this task, you will explore Visual Studio features for XML documentation in JavaScript.</span></span> <span data-ttu-id="55a2e-397">Você verá que a lista de JavaScript IntelliSense agora mostra a documentação XML de cada função.</span><span class="sxs-lookup"><span data-stu-id="55a2e-397">You will see the JavaScript IntelliSense list now shows the XML documentation of each function.</span></span> <span data-ttu-id="55a2e-398">Além disso, você descobrirá que o recurso de navegação em JavaScript.</span><span class="sxs-lookup"><span data-stu-id="55a2e-398">Additionally, you will discover the navigation feature in JavaScript.</span></span>

1. <span data-ttu-id="55a2e-399">Abra **XMLDoc.js** arquivo localizado em **Scripts/personalizada** pasta do projeto.</span><span class="sxs-lookup"><span data-stu-id="55a2e-399">Open **XMLDoc.js** file located in **Scripts/custom** project folder.</span></span> <span data-ttu-id="55a2e-400">Este arquivo contém a documentação XML em cada uma das funções JavaScript.</span><span class="sxs-lookup"><span data-stu-id="55a2e-400">This file contains XML documentation on each of the JavaScript functions.</span></span>

    <span data-ttu-id="55a2e-401">![Documentação XML JavaScript integrado ao IntelliSense](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image44.png "documentação XML JavaScript integrado ao IntelliSense")</span><span class="sxs-lookup"><span data-stu-id="55a2e-401">![JavaScript XML documentation integrated to IntelliSense](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image44.png "JavaScript XML documentation integrated to IntelliSense")</span></span>

    <span data-ttu-id="55a2e-402">*Documentação XML JavaScript integrada ao IntelliSense*</span><span class="sxs-lookup"><span data-stu-id="55a2e-402">*JavaScript XML documentation integrated to IntelliSense*</span></span>
2. <span data-ttu-id="55a2e-403">Abaixo **adicionar** funcionar em **XMLDoc.js** de arquivo, crie uma nova função chamada **teste**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-403">Below **add** function in **XMLDoc.js** file, create a new function named **test**.</span></span>
3. <span data-ttu-id="55a2e-404">No **teste** funcionar, chame o **multiplicar** função que recebe dois parâmetros.</span><span class="sxs-lookup"><span data-stu-id="55a2e-404">In the **test** function, call the **multiply** function that receives two parameters.</span></span> <span data-ttu-id="55a2e-405">Observe que a caixa de dica de ferramenta mostra o **multiplicar** documentação de função.</span><span class="sxs-lookup"><span data-stu-id="55a2e-405">Notice the tooltip box is showing the **multiply** function documentation.</span></span>

    [!code-javascript[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample9.js)]

    <span data-ttu-id="55a2e-406">![Documentação XML para funções JavaScript](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image45.png "documentação XML para funções JavaScript")</span><span class="sxs-lookup"><span data-stu-id="55a2e-406">![XML documentation for JavaScript functions](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image45.png "XML documentation for JavaScript functions")</span></span>

    <span data-ttu-id="55a2e-407">*Documentação XML para funções JavaScript*</span><span class="sxs-lookup"><span data-stu-id="55a2e-407">*XML documentation for JavaScript functions*</span></span>
4. <span data-ttu-id="55a2e-408">Conclua a instrução de chamada de função e digite um *ponto* para abrir a lista do IntelliSense no valor retornado.</span><span class="sxs-lookup"><span data-stu-id="55a2e-408">Complete the function call statement and type a *dot* to open the IntelliSense list on the returned value.</span></span> <span data-ttu-id="55a2e-409">Observe que o Visual Studio está detectando a **retornar** valor na documentação, tratando o valor como um número.</span><span class="sxs-lookup"><span data-stu-id="55a2e-409">Notice that Visual Studio is detecting the **return** value in the documentation, treating the value as a number.</span></span>

    <span data-ttu-id="55a2e-410">![Documentação XML para tipos de retorno](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image46.png "documentação XML para tipos de retorno")</span><span class="sxs-lookup"><span data-stu-id="55a2e-410">![XML documentation for return types](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image46.png "XML documentation for return types")</span></span>

    <span data-ttu-id="55a2e-411">*Documentação XML para tipos de retorno*</span><span class="sxs-lookup"><span data-stu-id="55a2e-411">*XML documentation for return types*</span></span>
5. <span data-ttu-id="55a2e-412">Agora, insira uma chamada para adicionar a função.</span><span class="sxs-lookup"><span data-stu-id="55a2e-412">Now, insert a call to add function.</span></span> <span data-ttu-id="55a2e-413">Observe que o editor do JavaScript agora dá suporte a sobrecargas de função.</span><span class="sxs-lookup"><span data-stu-id="55a2e-413">Notice that the JavaScript editor now supports function overloads.</span></span> <span data-ttu-id="55a2e-414">Quando você escreve um nome de função, você poderá selecionar qualquer uma das sobrecargas disponíveis especificadas na documentação.</span><span class="sxs-lookup"><span data-stu-id="55a2e-414">When you write a function name, you will be able to select any of the available overloads specified in the documentation.</span></span>

    <span data-ttu-id="55a2e-415">![Documentação XML para as sobrecargas](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image47.png "documentação XML para as sobrecargas")</span><span class="sxs-lookup"><span data-stu-id="55a2e-415">![XML documentation for overloads](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image47.png "XML documentation for overloads")</span></span>

    <span data-ttu-id="55a2e-416">*Documentação XML para as sobrecargas*</span><span class="sxs-lookup"><span data-stu-id="55a2e-416">*XML documentation for overloads*</span></span>
6. <span data-ttu-id="55a2e-417">Abra **GotoDefinition.js** de arquivo e localize o **$().html()** chamada de função.</span><span class="sxs-lookup"><span data-stu-id="55a2e-417">Open **GotoDefinition.js** file and locate the **$().html()** function call.</span></span> <span data-ttu-id="55a2e-418">Localize o cursor em **html**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-418">Locate the cursor on **html**.</span></span>
7. <span data-ttu-id="55a2e-419">Pressione **F12** e navegue até a definição.</span><span class="sxs-lookup"><span data-stu-id="55a2e-419">Press **F12** and navigate to the definition.</span></span> <span data-ttu-id="55a2e-420">Observe que agora você pode acessar e procurar seu código JavaScript sem usar o **localizar** ferramenta.</span><span class="sxs-lookup"><span data-stu-id="55a2e-420">Notice you can now access and browse your JavaScript code without using the **Find** tool.</span></span>
8. <span data-ttu-id="55a2e-421">Localize o cursor sobre a instrução jQuery antes do bloco de assinatura na parte inferior do arquivo de código.</span><span class="sxs-lookup"><span data-stu-id="55a2e-421">Locate the cursor on the jQuery instruction prior to the signature block at the bottom of the code file.</span></span> <span data-ttu-id="55a2e-422">Pressione **F12**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-422">Press **F12**.</span></span> <span data-ttu-id="55a2e-423">Você navegará para o arquivo de biblioteca jQuery.</span><span class="sxs-lookup"><span data-stu-id="55a2e-423">You will navigate to the jQuery library file.</span></span> <span data-ttu-id="55a2e-424">Observe que você também pode navegar em todos os arquivos de jQuery usando **F12**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-424">Notice you can also navigate across the jQuery files using **F12**.</span></span>

    <span data-ttu-id="55a2e-425">![Navegar para jQuery definições](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image48.png "navegando até jQuery definições")</span><span class="sxs-lookup"><span data-stu-id="55a2e-425">![Navigating to jQuery definitions](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image48.png "Navigating to jQuery definitions")</span></span>

    <span data-ttu-id="55a2e-426">*Navegar para jQuery definições*</span><span class="sxs-lookup"><span data-stu-id="55a2e-426">*Navigating to jQuery definitions*</span></span>

> [!NOTE]
> <span data-ttu-id="55a2e-427">Certifique-se de que GotoDefinition.js não tem nenhum erro de sintaxe antes de salvar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-427">Make sure that GotoDefinition.js has no syntax errors before saving the file.</span></span>


<a id="Exercise4"></a>

<a id="Exercise_4_Bundling_and_Minification"></a>
### <a name="exercise-4-bundling-and-minification"></a><span data-ttu-id="55a2e-428">Exercício 4: Empacotamento e minimização</span><span class="sxs-lookup"><span data-stu-id="55a2e-428">Exercise 4: Bundling and Minification</span></span>

<span data-ttu-id="55a2e-429">Quantas vezes os sites têm os CSS ou JavaScript mais de um arquivo?</span><span class="sxs-lookup"><span data-stu-id="55a2e-429">How many times do your websites include more than one JavaScript or CSS file?</span></span> <span data-ttu-id="55a2e-430">Este é um cenário bastante comum, onde o empacotamento e minimização podem ajudar a reduzir o tamanho do arquivo e fazer com que o site ser executado mais rapidamente.</span><span class="sxs-lookup"><span data-stu-id="55a2e-430">This is a very common scenario where bundling and minification can help to reduce the file size and make the site perform faster.</span></span> <span data-ttu-id="55a2e-431">O novo recurso de agrupamento no ASP.NET 4.5 pacotes de um conjunto de arquivos JS ou CSS em um único elemento e reduz o tamanho, minimizando o conteúdo (por exemplo, remover espaços em branco não é necessários, removendo comentários, reduzindo identificadores).</span><span class="sxs-lookup"><span data-stu-id="55a2e-431">The new bundling feature in ASP.NET 4.5 packs a set of JS or CSS files into a single element, and reduces its size by minifying the content ( i.e. removing not required blank spaces, removing comments, reducing identifiers ).</span></span>

<span data-ttu-id="55a2e-432">Empacotamento e minimização no ASP.NET 4.5 é executada em tempo de execução, para que o processo pode identificar o agente do usuário (por exemplo, Internet Explorer, Mozilla, etc) e assim, melhorar a compactação direcionando o navegador do usuário (por exemplo, removendo objetos Mozilla específico Quando a solicitação chega do IE).</span><span class="sxs-lookup"><span data-stu-id="55a2e-432">Bundling and minification in ASP.NET 4.5 is performed at runtime, so that the process can identify the user agent (for example IE, Mozilla, etc), and thus, improve the compression by targeting the user browser (for instance, removing stuff that is Mozilla specific when the request comes from IE).</span></span>

<span data-ttu-id="55a2e-433">Neste exercício, você aprenderá como habilitar e usar os diferentes tipos de empacotamento e minimização no ASP.NET 4.5.</span><span class="sxs-lookup"><span data-stu-id="55a2e-433">In this exercise, you will learn how to enable and use the different types of bundling and minification in ASP.NET 4.5.</span></span>

<a id="Ex4Task1"></a>

<a id="Task_1_-_Installing_the_Bundling_and_Minification_Package_from_NuGet"></a>
#### <a name="task-1---installing-the-bundling-and-minification-package-from-nuget"></a><span data-ttu-id="55a2e-434">Tarefa 1: instalar o empacotamento e minimização de pacote do NuGet</span><span class="sxs-lookup"><span data-stu-id="55a2e-434">Task 1 - Installing the Bundling and Minification Package from NuGet</span></span>

1. <span data-ttu-id="55a2e-435">Se ainda não estiver aberto, inicie **Visual Studio** e abra o **WhatsNewASPNET.sln** solução localizada no **Source\WhatsNewASPNET** pasta deste laboratório.</span><span class="sxs-lookup"><span data-stu-id="55a2e-435">If not already opened, start **Visual Studio** and open the **WhatsNewASPNET.sln** solution located in the **Source\WhatsNewASPNET** folder of this lab.</span></span>
2. <span data-ttu-id="55a2e-436">Abra o NuGet Package Manager Console.</span><span class="sxs-lookup"><span data-stu-id="55a2e-436">Open the NuGet Package Manager Console.</span></span> <span data-ttu-id="55a2e-437">Para fazer isso, use o menu **exibição** | **outras janelas** | **Package Manager Console**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-437">To do this, use the menu **View** | **Other Windows** | **Package Manager Console**.</span></span>

    <span data-ttu-id="55a2e-438">![Abrir o pacote manager file:///C:/Users/User/AppData/Local/Temp/Marker3744//media/44462/Multiple-Stylesheets-and-JavaScript-files-in-the-application.pngconsole](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image49.png "abrindo o console do Gerenciador de pacote")</span><span class="sxs-lookup"><span data-stu-id="55a2e-438">![Opening the package manager file:///C:/Users/User/AppData/Local/Temp/Marker3744//media/44462/Multiple-Stylesheets-and-JavaScript-files-in-the-application.pngconsole](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image49.png "Opening the package manager console")</span></span>

    <span data-ttu-id="55a2e-439">*Abrindo o console do Gerenciador de pacote*</span><span class="sxs-lookup"><span data-stu-id="55a2e-439">*Opening the package manager console*</span></span>
3. <span data-ttu-id="55a2e-440">No **Package Manager Console,** tipo **Install-Package Microsoft.Web.Optimization** e pressione **ENTER**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-440">In the **Package Manager Console,** type **Install-Package Microsoft.Web.Optimization** and press **ENTER**.</span></span>

<a id="Ex4Task2"></a>

<a id="Task_2_-_Default_Bundles"></a>
#### <a name="task-2---default-bundles"></a><span data-ttu-id="55a2e-441">Tarefa 2 - pacotes padrão</span><span class="sxs-lookup"><span data-stu-id="55a2e-441">Task 2 - Default Bundles</span></span>

<span data-ttu-id="55a2e-442">A maneira mais simples de usar empacotamento e minimização é habilitar os pacotes padrão.</span><span class="sxs-lookup"><span data-stu-id="55a2e-442">The simplest way to use bundling and minification is to enable the default bundles.</span></span> <span data-ttu-id="55a2e-443">Esse método usa as convenções para lhe permitem fazer referência à versão do pacote e minimizada para os arquivos JS e CSS em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="55a2e-443">This method uses conventions to let you reference the bundled and minified version for the JS and CSS files in a folder.</span></span>

<span data-ttu-id="55a2e-444">Nesta tarefa, você aprenderá como ativar e fazer referência aos arquivos agrupados e minimizados JS e CSS e exibir a saída resultante.</span><span class="sxs-lookup"><span data-stu-id="55a2e-444">In this task, you will learn how to enable and reference the bundled and minified JS and CSS files and view the resulting output.</span></span>

1. <span data-ttu-id="55a2e-445">Se ainda não estiver aberto, inicie **Visual Studio** e abra o **WhatsNewASPNET.sln** solução localizada no **Source\WhatsNewASPNET** pasta deste laboratório.</span><span class="sxs-lookup"><span data-stu-id="55a2e-445">If not already opened, start **Visual Studio** and open the **WhatsNewASPNET.sln** solution located in the **Source\WhatsNewASPNET** folder of this lab.</span></span>
2. <span data-ttu-id="55a2e-446">No **Solution Explorer**, expanda o **estilos**, **Scripts\custom** e **Scripts\bundle** pastas.</span><span class="sxs-lookup"><span data-stu-id="55a2e-446">In the **Solution Explorer**, expand the **Styles**, **Scripts\custom** and **Scripts\bundle** folders.</span></span>

    <span data-ttu-id="55a2e-447">Observe que o aplicativo está usando o arquivo de mais de uma CSS e JS.</span><span class="sxs-lookup"><span data-stu-id="55a2e-447">Notice that the application is using more than one CSS and JS file.</span></span>

    <span data-ttu-id="55a2e-448">![Arquivos de várias folhas de estilo e JavaScript no aplicativo](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image50.png "arquivos várias folhas de estilo e JavaScript no aplicativo")</span><span class="sxs-lookup"><span data-stu-id="55a2e-448">![Multiple Stylesheets and JavaScript files in the application](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image50.png "Multiple Stylesheets and JavaScript files in the application")</span></span>

    <span data-ttu-id="55a2e-449">*Vários arquivos de folhas de estilo e JavaScript no aplicativo*</span><span class="sxs-lookup"><span data-stu-id="55a2e-449">*Multiple Stylesheets and JavaScript files in the application*</span></span>
3. <span data-ttu-id="55a2e-450">Abra o **Global.asax.cs** arquivo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-450">Open the **Global.asax.cs** file.</span></span>

    <span data-ttu-id="55a2e-451">Observe que o novo **Microsoft.Web.Optimization** namespace é comentado no início do arquivo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-451">Notice that the new **Microsoft.Web.Optimization** namespace is commented out at the beginning of the file.</span></span> <span data-ttu-id="55a2e-452">Remova o usando a diretiva para incluir os recursos de empacotamento e minimização.</span><span class="sxs-lookup"><span data-stu-id="55a2e-452">Uncomment the using directive to include the bundling and minification features.</span></span>


    [!code-csharp[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample10.cs)]
4. <span data-ttu-id="55a2e-453">Localize o **aplicativo\_iniciar** método.</span><span class="sxs-lookup"><span data-stu-id="55a2e-453">Locate the **Application\_Start** method.</span></span>

    <span data-ttu-id="55a2e-454">Nesse método, remova a chamada EnableDefaultBundles conforme mostrado no trecho a seguir.</span><span class="sxs-lookup"><span data-stu-id="55a2e-454">In this method, uncomment the EnableDefaultBundles call as shown in the snippet below.</span></span> <span data-ttu-id="55a2e-455">Isso nos permite fazer referência a uma coleção de pacote de arquivos CSS em uma pasta usando o caminho para a pasta, mais o &quot;CSS&quot; ou &quot;JS&quot; sufixo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-455">This enables us to reference a bundled collection of CSS files in a folder by using the path to that folder, plus the &quot;CSS&quot; or the &quot;JS&quot; suffix.</span></span>


    [!code-csharp[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample11.cs)]
5. <span data-ttu-id="55a2e-456">Abra o **Optimization.aspx** de arquivo e localize o controle de conteúdo de **HeadContent**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-456">Open the **Optimization.aspx** file and locate the content control for **HeadContent**.</span></span>

    <span data-ttu-id="55a2e-457">Observe os arquivos CSS e JS ter uma única marca referenciada.</span><span class="sxs-lookup"><span data-stu-id="55a2e-457">Notice the CSS files and the JS files have a single referenced tag.</span></span>


    [!code-aspx[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample12.aspx)]

    > [!NOTE]
    > <span data-ttu-id="55a2e-458">Esse código é para fins de demonstração.</span><span class="sxs-lookup"><span data-stu-id="55a2e-458">This code is for demo purposes.</span></span> <span data-ttu-id="55a2e-459">Idealmente, você irá referenciar os pacotes no arquivo Site.Master.</span><span class="sxs-lookup"><span data-stu-id="55a2e-459">Ideally, you will reference the bundles in the Site.Master file.</span></span> <span data-ttu-id="55a2e-460">Nesse código de exemplo, você descobrirá que alguns dos arquivos de pacote também estão sendo referenciados pelo arquivo de Site.Master, tornando esta última referência redundantes.</span><span class="sxs-lookup"><span data-stu-id="55a2e-460">In this sample code, you will find that some of the bundled files are also being referenced by the Site.Master file, making this last reference redundant.</span></span>
6. <span data-ttu-id="55a2e-461">Observe que os links são usando as convenções de agrupamento de **href** atributo para obter os arquivos de todos os CSS ou JS dos estilos e Scripts\custom pasta respectivamente.</span><span class="sxs-lookup"><span data-stu-id="55a2e-461">Notice that the links are using the bundling conventions in the **href** attribute to get all the CSS or JS files from the Styles and Scripts\custom folder respectively.</span></span>

    <span data-ttu-id="55a2e-462">Você pode usar o caminho **personalizado/Scripts/JS** conforme mostrado abaixo, agrupar e minificada todos os arquivos JS dentro de um **Scripts/personalizada** pasta.</span><span class="sxs-lookup"><span data-stu-id="55a2e-462">You can use the path **Scripts/custom/JS** as shown below to bundle and minify all the JS files inside a **Scripts/custom** folder.</span></span> <span data-ttu-id="55a2e-463">Esse é o comportamento padrão com os pacotes padrão.</span><span class="sxs-lookup"><span data-stu-id="55a2e-463">This is the default behavior with the default bundles.</span></span>


    [!code-aspx[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample13.aspx)]
7. <span data-ttu-id="55a2e-464">Abra o **Styles\Site.css** arquivo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-464">Open the **Styles\Site.css** file.</span></span>

    <span data-ttu-id="55a2e-465">Observe que o arquivo CSS original contém código recuado, espaços em branco e comentários que aumentam o arquivo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-465">Notice that the original CSS file contains indented code, blank spaces and comments that enlarge the file.</span></span> <span data-ttu-id="55a2e-466">(Também o arquivo JavaScript contém comentários e espaços em branco).</span><span class="sxs-lookup"><span data-stu-id="55a2e-466">(Also the JavaScript file contains blank spaces and comments).</span></span>

    <span data-ttu-id="55a2e-467">![Uma folha de estilos original arquivos na pasta Scripts](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image51.png "uma folha de estilos original arquivos na pasta Scripts")</span><span class="sxs-lookup"><span data-stu-id="55a2e-467">![One of the original CSS files in the Scripts folder](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image51.png "One of the original CSS files in the Scripts folder")</span></span>

    <span data-ttu-id="55a2e-468">*Um dos arquivos CSS originais na pasta Scripts*</span><span class="sxs-lookup"><span data-stu-id="55a2e-468">*One of the original CSS files in the Scripts folder*</span></span>
8. <span data-ttu-id="55a2e-469">Pressione **F5** para executar o aplicativo e navegue até o **otimização** página.</span><span class="sxs-lookup"><span data-stu-id="55a2e-469">Press **F5** to run the application and navigate to the **Optimization** page.</span></span>
9. <span data-ttu-id="55a2e-470">Clique no **pacote CSS** link para baixar e abrir o arquivo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-470">Click on the **CSS Bundle** link to download and open the file.</span></span>

    <span data-ttu-id="55a2e-471">Check-out do arquivo de pacote minimizado.</span><span class="sxs-lookup"><span data-stu-id="55a2e-471">Check out the minified bundled file.</span></span> <span data-ttu-id="55a2e-472">Você observará que todos os espaços em branco, comentários e caracteres de recuo foram removidas, gerando um arquivo menor.</span><span class="sxs-lookup"><span data-stu-id="55a2e-472">You will notice that all the blank spaces, comments and indentation characters have been removed, generating a smaller file.</span></span>

    <span data-ttu-id="55a2e-473">![Arquivos CSS empacotados](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image52.png "arquivos CSS agrupados")</span><span class="sxs-lookup"><span data-stu-id="55a2e-473">![Bundled CSS files](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image52.png "Bundled CSS files")</span></span>

    <span data-ttu-id="55a2e-474">*Os arquivos CSS*</span><span class="sxs-lookup"><span data-stu-id="55a2e-474">*Bundled CSS files*</span></span>
10. <span data-ttu-id="55a2e-475">Agora clique o **JS pacote** link para abrir o arquivo de pacote de JavaScript.</span><span class="sxs-lookup"><span data-stu-id="55a2e-475">Now click the **JS Bundle** link to open the JavaScript bundled file.</span></span> <span data-ttu-id="55a2e-476">Você poderá desconsiderar o aviso do Pesquisador de objetos.</span><span class="sxs-lookup"><span data-stu-id="55a2e-476">You can safely disregard the explorer warning.</span></span> <span data-ttu-id="55a2e-477">Observe os arquivos JavaScript sob o **personalizado** pasta também são agrupadas e minimizada.</span><span class="sxs-lookup"><span data-stu-id="55a2e-477">Notice the JavaScript files under the **custom** folder are also bundled and minified.</span></span>

    <span data-ttu-id="55a2e-478">![Os arquivos JavaScript de pacote](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image53.png "arquivos JavaScript agrupado")</span><span class="sxs-lookup"><span data-stu-id="55a2e-478">![Bundled JavaScript files](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image53.png "Bundled JavaScript files")</span></span>

    <span data-ttu-id="55a2e-479">*Os arquivos do JavaScript*</span><span class="sxs-lookup"><span data-stu-id="55a2e-479">*Bundled JavaScript files*</span></span>

    <span data-ttu-id="55a2e-480">A habilitação da compactação de arquivos CSS ou JS era muito mais complicada na versão anterior do ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="55a2e-480">Enabling compression for CSS or JS files was much more complicated in previous ASP.NET version.</span></span> <span data-ttu-id="55a2e-481">Agora, como você viu, basta adicionar uma linha no *global. asax* para habilitar o agrupamento de arquivo e, em seguida, fazer referência aos arquivos de pacotes do seu site.</span><span class="sxs-lookup"><span data-stu-id="55a2e-481">Now, as you have seen, you just need to add one line in the *Global.asax* file to enable bundling, and then reference the bundled files from your site.</span></span>

<a id="Ex4Task3"></a>

<a id="Task_3_-_Static_Bundles"></a>
#### <a name="task-3---static-bundles"></a><span data-ttu-id="55a2e-482">Tarefa 3 - pacotes estáticos</span><span class="sxs-lookup"><span data-stu-id="55a2e-482">Task 3 - Static Bundles</span></span>

<span data-ttu-id="55a2e-483">A abordagem de pacote estático permite que você personalize o conjunto de arquivos de pacote, a referência e o método de minimização que será usado.</span><span class="sxs-lookup"><span data-stu-id="55a2e-483">The static bundle approach allows you to customize the set of files to bundle, the reference and the minification method that will be used.</span></span>

<span data-ttu-id="55a2e-484">Nesta tarefa, você configurará um conjunto estático para definir um conjunto específico de arquivos para agrupar e minificada.</span><span class="sxs-lookup"><span data-stu-id="55a2e-484">In this task, you will configure a static bundle to define a specific set of files to bundle and minify.</span></span>

1. <span data-ttu-id="55a2e-485">Feche o navegador.</span><span class="sxs-lookup"><span data-stu-id="55a2e-485">Close the browser.</span></span>
2. <span data-ttu-id="55a2e-486">Abra o **Global.asax.cs** de arquivo e localize o **aplicativo\_iniciar** método.</span><span class="sxs-lookup"><span data-stu-id="55a2e-486">Open the **Global.asax.cs** file and locate the **Application\_Start** method.</span></span>
3. <span data-ttu-id="55a2e-487">Descomente o código de pacote estáticos, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="55a2e-487">Uncomment the static bundle code as shown in the code below.</span></span>

    <span data-ttu-id="55a2e-488">Você está definindo um conjunto estático que será referenciado com o &quot; **~/StaticBundle** &quot; caminho virtual e use **JsMinify** para minimização de todos os arquivos especificados com o **AddFile** método.</span><span class="sxs-lookup"><span data-stu-id="55a2e-488">You are defining a static bundle that will be referenced with the &quot;**~/StaticBundle**&quot; virtual path and use **JsMinify** for minification of all the specified files with the **AddFile** method.</span></span> <span data-ttu-id="55a2e-489">Por fim, você está adicionando o pacote estático para o **BundleTable** e habilitá-la.</span><span class="sxs-lookup"><span data-stu-id="55a2e-489">Finally, you are adding the static bundle to the **BundleTable** and enabling it.</span></span>

    <span data-ttu-id="55a2e-490">Observe que os arquivos não estão localizados no mesmo lugar; Essa é outra vantagem sobre o agrupamento padrão.</span><span class="sxs-lookup"><span data-stu-id="55a2e-490">Notice that the files are not located in the same place; this is another advantage over the default bundling.</span></span>


    [!code-csharp[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample14.cs)]
4. <span data-ttu-id="55a2e-491">Abra o **Optimization.aspx** arquivo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-491">Open the **Optimization.aspx** file.</span></span>

    <span data-ttu-id="55a2e-492">Observe que o link para **conjunto estático de JS** está usando o caminho que você declarou quando você configurou o pacote estático no arquivo asax: **/StaticBundle**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-492">Notice that the link to **Static JS Bundle** is using the path you have declared when you configured the static bundle in the Global.asax.cs file: **/StaticBundle**.</span></span>


    [!code-aspx[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample15.aspx)]
5. <span data-ttu-id="55a2e-493">Pressione **F5** para executar o aplicativo e, em seguida, navegue até o **otimização** página.</span><span class="sxs-lookup"><span data-stu-id="55a2e-493">Press **F5** to run the application, and then navigate to the **Optimization** page.</span></span>
6. <span data-ttu-id="55a2e-494">Clique no **conjunto estático de JS** link para abrir o arquivo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-494">Click on the **Static JS Bundle** link to open the file.</span></span>

    <span data-ttu-id="55a2e-495">Observe que o minimizada agrupados arquivo JavaScript é a saída para todos os arquivos do JavaScript são configurados no arquivo de pacote estáticos no caminho &quot;/StaticBundle&quot;.</span><span class="sxs-lookup"><span data-stu-id="55a2e-495">Notice that the minified bundled JavaScript file is the output for all the JavaScript files configured in the static bundle file under the path &quot;/StaticBundle&quot;.</span></span>

    <span data-ttu-id="55a2e-496">![Pacote de arquivos estático JavaScript](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image54.png "pacote de arquivos estáticos JavaScript")</span><span class="sxs-lookup"><span data-stu-id="55a2e-496">![Static JavaScript files bundle](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image54.png "Static JavaScript files bundle")</span></span>

    <span data-ttu-id="55a2e-497">*Agrupar arquivos JavaScript estáticos*</span><span class="sxs-lookup"><span data-stu-id="55a2e-497">*Static JavaScript files bundle*</span></span>
7. <span data-ttu-id="55a2e-498">Feche o navegador e retorne ao Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="55a2e-498">Close the browser and return to Visual Studio.</span></span>

<a id="Ex4Task4"></a>

<a id="Task_4_-_Dynamic_Folder_Bundles"></a>
#### <a name="task-4---dynamic-folder-bundles"></a><span data-ttu-id="55a2e-499">Tarefa 4 - pasta dinâmico pacotes</span><span class="sxs-lookup"><span data-stu-id="55a2e-499">Task 4 - Dynamic Folder Bundles</span></span>

<span data-ttu-id="55a2e-500">Nesta tarefa, você aprenderá como configurar pacotes de pasta dinâmico.</span><span class="sxs-lookup"><span data-stu-id="55a2e-500">In this task, you will learn how to configure dynamic folder bundles.</span></span> <span data-ttu-id="55a2e-501">O poder do empacotamento dinâmico é que você pode incluir JavaScript estático, bem como outros arquivos em idiomas que compila em JavaScript e assim, exigem algum processamento antes que o agrupamento é executada.</span><span class="sxs-lookup"><span data-stu-id="55a2e-501">The power of dynamic bundling is that you can include static JavaScript, as well as other files in languages that compiles into JavaScript, and thus, require some processing before the bundling is executed.</span></span>

<span data-ttu-id="55a2e-502">Neste exemplo, você aprenderá como usar o **DynamicFolderBundle** classe para criar um conjunto dinâmico para arquivos escritos em CofeeScript.</span><span class="sxs-lookup"><span data-stu-id="55a2e-502">In this example, you will learn how to use the **DynamicFolderBundle** class to create a dynamic bundle for files written in CofeeScript.</span></span> <span data-ttu-id="55a2e-503">CofeeScript é uma linguagem de programação que compila em JavaScript e fornece uma sintaxe mais simples para escrever código JavaScript, melhorando a legibilidade e resumir do JavaScript.</span><span class="sxs-lookup"><span data-stu-id="55a2e-503">CofeeScript is a programming language that compiles into JavaScript and provides a simpler syntax for writing JavaScript code, enhancing JavaScript's brevity and readability.</span></span>

1. <span data-ttu-id="55a2e-504">Abra o **Global.asax.cs** de arquivo e localize o **aplicativo\_iniciar** método.</span><span class="sxs-lookup"><span data-stu-id="55a2e-504">Open the **Global.asax.cs** file and locate the **Application\_Start** method.</span></span>
2. <span data-ttu-id="55a2e-505">Descomente o código de pacote dinâmico, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="55a2e-505">Uncomment the dynamic bundle code as shown in the code below.</span></span>

    <span data-ttu-id="55a2e-506">Você está definindo um pacote da pasta dinâmico que usará o **CoffeeMinify** processador minimização personalizados que se aplicam somente a arquivos com o &quot; **.coffee** &quot; (de extensão Arquivos de CoffeeScript).</span><span class="sxs-lookup"><span data-stu-id="55a2e-506">You are defining a dynamic folder bundle that will use the **CoffeeMinify** custom minification processor that will only apply to the files with the &quot;**.coffee**&quot; extension (CoffeeScript files).</span></span> <span data-ttu-id="55a2e-507">Observe que você pode usar um padrão de pesquisa para selecionar os arquivos para agrupar dentro de uma pasta, como '\*.coffee'.</span><span class="sxs-lookup"><span data-stu-id="55a2e-507">Notice that you can use a search pattern to select the files to bundle within a folder, like '\*.coffee'.</span></span>


    [!code-csharp[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample16.cs)]
3. <span data-ttu-id="55a2e-508">Abra o NuGet Package Manager Console.</span><span class="sxs-lookup"><span data-stu-id="55a2e-508">Open the NuGet Package Manager Console.</span></span> <span data-ttu-id="55a2e-509">Para fazer isso, use o menu **exibição** | **outras janelas** | **Package Manager Console**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-509">To do this, use the menu **View** | **Other Windows** | **Package Manager Console**.</span></span>
4. <span data-ttu-id="55a2e-510">No **Package Manager Console,** tipo **Install-Package CoffeeSharp** e pressione **ENTER**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-510">In the **Package Manager Console,** type **Install-Package CoffeeSharp** and press **ENTER**.</span></span>
5. <span data-ttu-id="55a2e-511">Clique o **Mostrar todos os arquivos** no botão de **Solution Explorer** janela</span><span class="sxs-lookup"><span data-stu-id="55a2e-511">Click the **Show All Files** button in the **Solution Explorer** window</span></span>

    <span data-ttu-id="55a2e-512">![Mostrando todos os arquivos](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image55.png "mostrando todos os arquivos")</span><span class="sxs-lookup"><span data-stu-id="55a2e-512">![Showing all files](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image55.png "Showing all files")</span></span>

    <span data-ttu-id="55a2e-513">*Mostrando todos os arquivos*</span><span class="sxs-lookup"><span data-stu-id="55a2e-513">*Showing all files*</span></span>
6. <span data-ttu-id="55a2e-514">Clique com botão direito do **CoffeeMinify.cs** de arquivos no **Gerenciador de soluções** e selecione **incluir no projeto**</span><span class="sxs-lookup"><span data-stu-id="55a2e-514">Right click the **CoffeeMinify.cs** file in the **Solution Explorer** and select **Include in Project**</span></span>

    <span data-ttu-id="55a2e-515">![Incluir o arquivo CoffeeMinify.cs no projeto](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image56.png "incluem o arquivo CoffeeMinify.cs no projeto")</span><span class="sxs-lookup"><span data-stu-id="55a2e-515">![Include the CoffeeMinify.cs file in the project](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image56.png "Include the CoffeeMinify.cs file in the project")</span></span>

    <span data-ttu-id="55a2e-516">*Incluir o arquivo CoffeeMinify.cs no projeto*</span><span class="sxs-lookup"><span data-stu-id="55a2e-516">*Include the CoffeeMinify.cs file in the project*</span></span>
7. <span data-ttu-id="55a2e-517">Abra o **CoffeeMinify.cs** arquivo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-517">Open the **CoffeeMinify.cs** file.</span></span>

    <span data-ttu-id="55a2e-518">Essa classe herda do JsMinify ser minificada a saída de JavaScript resultante da compilação de código CoffeeScript.</span><span class="sxs-lookup"><span data-stu-id="55a2e-518">This class inherits from JsMinify to minify the JavaScript output resulting from the CoffeeScript code compilation.</span></span> <span data-ttu-id="55a2e-519">Ele chama o compilador CoffeeScript para gerar o código JavaScript primeiro e, em seguida, ele envia para o método de JsMinify.Process para minificada o código resultante.</span><span class="sxs-lookup"><span data-stu-id="55a2e-519">It calls the CoffeeScript compiler to generate the JavaScript code first, and then it sends it to the JsMinify.Process method to minify the resulting code.</span></span>


    [!code-csharp[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample17.cs)]
8. <span data-ttu-id="55a2e-520">Abra o **Script1.coffee** e **Script2.coffee** arquivos do **Scripts/pacote** pasta.</span><span class="sxs-lookup"><span data-stu-id="55a2e-520">Open the **Script1.coffee** and **Script2.coffee** files from the **Scripts/bundle** folder.</span></span>

    <span data-ttu-id="55a2e-521">Esses arquivos incluirá o código CoffeScript para ser compilada ao executar o agrupamento com a classe CoffeeMinify.</span><span class="sxs-lookup"><span data-stu-id="55a2e-521">These files will include the CoffeScript code to be compiled while performing the bundling with the CoffeeMinify class.</span></span>

    <span data-ttu-id="55a2e-522">Para fins de simplicidade, os arquivos de CoffeeScript fornecidos são apenas incluindo CoffeeScript código de exemplo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-522">For simplicity purposes, the CoffeeScript files provided are only including CoffeeScript sample code.</span></span> <span data-ttu-id="55a2e-523">Os comentários são excluídos pelo processo de JsMinify.</span><span class="sxs-lookup"><span data-stu-id="55a2e-523">The comments are excluded by the JsMinify process.</span></span>

    <span data-ttu-id="55a2e-524">![Arquivos de CoffeeScript](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image57.png "CoffeeScript arquivos")</span><span class="sxs-lookup"><span data-stu-id="55a2e-524">![CoffeeScript files](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image57.png "CoffeeScript files")</span></span>

    <span data-ttu-id="55a2e-525">*Arquivos do CoffeeScript*</span><span class="sxs-lookup"><span data-stu-id="55a2e-525">*CoffeeScript files*</span></span>

    > [!NOTE]
    > <span data-ttu-id="55a2e-526">[CofeeScript](https://github.com/jashkenas/coffeescript/) fornece uma sintaxe mais simples para escrever código JavaScript, melhorando a legibilidade e resumir do JavaScript, bem como adicionar outros recursos, como a compreensão de matriz e a correspondência de padrões.</span><span class="sxs-lookup"><span data-stu-id="55a2e-526">[CofeeScript](https://github.com/jashkenas/coffeescript/) provides a simpler syntax for writing JavaScript code, enhancing JavaScript's brevity and readability, as well as adding other features like array comprehension and pattern matching.</span></span>
9. <span data-ttu-id="55a2e-527">Abra o **Optimization.aspx** de arquivo e localize os links do pacote.</span><span class="sxs-lookup"><span data-stu-id="55a2e-527">Open the **Optimization.aspx** file and locate the bundle links.</span></span>

    <span data-ttu-id="55a2e-528">Observe que o link para **pacote dinâmico de JS** faz referência a **Scripts/pacote** pasta usando o **/café** sufixo que você configurou para o pacote da pasta dinâmico.</span><span class="sxs-lookup"><span data-stu-id="55a2e-528">Notice that the link to **Dynamic JS Bundle** is referencing the **Scripts/bundle** folder by using the **/Coffee** suffix you configured for the dynamic folder bundle.</span></span>


    [!code-aspx[Main](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/samples/sample18.aspx)]
10. <span data-ttu-id="55a2e-529">Pressione **F5** para executar o aplicativo e, em seguida, navegue até o **otimização** página.</span><span class="sxs-lookup"><span data-stu-id="55a2e-529">Press **F5** to run the application, and then navigate to the **Optimization** page.</span></span>
11. <span data-ttu-id="55a2e-530">Clique no **pacote dinâmico de JS** link para abrir o arquivo gerado.</span><span class="sxs-lookup"><span data-stu-id="55a2e-530">Click on the **Dynamic JS Bundle** link to open the generated file.</span></span>

    <span data-ttu-id="55a2e-531">Observe que só contém o conteúdo que foi incluído neste pacote **.coffee** arquivos.</span><span class="sxs-lookup"><span data-stu-id="55a2e-531">Notice that the content that was included in this bundle only contains **.coffee** files.</span></span> <span data-ttu-id="55a2e-532">Você também pode ver que o código de CoffeeScript foi compilado para JavaScript e as linhas comentadas foi removido.</span><span class="sxs-lookup"><span data-stu-id="55a2e-532">You can also see that the CoffeeScript code was compiled to JavaScript and the commented-out lines has been removed.</span></span>

    <span data-ttu-id="55a2e-533">![Agrupar arquivos JS dinâmicos](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image58.png "JS dinâmico pacote de arquivos")</span><span class="sxs-lookup"><span data-stu-id="55a2e-533">![Dynamic JS files bundle](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image58.png "Dynamic JS files bundle")</span></span>

    <span data-ttu-id="55a2e-534">*Pacote de arquivos JS dinâmico*</span><span class="sxs-lookup"><span data-stu-id="55a2e-534">*Dynamic JS files bundle*</span></span>

> [!NOTE]
> <span data-ttu-id="55a2e-535">Além disso, você pode implantar esse aplicativo para Windows Azure Web Sites a seguir [apêndice b: publicação um aplicativo ASP.NET MVC 4 usando a implantação da Web](#AppendixB).</span><span class="sxs-lookup"><span data-stu-id="55a2e-535">Additionally, you can deploy this application to Windows Azure Web Sites following [Appendix B: Publishing an ASP.NET MVC 4 Application using Web Deploy](#AppendixB).</span></span>


<a id="Summary"></a>
## <a name="summary"></a><span data-ttu-id="55a2e-536">Resumo</span><span class="sxs-lookup"><span data-stu-id="55a2e-536">Summary</span></span>

<span data-ttu-id="55a2e-537">Este laboratório o ajudará a entender o que há de novo no ASP.NET e desenvolvimento da Web no Visual Studio 2012 e como aproveitar a variedade de aprimoramentos no Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="55a2e-537">This lab helps you to understand what New in ASP.NET and Web Development in Visual Studio 2012 is and how to take advantage of the variety of enhancements in Visual Studio 2012.</span></span>

<span data-ttu-id="55a2e-538">Ao concluir este laboratório prático, você tem learnt como usar os novos recursos e aprimoramentos no Visual Studio 2012 editores CSS, JavaScript e HTML.</span><span class="sxs-lookup"><span data-stu-id="55a2e-538">By completing this Hands-On Lab, you have learnt how to use the new features and improvements in Visual Studio 2012 Editors for CSS, JavaScript and HTML.</span></span> <span data-ttu-id="55a2e-539">Além disso, você tem learnt como o Visual Studio 2012 implementa internos de empacotamento e minimização.</span><span class="sxs-lookup"><span data-stu-id="55a2e-539">In addition, you have learnt how Visual Studio 2012 implements built-in bundling and minification.</span></span>

<a id="AppendixA"></a>

<a id="Appendix_A_Installing_Visual_Studio_Express_2012_for_Web"></a>
## <a name="appendix-a-installing-visual-studio-express-2012-for-web"></a><span data-ttu-id="55a2e-540">Apêndice a: instalar o Visual Studio Express 2012 para Web</span><span class="sxs-lookup"><span data-stu-id="55a2e-540">Appendix A: Installing Visual Studio Express 2012 for Web</span></span>

<span data-ttu-id="55a2e-541">Você pode instalar **Microsoft Visual Studio Express 2012 para Web** ou outro &quot;Express&quot; versão usando o  **[Microsoft Web Platform Installer](https://www.microsoft.com/web/downloads/platform.aspx)** .</span><span class="sxs-lookup"><span data-stu-id="55a2e-541">You can install **Microsoft Visual Studio Express 2012 for Web** or another &quot;Express&quot; version using the **[Microsoft Web Platform Installer](https://www.microsoft.com/web/downloads/platform.aspx)**.</span></span> <span data-ttu-id="55a2e-542">As instruções a seguir guiá-lo pelas etapas necessárias para instalar o *Visual studio Express 2012 para Web* usando *Microsoft Web Platform Installer*.</span><span class="sxs-lookup"><span data-stu-id="55a2e-542">The following instructions guide you through the steps required to install *Visual studio Express 2012 for Web* using *Microsoft Web Platform Installer*.</span></span>

1. <span data-ttu-id="55a2e-543">Vá para [ [https://go.microsoft.com/?linkid=9810169](https://go.microsoft.com/?linkid=9810169)](https://go.microsoft.com/?linkid=9810169).</span><span class="sxs-lookup"><span data-stu-id="55a2e-543">Go to [[https://go.microsoft.com/?linkid=9810169](https://go.microsoft.com/?linkid=9810169)](https://go.microsoft.com/?linkid=9810169).</span></span> <span data-ttu-id="55a2e-544">Como alternativa, se você já tiver instalado o Web Platform Installer, você pode abri-la e procure o produto &quot; *Visual Studio Express 2012 para Web com o SDK do Windows Azure*&quot;.</span><span class="sxs-lookup"><span data-stu-id="55a2e-544">Alternatively, if you already have installed Web Platform Installer, you can open it and search for the product &quot;*Visual Studio Express 2012 for Web with Windows Azure SDK*&quot;.</span></span>
2. <span data-ttu-id="55a2e-545">Clique em **instalar agora**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-545">Click on **Install Now**.</span></span> <span data-ttu-id="55a2e-546">Se você não tem **Web Platform Installer** você será redirecionado para baixar e instalá-lo primeiro.</span><span class="sxs-lookup"><span data-stu-id="55a2e-546">If you do not have **Web Platform Installer** you will be redirected to download and install it first.</span></span>
3. <span data-ttu-id="55a2e-547">Uma vez **Web Platform Installer** é aberto, clique em **instalar** para iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="55a2e-547">Once **Web Platform Installer** is open, click **Install** to start the setup.</span></span>

    <span data-ttu-id="55a2e-548">![Instalar Visual Studio Express](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image59.png "instalar Visual Studio Express")</span><span class="sxs-lookup"><span data-stu-id="55a2e-548">![Install Visual Studio Express](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image59.png "Install Visual Studio Express")</span></span>

    <span data-ttu-id="55a2e-549">*Instalar Visual Studio Express*</span><span class="sxs-lookup"><span data-stu-id="55a2e-549">*Install Visual Studio Express*</span></span>
4. <span data-ttu-id="55a2e-550">Leia os termos e licenças de todos os produtos e clique em **aceito** para continuar.</span><span class="sxs-lookup"><span data-stu-id="55a2e-550">Read all the products' licenses and terms and click **I Accept** to continue.</span></span>

    ![Aceitar os termos de licença](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image60.png)

    <span data-ttu-id="55a2e-552">*Aceitar os termos de licença*</span><span class="sxs-lookup"><span data-stu-id="55a2e-552">*Accepting the license terms*</span></span>
5. <span data-ttu-id="55a2e-553">Aguarde até que o processo de download e instalação seja concluída.</span><span class="sxs-lookup"><span data-stu-id="55a2e-553">Wait until the downloading and installation process completes.</span></span>

    ![Progresso da instalação](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image61.png)

    <span data-ttu-id="55a2e-555">*Progresso da instalação*</span><span class="sxs-lookup"><span data-stu-id="55a2e-555">*Installation progress*</span></span>
6. <span data-ttu-id="55a2e-556">Quando a instalação for concluída, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-556">When the installation completes, click **Finish**.</span></span>

    ![Instalação concluída](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image62.png)

    <span data-ttu-id="55a2e-558">*Instalação concluída*</span><span class="sxs-lookup"><span data-stu-id="55a2e-558">*Installation completed*</span></span>
7. <span data-ttu-id="55a2e-559">Clique em **saída** para fechar o Web Platform Installer.</span><span class="sxs-lookup"><span data-stu-id="55a2e-559">Click **Exit** to close Web Platform Installer.</span></span>
8. <span data-ttu-id="55a2e-560">Para abrir o Visual Studio Express para Web, vá para o **iniciar** tela e comece a escrever &quot; **VS Express**&quot;, em seguida, clique no **VS Express para Web** lado a lado.</span><span class="sxs-lookup"><span data-stu-id="55a2e-560">To open Visual Studio Express for Web, go to the **Start** screen and start writing &quot;**VS Express**&quot;, then click on the **VS Express for Web** tile.</span></span>

    ![VS Express para o bloco de Web](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image63.png)

    <span data-ttu-id="55a2e-562">*VS Express para o bloco de Web*</span><span class="sxs-lookup"><span data-stu-id="55a2e-562">*VS Express for Web tile*</span></span>

* * *

<a id="AppendixB"></a>

<a id="Appendix_B_Publishing_an_ASPNET_MVC_4_Application_using_Web_Deploy"></a>
## <a name="appendix-b-publishing-an-aspnet-mvc-4-application-using-web-deploy"></a><span data-ttu-id="55a2e-563">Apêndice b: publicar um aplicativo ASP.NET MVC 4 usando a implantação da Web</span><span class="sxs-lookup"><span data-stu-id="55a2e-563">Appendix B: Publishing an ASP.NET MVC 4 Application using Web Deploy</span></span>

<span data-ttu-id="55a2e-564">Este apêndice mostram como criar um novo site do Portal de gerenciamento do Windows Azure e publicar o aplicativo que você obteve seguindo o laboratório, aproveitando o recurso de publicação de implantação da Web fornecido pelo Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="55a2e-564">This appendix will show you how to create a new web site from the Windows Azure Management Portal and publish the application you obtained by following the lab, taking advantage of the Web Deploy publishing feature provided by Windows Azure.</span></span>

<a id="Ex1Task1"></a>

<a id="Task_1_-_Creating_a_New_Web_Site_from_the_Windows_Azure_Portal"></a>
#### <a name="task-1---creating-a-new-web-site-from-the-windows-azure-portal"></a><span data-ttu-id="55a2e-565">Tarefa 1: criar um novo Site do Windows Azure Portal</span><span class="sxs-lookup"><span data-stu-id="55a2e-565">Task 1 - Creating a New Web Site from the Windows Azure Portal</span></span>

1. <span data-ttu-id="55a2e-566">Vá para o [Portal de gerenciamento do Windows Azure](https://manage.windowsazure.com/) e entre usando as credenciais da Microsoft associadas à sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="55a2e-566">Go to the [Windows Azure Management Portal](https://manage.windowsazure.com/) and sign in using the Microsoft credentials associated with your subscription.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55a2e-567">Com o Windows Azure, você pode hospedar 10 Sites da Web ASP.NET gratuitamente e, em seguida, dimensione conforme seu tráfego cresce.</span><span class="sxs-lookup"><span data-stu-id="55a2e-567">With Windows Azure you can host 10 ASP.NET Web Sites for free and then scale as your traffic grows.</span></span> <span data-ttu-id="55a2e-568">Você pode inscrever [aqui](http://aka.ms/aspnet-hol-azure).</span><span class="sxs-lookup"><span data-stu-id="55a2e-568">You can sign up [here](http://aka.ms/aspnet-hol-azure).</span></span>

    <span data-ttu-id="55a2e-569">![Faça logon no portal do Windows Azure](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image64.png "faça logon no portal do Windows Azure")</span><span class="sxs-lookup"><span data-stu-id="55a2e-569">![Log on to Windows Azure portal](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image64.png "Log on to Windows Azure portal")</span></span>

    <span data-ttu-id="55a2e-570">*Faça logon no Portal de gerenciamento do Azure do Windows*</span><span class="sxs-lookup"><span data-stu-id="55a2e-570">*Log on to Windows Azure Management Portal*</span></span>
2. <span data-ttu-id="55a2e-571">Clique em **novo** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="55a2e-571">Click **New** on the command bar.</span></span>

    <span data-ttu-id="55a2e-572">![Criando um novo Site](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image65.png "criar um novo Site")</span><span class="sxs-lookup"><span data-stu-id="55a2e-572">![Creating a new Web Site](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image65.png "Creating a new Web Site")</span></span>

    <span data-ttu-id="55a2e-573">*Criando um novo Site*</span><span class="sxs-lookup"><span data-stu-id="55a2e-573">*Creating a new Web Site*</span></span>
3. <span data-ttu-id="55a2e-574">Clique em **de computação** | **Site da Web**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-574">Click **Compute** | **Web Site**.</span></span> <span data-ttu-id="55a2e-575">Em seguida, selecione **criação rápida** opção.</span><span class="sxs-lookup"><span data-stu-id="55a2e-575">Then select **Quick Create** option.</span></span> <span data-ttu-id="55a2e-576">Forneça uma URL disponível para o novo site e clique em **Criar Site**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-576">Provide an available URL for the new web site and click **Create Web Site**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55a2e-577">Um Site do Windows Azure é o host para um aplicativo web em execução na nuvem que você pode controlar e gerenciar.</span><span class="sxs-lookup"><span data-stu-id="55a2e-577">A Windows Azure Web Site is the host for a web application running in the cloud that you can control and manage.</span></span> <span data-ttu-id="55a2e-578">A opção criação rápida permite que você implante um aplicativo web concluído ao Site do Windows Azure de fora do portal.</span><span class="sxs-lookup"><span data-stu-id="55a2e-578">The Quick Create option allows you to deploy a completed web application to the Windows Azure Web Site from outside the portal.</span></span> <span data-ttu-id="55a2e-579">Ele não inclui etapas para configurar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55a2e-579">It does not include steps for setting up a database.</span></span>

    <span data-ttu-id="55a2e-580">![Criando um novo Site usando a criação rápida](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image66.png "criar um novo Site usando a criação rápida")</span><span class="sxs-lookup"><span data-stu-id="55a2e-580">![Creating a new Web Site using Quick Create](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image66.png "Creating a new Web Site using Quick Create")</span></span>

    <span data-ttu-id="55a2e-581">*Criando um novo Site usando a criação rápida*</span><span class="sxs-lookup"><span data-stu-id="55a2e-581">*Creating a new Web Site using Quick Create*</span></span>
4. <span data-ttu-id="55a2e-582">Aguarde até que o novo **Site da Web** é criado.</span><span class="sxs-lookup"><span data-stu-id="55a2e-582">Wait until the new **Web Site** is created.</span></span>
5. <span data-ttu-id="55a2e-583">Depois que o Site da Web é criado, clique no link sob a **URL** coluna.</span><span class="sxs-lookup"><span data-stu-id="55a2e-583">Once the Web Site is created click the link under the **URL** column.</span></span> <span data-ttu-id="55a2e-584">Verifique se o novo Site da Web está funcionando.</span><span class="sxs-lookup"><span data-stu-id="55a2e-584">Check that the new Web Site is working.</span></span>

    <span data-ttu-id="55a2e-585">![Navegando para o novo site](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image67.png "navegando para o novo site")</span><span class="sxs-lookup"><span data-stu-id="55a2e-585">![Browsing to the new web site](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image67.png "Browsing to the new web site")</span></span>

    <span data-ttu-id="55a2e-586">*Navegando para o novo site*</span><span class="sxs-lookup"><span data-stu-id="55a2e-586">*Browsing to the new web site*</span></span>

    <span data-ttu-id="55a2e-587">![Site da Web em execução](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image68.png "site em execução")</span><span class="sxs-lookup"><span data-stu-id="55a2e-587">![Web site running](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image68.png "Web site running")</span></span>

    <span data-ttu-id="55a2e-588">*Site da Web em execução*</span><span class="sxs-lookup"><span data-stu-id="55a2e-588">*Web site running*</span></span>
6. <span data-ttu-id="55a2e-589">Acesse o portal e clique no nome do site sob o **nome** coluna para exibir as páginas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="55a2e-589">Go back to the portal and click the name of the web site under the **Name** column to display the management pages.</span></span>

    <span data-ttu-id="55a2e-590">![Abrir as páginas de gerenciamento do site da web](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image69.png "abrir páginas de gerenciamento do site")</span><span class="sxs-lookup"><span data-stu-id="55a2e-590">![Opening the web site management pages](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image69.png "Opening the web site management pages")</span></span>

    <span data-ttu-id="55a2e-591">*Abrir as páginas de gerenciamento do Site da Web*</span><span class="sxs-lookup"><span data-stu-id="55a2e-591">*Opening the Web Site management pages*</span></span>
7. <span data-ttu-id="55a2e-592">No **painel** página no **visão rápida** seção, clique o **baixar perfil de publicação** link.</span><span class="sxs-lookup"><span data-stu-id="55a2e-592">In the **Dashboard** page, under the **quick glance** section, click the **Download publish profile** link.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55a2e-593">O *perfil de publicação* contém todas as informações necessárias para publicar um aplicativo web para um site do Windows Azure para cada método de publicação habilitado.</span><span class="sxs-lookup"><span data-stu-id="55a2e-593">The *publish profile* contains all of the information required to publish a web application to a Windows Azure website for each enabled publication method.</span></span> <span data-ttu-id="55a2e-594">O perfil de publicação contém as URLs, as credenciais do usuário e cadeias de caracteres de banco de dados necessárias para se conectar e autenticar cada um dos pontos de extremidade para o qual um método de publicação está habilitado.</span><span class="sxs-lookup"><span data-stu-id="55a2e-594">The publish profile contains the URLs, user credentials and database strings required to connect to and authenticate against each of the endpoints for which a publication method is enabled.</span></span> <span data-ttu-id="55a2e-595">**Microsoft WebMatrix 2**, **Microsoft Visual Studio para Web Express** e **Microsoft Visual Studio 2012** oferecem suporte à leitura perfis de publicação para automatizar a configuração desses programas para publicação de aplicativos web para sites do Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="55a2e-595">**Microsoft WebMatrix 2**, **Microsoft Visual Studio Express for Web** and **Microsoft Visual Studio 2012** support reading publish profiles to automate configuration of these programs for publishing web applications to Windows Azure websites.</span></span>

    <span data-ttu-id="55a2e-596">![Baixando o site da web de perfil de publicação](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image70.png "baixando o site da web de perfil de publicação")</span><span class="sxs-lookup"><span data-stu-id="55a2e-596">![Downloading the web site publish profile](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image70.png "Downloading the web site publish profile")</span></span>

    <span data-ttu-id="55a2e-597">*Baixando o Site da Web de perfil de publicação*</span><span class="sxs-lookup"><span data-stu-id="55a2e-597">*Downloading the Web Site publish profile*</span></span>
8. <span data-ttu-id="55a2e-598">Baixe o arquivo de perfil de publicação para um local conhecido.</span><span class="sxs-lookup"><span data-stu-id="55a2e-598">Download the publish profile file to a known location.</span></span> <span data-ttu-id="55a2e-599">Mais neste exercício, você verá como usar esse arquivo para publicar um aplicativo web para um Windows Azure Web Sites do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="55a2e-599">Further in this exercise you will see how to use this file to publish a web application to a Windows Azure Web Sites from Visual Studio.</span></span>

    <span data-ttu-id="55a2e-600">![Salvando o arquivo de perfil de publicação](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image71.png "salvar o perfil de publicação")</span><span class="sxs-lookup"><span data-stu-id="55a2e-600">![Saving the publish profile file](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image71.png "Saving the publish profile")</span></span>

    <span data-ttu-id="55a2e-601">*Salvando o arquivo de perfil de publicação*</span><span class="sxs-lookup"><span data-stu-id="55a2e-601">*Saving the publish profile file*</span></span>

<a id="Ex1Task2"></a>

<a id="Task_2_-_Configuring_the_Database_Server"></a>
#### <a name="task-2---configuring-the-database-server"></a><span data-ttu-id="55a2e-602">Tarefa 2 – Configurando o servidor de banco de dados</span><span class="sxs-lookup"><span data-stu-id="55a2e-602">Task 2 - Configuring the Database Server</span></span>

<span data-ttu-id="55a2e-603">Se seu aplicativo utiliza o SQL Server bancos de dados que você precisará criar um servidor de banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="55a2e-603">If your application makes use of SQL Server databases you will need to create a SQL Database server.</span></span> <span data-ttu-id="55a2e-604">Se você deseja implantar um aplicativo simples que não usa o SQL Server, você pode ignorar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="55a2e-604">If you want to deploy a simple application that does not use SQL Server you might skip this task.</span></span>

1. <span data-ttu-id="55a2e-605">Você precisará de um servidor de banco de dados SQL para armazenar o banco de dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-605">You will need a SQL Database server for storing the application database.</span></span> <span data-ttu-id="55a2e-606">Você pode exibir os servidores de banco de dados SQL de sua assinatura no portal de gerenciamento do Windows Azure em **bancos de dados Sql** | **servidores** | **do servidor Painel**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-606">You can view the SQL Database servers from your subscription in the Windows Azure Management portal at **Sql Databases** | **Servers** | **Server's Dashboard**.</span></span> <span data-ttu-id="55a2e-607">Se você não tiver um servidor criado, você pode criar um usando o **adicionar** botão na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="55a2e-607">If you do not have a server created, you can create one using the **Add** button on the command bar.</span></span> <span data-ttu-id="55a2e-608">Anote o **nome do servidor e o URL, o nome de logon de administrador e senha**, pois você usará nas próximas tarefas.</span><span class="sxs-lookup"><span data-stu-id="55a2e-608">Take note of the **server name and URL, administrator login name and password**, as you will use them in the next tasks.</span></span> <span data-ttu-id="55a2e-609">Não crie o banco de dados, como ele será criado em um estágio posterior.</span><span class="sxs-lookup"><span data-stu-id="55a2e-609">Do not create the database yet, as it will be created in a later stage.</span></span>

    <span data-ttu-id="55a2e-610">![Painel do servidor de banco de dados SQL](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image72.png "painel de banco de dados do SQL Server")</span><span class="sxs-lookup"><span data-stu-id="55a2e-610">![SQL Database Server Dashboard](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image72.png "SQL Database Server Dashboard")</span></span>

    <span data-ttu-id="55a2e-611">*Painel de banco de dados do SQL Server*</span><span class="sxs-lookup"><span data-stu-id="55a2e-611">*SQL Database Server Dashboard*</span></span>
2. <span data-ttu-id="55a2e-612">A próxima tarefa, você testará a conexão de banco de dados do Visual Studio, por esse motivo, você precisa incluir seu endereço IP local na lista do servidor de **endereços IP permitidos**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-612">In the next task you will test the database connection from Visual Studio, for that reason you need to include your local IP address in the server's list of **Allowed IP Addresses**.</span></span> <span data-ttu-id="55a2e-613">Para fazer isso, clique em **configurar**, selecione o endereço IP do **endereço IP do cliente atual** e cole-o no **endereço IP inicial** e **oendereçoIPfinal** caixas de texto.</span><span class="sxs-lookup"><span data-stu-id="55a2e-613">To do that, click **Configure**, select the IP address from **Current Client IP Address** and paste it on the **Start IP Address** and **End IP Address** text boxes.</span></span> <span data-ttu-id="55a2e-614">Insira um nome para a regra e clique no ![add-client-ip-address-ok-button](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image73.png) botão.</span><span class="sxs-lookup"><span data-stu-id="55a2e-614">Enter a name for the rule and click the ![add-client-ip-address-ok-button](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image73.png) button.</span></span>

    ![Adicionar endereço IP do cliente](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image74.png)

    <span data-ttu-id="55a2e-616">*Adicionar endereço IP do cliente*</span><span class="sxs-lookup"><span data-stu-id="55a2e-616">*Adding Client IP Address*</span></span>
3. <span data-ttu-id="55a2e-617">Uma vez o **endereço IP do cliente** é adicionado para os endereços IP permitidos, clique em **salvar** para confirmar as alterações.</span><span class="sxs-lookup"><span data-stu-id="55a2e-617">Once the **Client IP Address** is added to the allowed IP addresses list, click on **Save** to confirm the changes.</span></span>

    ![Confirmar alterações](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image75.png)

    <span data-ttu-id="55a2e-619">*Confirmar alterações*</span><span class="sxs-lookup"><span data-stu-id="55a2e-619">*Confirm Changes*</span></span>

<a id="Ex1Task3"></a>

<a id="Task_3_-_Publishing_an_ASPNET_MVC_4_Application_using_Web_Deploy"></a>
#### <a name="task-3---publishing-an-aspnet-mvc-4-application-using-web-deploy"></a><span data-ttu-id="55a2e-620">Tarefa 3: publicar um aplicativo ASP.NET MVC 4 usando a implantação da Web</span><span class="sxs-lookup"><span data-stu-id="55a2e-620">Task 3 - Publishing an ASP.NET MVC 4 Application using Web Deploy</span></span>

1. <span data-ttu-id="55a2e-621">Volte para a solução do ASP.NET MVC 4.</span><span class="sxs-lookup"><span data-stu-id="55a2e-621">Go back to the ASP.NET MVC 4 solution.</span></span> <span data-ttu-id="55a2e-622">No **Solution Explorer**, com o botão direito no projeto de site da web e selecione **publicar**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-622">In the **Solution Explorer**, right-click the web site project and select **Publish**.</span></span>

    <span data-ttu-id="55a2e-623">![Publicar o aplicativo](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image76.png "a publicação do aplicativo")</span><span class="sxs-lookup"><span data-stu-id="55a2e-623">![Publishing the Application](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image76.png "Publishing the Application")</span></span>

    <span data-ttu-id="55a2e-624">*Publicar o site*</span><span class="sxs-lookup"><span data-stu-id="55a2e-624">*Publishing the web site*</span></span>
2. <span data-ttu-id="55a2e-625">Importe o perfil de publicação que você salvou na primeira tarefa.</span><span class="sxs-lookup"><span data-stu-id="55a2e-625">Import the publish profile you saved in the first task.</span></span>

    <span data-ttu-id="55a2e-626">![Importar o perfil de publicação](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image77.png "importar o perfil de publicação")</span><span class="sxs-lookup"><span data-stu-id="55a2e-626">![Importing the publish profile](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image77.png "Importing the publish profile")</span></span>

    <span data-ttu-id="55a2e-627">*Importar o perfil de publicação*</span><span class="sxs-lookup"><span data-stu-id="55a2e-627">*Importing publish profile*</span></span>
3. <span data-ttu-id="55a2e-628">Clique em **validar Conexão**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-628">Click **Validate Connection**.</span></span> <span data-ttu-id="55a2e-629">Quando a validação estiver concluída, clique em **próximo**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-629">Once Validation is complete click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55a2e-630">A validação é concluída depois que aparecer uma marca de seleção verde ao lado do botão Validar Conexão.</span><span class="sxs-lookup"><span data-stu-id="55a2e-630">Validation is complete once you see a green checkmark appear next to the Validate Connection button.</span></span>

    <span data-ttu-id="55a2e-631">![Validando a conexão](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image78.png "validação de conexão")</span><span class="sxs-lookup"><span data-stu-id="55a2e-631">![Validating connection](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image78.png "Validating connection")</span></span>

    <span data-ttu-id="55a2e-632">*Validação de conexão*</span><span class="sxs-lookup"><span data-stu-id="55a2e-632">*Validating connection*</span></span>
4. <span data-ttu-id="55a2e-633">No **configurações** página no **bancos de dados** seção, clique no botão ao lado da caixa de texto da sua conexão de banco de dados (ou seja, **DefaultConnection**).</span><span class="sxs-lookup"><span data-stu-id="55a2e-633">In the **Settings** page, under the **Databases** section, click the button next to your database connection's textbox (i.e. **DefaultConnection**).</span></span>

    <span data-ttu-id="55a2e-634">![Configuração de implantação da Web](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image79.png "configuração de implantação da Web")</span><span class="sxs-lookup"><span data-stu-id="55a2e-634">![Web deploy configuration](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image79.png "Web deploy configuration")</span></span>

    <span data-ttu-id="55a2e-635">*Configuração de implantação da Web*</span><span class="sxs-lookup"><span data-stu-id="55a2e-635">*Web deploy configuration*</span></span>
5. <span data-ttu-id="55a2e-636">Configure a conexão de banco de dados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="55a2e-636">Configure the database connection as follows:</span></span>

    - <span data-ttu-id="55a2e-637">No **nome do servidor** digite sua URL de servidor de banco de dados SQL usando o *tcp:* prefixo.</span><span class="sxs-lookup"><span data-stu-id="55a2e-637">In the **Server name** type your SQL Database server URL using the *tcp:* prefix.</span></span>
    - <span data-ttu-id="55a2e-638">Em **nome de usuário** digite seu nome de logon de administrador do servidor.</span><span class="sxs-lookup"><span data-stu-id="55a2e-638">In **User name** type your server administrator login name.</span></span>
    - <span data-ttu-id="55a2e-639">Em **senha** digite sua senha de logon de administrador do servidor.</span><span class="sxs-lookup"><span data-stu-id="55a2e-639">In **Password** type your server administrator login password.</span></span>
    - <span data-ttu-id="55a2e-640">Digite um novo nome de banco de dados, por exemplo: *MVC4SampleDB*.</span><span class="sxs-lookup"><span data-stu-id="55a2e-640">Type a new database name, for example: *MVC4SampleDB*.</span></span>

    <span data-ttu-id="55a2e-641">![Configurando a cadeia de caracteres de conexão de destino](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image80.png "Configurando a cadeia de caracteres de conexão de destino")</span><span class="sxs-lookup"><span data-stu-id="55a2e-641">![Configuring destination connection string](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image80.png "Configuring destination connection string")</span></span>

    <span data-ttu-id="55a2e-642">*Configurando a cadeia de caracteres de conexão de destino*</span><span class="sxs-lookup"><span data-stu-id="55a2e-642">*Configuring destination connection string*</span></span>
6. <span data-ttu-id="55a2e-643">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-643">Then click **OK**.</span></span> <span data-ttu-id="55a2e-644">Quando solicitado a criar o banco de dados, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-644">When prompted to create the database click **Yes**.</span></span>

    <span data-ttu-id="55a2e-645">![Criando o banco de dados](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image81.png "criar a cadeia de caracteres do banco de dados")</span><span class="sxs-lookup"><span data-stu-id="55a2e-645">![Creating the database](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image81.png "Creating the database string")</span></span>

    <span data-ttu-id="55a2e-646">*Criando o banco de dados*</span><span class="sxs-lookup"><span data-stu-id="55a2e-646">*Creating the database*</span></span>
7. <span data-ttu-id="55a2e-647">A cadeia de caracteres de conexão que você usará para se conectar ao banco de dados SQL no Windows Azure é mostrada na caixa de texto de Conexão padrão.</span><span class="sxs-lookup"><span data-stu-id="55a2e-647">The connection string you will use to connect to SQL Database in Windows Azure is shown within Default Connection textbox.</span></span> <span data-ttu-id="55a2e-648">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-648">Then click **Next**.</span></span>

    <span data-ttu-id="55a2e-649">![Cadeia de caracteres de Conexão que aponta para o banco de dados SQL](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image82.png "cadeia de caracteres de Conexão que aponta para o banco de dados SQL")</span><span class="sxs-lookup"><span data-stu-id="55a2e-649">![Connection string pointing to SQL Database](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image82.png "Connection string pointing to SQL Database")</span></span>

    <span data-ttu-id="55a2e-650">*Cadeia de caracteres de Conexão que aponta para o banco de dados SQL*</span><span class="sxs-lookup"><span data-stu-id="55a2e-650">*Connection string pointing to SQL Database*</span></span>
8. <span data-ttu-id="55a2e-651">No **visualização** , clique em **publicar**.</span><span class="sxs-lookup"><span data-stu-id="55a2e-651">In the **Preview** page, click **Publish**.</span></span>

    <span data-ttu-id="55a2e-652">![Publicar o aplicativo web](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image83.png "publicar o aplicativo web")</span><span class="sxs-lookup"><span data-stu-id="55a2e-652">![Publishing the web application](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image83.png "Publishing the web application")</span></span>

    <span data-ttu-id="55a2e-653">*Publicar o aplicativo web*</span><span class="sxs-lookup"><span data-stu-id="55a2e-653">*Publishing the web application*</span></span>
9. <span data-ttu-id="55a2e-654">Quando termina o processo de publicação, o navegador padrão abrirá o site da web publicado.</span><span class="sxs-lookup"><span data-stu-id="55a2e-654">Once the publishing process finishes, your default browser will open the published web site.</span></span>

    <span data-ttu-id="55a2e-655">![Aplicativo publicado no Windows Azure](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image84.png "aplicativo publicado no Windows Azure")</span><span class="sxs-lookup"><span data-stu-id="55a2e-655">![Application published to Windows Azure](whats-new-in-aspnet-and-web-development-in-visual-studio-2012/_static/image84.png "Application published to Windows Azure")</span></span>

    <span data-ttu-id="55a2e-656">*Aplicativos publicados no Windows Azure*</span><span class="sxs-lookup"><span data-stu-id="55a2e-656">*Application published to Windows Azure*</span></span>