---
uid: aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/introduction
title: Criando aplicativos de nuvem do mundo Real com o Azure | Microsoft Docs
author: MikeWasson
description: "Este livro eletrônico orienta você por meio de uma abordagem baseada em padrões para criar soluções de nuvem do mundo real. Os padrões se aplicam ao processo de desenvolvimento, bem como para um..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 06/12/2014
ms.topic: article
ms.assetid: accfa16a-ab15-4c26-9ad4-babdc2a77d2e
ms.technology: 
ms.prod: .net-framework
msc.legacyurl: /aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/introduction
msc.type: authoredcontent
ms.openlocfilehash: 4de0b52e0b4ae7ce00e7b07bce2decfc5068964a
ms.sourcegitcommit: 060879fcf3f73d2366b5c811986f8695fff65db8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2018
---
<a name="building-real-world-cloud-apps-with-azure"></a><span data-ttu-id="2c754-104">Criando aplicativos de nuvem do mundo Real com o Azure</span><span class="sxs-lookup"><span data-stu-id="2c754-104">Building Real-World Cloud Apps with Azure</span></span>
====================
<span data-ttu-id="2c754-105">por [Mike Wasson](https://github.com/MikeWasson), [Rick Anderson](https://github.com/Rick-Anderson), [Tom Dykstra](https://github.com/tdykstra)</span><span class="sxs-lookup"><span data-stu-id="2c754-105">by [Mike Wasson](https://github.com/MikeWasson), [Rick Anderson](https://github.com/Rick-Anderson), [Tom Dykstra](https://github.com/tdykstra)</span></span>

<span data-ttu-id="2c754-106">[Download corrigi-lo projeto](http://code.msdn.microsoft.com/Fix-It-app-for-Building-cdd80df4) ou [baixar livro eletrônico](http://blogs.msdn.com/b/microsoft_press/archive/2014/07/23/free-ebook-building-cloud-apps-with-microsoft-azure.aspx)</span><span class="sxs-lookup"><span data-stu-id="2c754-106">[Download Fix It Project](http://code.msdn.microsoft.com/Fix-It-app-for-Building-cdd80df4) or [Download E-book](http://blogs.msdn.com/b/microsoft_press/archive/2014/07/23/free-ebook-building-cloud-apps-with-microsoft-azure.aspx)</span></span>

> <span data-ttu-id="2c754-107">Este livro eletrônico orienta você por meio de uma abordagem baseada em padrões para criar soluções de nuvem do mundo real.</span><span class="sxs-lookup"><span data-stu-id="2c754-107">This e-book walks you through a patterns-based approach to building real-world cloud solutions.</span></span> <span data-ttu-id="2c754-108">Os padrões se aplicam ao processo de desenvolvimento, bem como a arquitetura e práticas de codificação.</span><span class="sxs-lookup"><span data-stu-id="2c754-108">The patterns apply to the development process as well as to architecture and coding practices.</span></span>
> 
> <span data-ttu-id="2c754-109">O conteúdo é baseado em uma apresentação desenvolvido por Scott Guthrie e entregue por ele na conferência de desenvolvedores norueguês (NDC) em junho de 2013 ([parte 1](http://vimeo.com/68215538), [parte 2](http://vimeo.com/68215602)) e no Microsoft Tech Ed Austrália no Setembro de 2013 ([parte 1](https://channel9.msdn.com/Events/TechEd/Australia/2013/AZR324), [parte 2](https://channel9.msdn.com/Events/TechEd/Australia/2013/AZR325)).</span><span class="sxs-lookup"><span data-stu-id="2c754-109">The content is based on a presentation developed by Scott Guthrie and delivered by him at the Norwegian Developers Conference (NDC) in June of 2013 ([part 1](http://vimeo.com/68215538), [part 2](http://vimeo.com/68215602)), and at Microsoft Tech Ed Australia in September, 2013 ([part 1](https://channel9.msdn.com/Events/TechEd/Australia/2013/AZR324), [part 2](https://channel9.msdn.com/Events/TechEd/Australia/2013/AZR325)).</span></span> <span data-ttu-id="2c754-110">[Muitos outros](more-patterns-and-guidance.md#acknowledgments) atualizado e aumentada o conteúdo durante a transição-lo de vídeo para forma escrita.</span><span class="sxs-lookup"><span data-stu-id="2c754-110">[Many others](more-patterns-and-guidance.md#acknowledgments) updated and augmented the content while transitioning it from video to written form.</span></span>


## <a name="intended-audience"></a><span data-ttu-id="2c754-111">Público-alvo</span><span class="sxs-lookup"><span data-stu-id="2c754-111">Intended Audience</span></span>

<span data-ttu-id="2c754-112">Os desenvolvedores que estiver curioso sobre o desenvolvimento para a nuvem, considerando uma mudança para a nuvem, ou que são novos para desenvolvimento em nuvem encontrará aqui uma visão geral dos conceitos mais importantes e práticas recomendadas que precisam saber.</span><span class="sxs-lookup"><span data-stu-id="2c754-112">Developers who are curious about developing for the cloud, considering a move to the cloud, or are new to cloud development will find here a concise overview of the most important concepts and practices they need to know.</span></span> <span data-ttu-id="2c754-113">Os conceitos são ilustrados com exemplos concretos e cada capítulo para outros recursos para obter informações mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="2c754-113">The concepts are illustrated with concrete examples, and each chapter links to other resources for more in-depth information.</span></span> <span data-ttu-id="2c754-114">Os exemplos e os links para recursos adicionais são estruturas da Microsoft e serviços, mas os princípios ilustrados se aplicam a outras estruturas de desenvolvimento da web e também para ambientes de nuvem.</span><span class="sxs-lookup"><span data-stu-id="2c754-114">The examples and the links to additional resources are for Microsoft frameworks and services, but the principles illustrated apply to other web development frameworks and cloud environments as well.</span></span>

<span data-ttu-id="2c754-115">Os desenvolvedores que já estão desenvolvendo para a nuvem podem descobrir ideias aqui que ajudarão a torná-los mais bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="2c754-115">Developers who are already developing for the cloud may find ideas here that will help make them more successful.</span></span> <span data-ttu-id="2c754-116">Cada capítulo na série pode ser lido independentemente, para que você pode escolher e escolha tópicos que você está interessado.</span><span class="sxs-lookup"><span data-stu-id="2c754-116">Each chapter in the series can be read independently, so you can pick and choose topics that you're interested in.</span></span>

<span data-ttu-id="2c754-117">Qualquer pessoa que é inspecionada de Scott Guthrie *nuvem aplicativos do mundo Real criando com o Azure* apresentação e deseja obter mais detalhes e as informações atualizadas descobrirá que aqui.</span><span class="sxs-lookup"><span data-stu-id="2c754-117">Anyone who watched Scott Guthrie's *Building Real World Cloud Apps with Azure* presentation and wants more details and updated information will find that here.</span></span>

<a id="patterns"></a>
## <a name="cloud-development-patterns"></a><span data-ttu-id="2c754-118">Padrões de desenvolvimento de nuvem</span><span class="sxs-lookup"><span data-stu-id="2c754-118">Cloud development patterns</span></span>

<span data-ttu-id="2c754-119">Este livro eletrônico explica que treze recomendadas padrões de desenvolvimento em nuvem.</span><span class="sxs-lookup"><span data-stu-id="2c754-119">This e-book explains thirteen recommended patterns for cloud development.</span></span> <span data-ttu-id="2c754-120">"Padrão" é usado aqui em um sentido mais amplo para significar uma maneira recomendada para fazer coisas: a melhor maneira de desenvolver, criar e codificar aplicativos de nuvem.</span><span class="sxs-lookup"><span data-stu-id="2c754-120">"Pattern" is used here in a broad sense to mean a recommended way to do things: how best to go about developing, designing, and coding cloud apps.</span></span> <span data-ttu-id="2c754-121">Estes são os padrões de chave que ajudarão "entram na pit de sucesso" Se você segui-los.</span><span class="sxs-lookup"><span data-stu-id="2c754-121">These are key patterns which will help you "fall into the pit of success" if you follow them.</span></span>

- <span data-ttu-id="2c754-122">[Automatizar tudo](automate-everything.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-122">[Automate everything](automate-everything.md).</span></span>

    - <span data-ttu-id="2c754-123">Use scripts para maximizar a eficiência e minimizar erros em processos repetitivos.</span><span class="sxs-lookup"><span data-stu-id="2c754-123">Use scripts to maximize efficiency and minimize errors in repetitive processes.</span></span>
    - <span data-ttu-id="2c754-124">Demonstração: Scripts de gerenciamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="2c754-124">Demo: Azure management scripts.</span></span>
- <span data-ttu-id="2c754-125">[Controle de origem](source-control.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-125">[Source control](source-control.md).</span></span> 

    - <span data-ttu-id="2c754-126">Configure a estrutura de ramificação em controle de origem para facilitar o fluxo de trabalho do DevOps.</span><span class="sxs-lookup"><span data-stu-id="2c754-126">Set up branching structure in source control to facilitate DevOps workflow.</span></span>
    - <span data-ttu-id="2c754-127">Demonstração: Adicione scripts ao controle de origem.</span><span class="sxs-lookup"><span data-stu-id="2c754-127">Demo: add scripts to source control.</span></span>
    - <span data-ttu-id="2c754-128">Demonstração: mantenha os dados confidenciais do controle de origem.</span><span class="sxs-lookup"><span data-stu-id="2c754-128">Demo: keep sensitive data out of source control.</span></span>
    - <span data-ttu-id="2c754-129">Demonstração: use o Git no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2c754-129">Demo: use Git in Visual Studio.</span></span>
- <span data-ttu-id="2c754-130">[Integração contínua e entrega](continuous-integration-and-continuous-delivery.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-130">[Continuous integration and delivery](continuous-integration-and-continuous-delivery.md).</span></span> 

    - <span data-ttu-id="2c754-131">Automatize a compilação e implantação com cada check-in de controle de origem.</span><span class="sxs-lookup"><span data-stu-id="2c754-131">Automate build and deployment with each source control check-in.</span></span>
- <span data-ttu-id="2c754-132">[Práticas recomendadas de desenvolvimento de Web](web-development-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-132">[Web development best practices](web-development-best-practices.md).</span></span> 

    - <span data-ttu-id="2c754-133">Mantenha a camada da web sem monitoração de estado.</span><span class="sxs-lookup"><span data-stu-id="2c754-133">Keep web tier stateless.</span></span>
    - <span data-ttu-id="2c754-134">Demonstração: escala e o dimensionamento automático em aplicativos da Web no serviço de aplicativo do Azure.</span><span class="sxs-lookup"><span data-stu-id="2c754-134">Demo: scaling and auto-scaling in Web Apps in Azure App Service.</span></span>
    - <span data-ttu-id="2c754-135">Evite o estado da sessão.</span><span class="sxs-lookup"><span data-stu-id="2c754-135">Avoid session state.</span></span>
    - <span data-ttu-id="2c754-136">Use um CDN.</span><span class="sxs-lookup"><span data-stu-id="2c754-136">Use a CDN.</span></span>
    - <span data-ttu-id="2c754-137">Use o modelo de programação assíncrona.</span><span class="sxs-lookup"><span data-stu-id="2c754-137">Use asynchronous programming model.</span></span>
    - <span data-ttu-id="2c754-138">Demonstração: assíncrona no ASP.NET MVC e o Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="2c754-138">Demo: async in ASP.NET MVC and Entity Framework.</span></span>
- <span data-ttu-id="2c754-139">[Logon único](single-sign-on.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-139">[Single sign-on](single-sign-on.md).</span></span> 

    - <span data-ttu-id="2c754-140">Introdução ao Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2c754-140">Introduction to Azure Active Directory.</span></span>
    - <span data-ttu-id="2c754-141">Demonstração: Crie um aplicativo ASP.NET que usa o Active Directory do Azure.</span><span class="sxs-lookup"><span data-stu-id="2c754-141">Demo: create an ASP.NET app that uses Azure Active Directory.</span></span>
- <span data-ttu-id="2c754-142">[Opções de armazenamento de dados](data-storage-options.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-142">[Data storage options](data-storage-options.md).</span></span> 

    - <span data-ttu-id="2c754-143">Tipos de armazenamentos de dados.</span><span class="sxs-lookup"><span data-stu-id="2c754-143">Types of data stores.</span></span>
    - <span data-ttu-id="2c754-144">Como escolher o repositório de dados à direita.</span><span class="sxs-lookup"><span data-stu-id="2c754-144">How to choose the right data store.</span></span>
    - <span data-ttu-id="2c754-145">Demonstração: Banco de dados SQL do Azure.</span><span class="sxs-lookup"><span data-stu-id="2c754-145">Demo: Azure SQL Database.</span></span>
- <span data-ttu-id="2c754-146">[Estratégias de particionamento de dados](data-partitioning-strategies.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-146">[Data partitioning strategies](data-partitioning-strategies.md).</span></span> 

    - <span data-ttu-id="2c754-147">Particionar os dados verticalmente, horizontalmente, ou ambos para facilitar o dimensionamento de um banco de dados relacional.</span><span class="sxs-lookup"><span data-stu-id="2c754-147">Partition data vertically, horizontally, or both to facilitate scaling a relational database.</span></span>
- <span data-ttu-id="2c754-148">[Armazenamento de blob não estruturados](unstructured-blob-storage.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-148">[Unstructured blob storage](unstructured-blob-storage.md).</span></span> 

    - <span data-ttu-id="2c754-149">Armazenar arquivos na nuvem usando o serviço blob.</span><span class="sxs-lookup"><span data-stu-id="2c754-149">Store files in the cloud by using the blob service.</span></span>
    - <span data-ttu-id="2c754-150">Demonstração: usando o armazenamento de blob no aplicativo corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="2c754-150">Demo: using blob storage in the Fix It app.</span></span>
- <span data-ttu-id="2c754-151">[Design sobreviver a falhas](design-to-survive-failures.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-151">[Design to survive failures](design-to-survive-failures.md).</span></span> 

    - <span data-ttu-id="2c754-152">Tipos de falhas.</span><span class="sxs-lookup"><span data-stu-id="2c754-152">Types of failures.</span></span>
    - <span data-ttu-id="2c754-153">Escopo da falha.</span><span class="sxs-lookup"><span data-stu-id="2c754-153">Failure Scope.</span></span>
    - <span data-ttu-id="2c754-154">Noções básicas sobre SLAs.</span><span class="sxs-lookup"><span data-stu-id="2c754-154">Understanding SLAs.</span></span>
- <span data-ttu-id="2c754-155">[Monitoramento e telemetria](monitoring-and-telemetry.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-155">[Monitoring and telemetry](monitoring-and-telemetry.md).</span></span> 

    - <span data-ttu-id="2c754-156">Por que você deve comprar um aplicativo de telemetria tanto escrever seu próprio código para instrumentar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2c754-156">Why you should both buy a telemetry app and write your own code to instrument your app.</span></span>
    - <span data-ttu-id="2c754-157">Demonstração: New Relic para o Azure</span><span class="sxs-lookup"><span data-stu-id="2c754-157">Demo: New Relic for Azure</span></span>
    - <span data-ttu-id="2c754-158">Demonstração: log de código no aplicativo corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="2c754-158">Demo: logging code in the Fix It app.</span></span>
    - <span data-ttu-id="2c754-159">Demonstração: injeção de dependência no aplicativo corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="2c754-159">Demo: dependency injection in the Fix It app.</span></span>
    - <span data-ttu-id="2c754-160">Demonstração: o suporte de registro em log internos no Azure.</span><span class="sxs-lookup"><span data-stu-id="2c754-160">Demo: built-in logging support in Azure.</span></span>
- <span data-ttu-id="2c754-161">[Tratamento de falhas transitórias](transient-fault-handling.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-161">[Transient fault handling](transient-fault-handling.md).</span></span> 

    - <span data-ttu-id="2c754-162">Use uma lógica de repetição/retirada inteligente para reduzir o efeito de falhas transitórias.</span><span class="sxs-lookup"><span data-stu-id="2c754-162">Use smart retry/back-off logic to mitigate the effect of transient failures.</span></span>
    - <span data-ttu-id="2c754-163">Demonstração: repetição/retirada no Entity Framework 6.</span><span class="sxs-lookup"><span data-stu-id="2c754-163">Demo: retry/back-off in Entity Framework 6.</span></span>
- <span data-ttu-id="2c754-164">[Cache distribuído](distributed-caching.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-164">[Distributed caching](distributed-caching.md).</span></span> 

    - <span data-ttu-id="2c754-165">Melhorar a escalabilidade e reduzir os custos de transações do banco de dados usando o cache distribuído.</span><span class="sxs-lookup"><span data-stu-id="2c754-165">Improve scalability and reduce database transaction costs by using distributed caching.</span></span>
- <span data-ttu-id="2c754-166">[Padrão de trabalho centrado em fila](queue-centric-work-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-166">[Queue-centric work pattern](queue-centric-work-pattern.md).</span></span> 

    - <span data-ttu-id="2c754-167">Habilitar a alta disponibilidade e melhorar a escalabilidade acoplamento flexível camadas web e de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2c754-167">Enable high availability and improve scalability by loosely coupling web and worker tiers.</span></span>
    - <span data-ttu-id="2c754-168">Demonstração: Filas de armazenamento do Azure no aplicativo corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="2c754-168">Demo: Azure storage queues in the Fix It app.</span></span>
- <span data-ttu-id="2c754-169">[Mais diretrizes e padrões de aplicativo de nuvem](more-patterns-and-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-169">[More cloud app patterns and guidance](more-patterns-and-guidance.md).</span></span>
- [<span data-ttu-id="2c754-170">Apêndice: o aplicativo de exemplo Fix It</span><span class="sxs-lookup"><span data-stu-id="2c754-170">Appendix: The Fix It Sample Application</span></span>](the-fix-it-sample-application.md)

    - <span data-ttu-id="2c754-171">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="2c754-171">Known Issues</span></span>
    - <span data-ttu-id="2c754-172">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="2c754-172">Best Practices</span></span>
    - <span data-ttu-id="2c754-173">Como baixar, criar, executar e implantar.</span><span class="sxs-lookup"><span data-stu-id="2c754-173">How to download, build, run, and deploy.</span></span>

<span data-ttu-id="2c754-174">Esses padrões se aplicam a todos os ambientes de nuvem, mas que ilustraremos usando exemplos com base em tecnologias da Microsoft e serviços, como o Visual Studio, o Team Foundation Service, o ASP.NET e o Azure.</span><span class="sxs-lookup"><span data-stu-id="2c754-174">These patterns apply to all cloud environments, but we'll illustrate them by using examples based on Microsoft technologies and services, such as Visual Studio, Team Foundation Service, ASP.NET, and Azure.</span></span>

<span data-ttu-id="2c754-175">Este restante deste capítulo apresenta o aplicativo de exemplo corrigir e os aplicativos Web no ambiente de nuvem do serviço de aplicativo do Azure que executa o aplicativo para corrigi-lo no.</span><span class="sxs-lookup"><span data-stu-id="2c754-175">This remainder of this chapter introduces the Fix It sample application and the Web Apps in Azure App Service cloud environment that the Fix It app runs in.</span></span>

<a id="fixit"></a>
## <a name="the-fix-it-sample-application"></a><span data-ttu-id="2c754-176">A exemplo de aplicativo de correção</span><span class="sxs-lookup"><span data-stu-id="2c754-176">The Fix it sample application</span></span>

<span data-ttu-id="2c754-177">A maioria dos exemplos de código mostrados neste livro eletrônico e capturas de tela baseiam-se o aplicativo corrigir originalmente desenvolvido pela [Scott Guthrie](https://weblogs.asp.net/scottgu/) para demonstrar as práticas e padrões de desenvolvimento de aplicativo de nuvem recomendado.</span><span class="sxs-lookup"><span data-stu-id="2c754-177">Most of the screen shots and code examples shown in this e-book are based on the Fix It app originally developed by [Scott Guthrie](https://weblogs.asp.net/scottgu/) to demonstrate recommended cloud app development patterns and practices.</span></span>

![Corrija-a página inicial do aplicativo](introduction/_static/image1.png)

<span data-ttu-id="2c754-179">O aplicativo de exemplo é um sistema de registro de item de trabalho simples.</span><span class="sxs-lookup"><span data-stu-id="2c754-179">The sample app is a simple work item ticketing system.</span></span> <span data-ttu-id="2c754-180">Quando você precisar de algo fixo, você cria um tíquete e atribuir a alguém e outras pode fazer logon e ver as permissões atribuídas a eles e marca tíquetes como concluído quando o trabalho é feito.</span><span class="sxs-lookup"><span data-stu-id="2c754-180">When you need something fixed, you create a ticket and assign it to someone, and others can log in and see the tickets assigned to them and mark tickets as completed when the work is done.</span></span>

<span data-ttu-id="2c754-181">É um projeto de web padrão do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2c754-181">It's a standard Visual Studio web project.</span></span> <span data-ttu-id="2c754-182">Ele se baseia no ASP.NET MVC e usa um banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c754-182">It is built on ASP.NET MVC and uses a SQL Server database.</span></span> <span data-ttu-id="2c754-183">Ele pode ser executada localmente no IIS Express e pode ser implantado para um Site do Azure para executar na nuvem.</span><span class="sxs-lookup"><span data-stu-id="2c754-183">It can run locally in IIS Express and can be deployed to a Azure Web Site to run in the cloud.</span></span> <span data-ttu-id="2c754-184">Você pode fazer logon usando autenticação de formulários e um banco de dados local ou por meio de um provedor social, como Google.</span><span class="sxs-lookup"><span data-stu-id="2c754-184">You can log in using forms authentication and a local database or by using a social provider such as Google.</span></span> <span data-ttu-id="2c754-185">(Posteriormente também mostraremos como fazer logon com uma conta organizacional do Active Directory.)</span><span class="sxs-lookup"><span data-stu-id="2c754-185">(Later we'll also show how to log in with an Active Directory organizational account.)</span></span>

![Página de logon](introduction/_static/image2.png)

<span data-ttu-id="2c754-187">Depois que você está conectado em você pode criar um tíquete, atribuí-lo a outra e carregue uma imagem do que você deseja obter corrigido.</span><span class="sxs-lookup"><span data-stu-id="2c754-187">Once you're logged in you can create a ticket, assign it to someone, and upload a picture of what you want to get fixed.</span></span>

![Criar uma tarefa corrigir](introduction/_static/image3.png)

![Corrija-a tarefa criada](introduction/_static/image4.png)

<span data-ttu-id="2c754-190">Você pode acompanhar o progresso de itens de trabalho criados por você, consulte permissões atribuídas a você, exibir detalhes de tíquete e itens de marca como concluído.</span><span class="sxs-lookup"><span data-stu-id="2c754-190">You can track the progress of work items you created, see tickets assigned to you, view ticket details, and mark items as completed.</span></span>

<span data-ttu-id="2c754-191">Este é um aplicativo muito simples de uma perspectiva de recurso, mas você verá como criá-lo para que ele pode dimensionar para milhões de usuários e serão resiliente a coisas como falhas de banco de dados e encerramentos de conexão.</span><span class="sxs-lookup"><span data-stu-id="2c754-191">This is a very simple app from a feature perspective, but you'll see how to build it so that it can scale to millions of users and will be resilient to things like database failures and connection terminations.</span></span> <span data-ttu-id="2c754-192">Você também verá como criar um fluxo de trabalho de desenvolvimento ágil e automatizada, o que permite que você inicie simples e tornar o aplicativo melhor e melhor iteração do ciclo de desenvolvimento, rápida e eficiente.</span><span class="sxs-lookup"><span data-stu-id="2c754-192">You'll also see how to create an automated and agile development workflow, which enables you to start simple and make the app better and better by iterating the development cycle efficiently and quickly.</span></span>

<a id="waws"></a>
## <a name="web-apps-in-azure-app-service"></a><span data-ttu-id="2c754-193">Aplicativos Web no serviço de aplicativo do Azure</span><span class="sxs-lookup"><span data-stu-id="2c754-193">Web Apps in Azure App Service</span></span>

<span data-ttu-id="2c754-194">Usado para o aplicativo para corrigir o ambiente de nuvem é um serviço do Azure que chamamos de Sites da Web.</span><span class="sxs-lookup"><span data-stu-id="2c754-194">The cloud environment used for the Fix It application is a service of Azure that we call Web Sites.</span></span> <span data-ttu-id="2c754-195">Esse serviço é uma maneira que você pode hospedar seu próprio aplicativo web no Azure sem a necessidade de criar VMs e mantê-los atualizados, instalar e configurar o IIS, etc. Podemos hospedar seu site em nosso VMs e forneça automaticamente o backup e recuperação e outros serviços para você.</span><span class="sxs-lookup"><span data-stu-id="2c754-195">This service is a way that you can host your own web app in Azure without having to create VMs and keep them updated, install and configure IIS, etc. We host your site on our VMs and automatically provide backup and recovery and other services for you.</span></span> <span data-ttu-id="2c754-196">O serviço de Sites da Web funciona com o ASP.NET, Node.js, PHP e Python.</span><span class="sxs-lookup"><span data-stu-id="2c754-196">The Web Sites service works with ASP.NET, Node.js, PHP, and Python.</span></span> <span data-ttu-id="2c754-197">Ele permite que você implante rapidamente usando o Visual Studio, implantação da Web, FTP, Git ou TFS.</span><span class="sxs-lookup"><span data-stu-id="2c754-197">It enables you to deploy very quickly using Visual Studio, Web Deploy, FTP, Git, or TFS.</span></span> <span data-ttu-id="2c754-198">É normalmente apenas alguns segundos entre a hora em que você iniciar uma implantação e a hora em que a atualização está disponível na Internet.</span><span class="sxs-lookup"><span data-stu-id="2c754-198">It's usually just a few seconds between the time you start a deployment and the time your update is available over the Internet.</span></span> <span data-ttu-id="2c754-199">É tudo gratuito começar, e você pode expandir conforme seu tráfego cresce.</span><span class="sxs-lookup"><span data-stu-id="2c754-199">It's all free to get started, and you can scale up as your traffic grows.</span></span>

<span data-ttu-id="2c754-200">Nos bastidores, aplicativos Web no serviço de aplicativo do Azure fornece muitos componentes de arquitetura e os recursos que você precisa criar por conta própria, se você for para hospedar um site da web usando o IIS em suas próprias VMs.</span><span class="sxs-lookup"><span data-stu-id="2c754-200">Behind the scenes, Web Apps in Azure App Service provides a lot of architectural components and features that you'd have to build yourself if you were going to host a web site using IIS on your own VMs.</span></span> <span data-ttu-id="2c754-201">Um componente é um ponto de extremidade de implantação que configura o IIS automaticamente e instala o aplicativo em como muitas máquinas virtuais que você deseja executar o seu site.</span><span class="sxs-lookup"><span data-stu-id="2c754-201">One component is a deployment end point that automatically configures IIS and installs your application on as many VMs as you want to run your site on.</span></span>

![Serviço de implantação](introduction/_static/image5.png)

<span data-ttu-id="2c754-203">Quando um usuário acessa o site da web, não atingem o IIS VMs diretamente, passam pelo [roteamento ARR (Application Request)](https://www.iis.net/downloads/microsoft/application-request-routing) balanceadores de carga.</span><span class="sxs-lookup"><span data-stu-id="2c754-203">When a user hits the web site, they don't hit the IIS VMs directly, they go through [Application Request Routing (ARR)](https://www.iis.net/downloads/microsoft/application-request-routing) load balancers.</span></span> <span data-ttu-id="2c754-204">Você pode usá-los com seus próprios servidores, mas a vantagem aqui é que ele estão configurados para você automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2c754-204">You can use these with your own servers, but the advantage here is that they're set up for you automatically.</span></span> <span data-ttu-id="2c754-205">Eles usam uma heurística inteligente que leva em consideração fatores como a afinidade de sessão, profundidade da fila no IIS, e o uso da CPU em cada computador direcione o tráfego para as máquinas virtuais que hospedam o site da web.</span><span class="sxs-lookup"><span data-stu-id="2c754-205">They use a smart heuristic that takes into account factors such as session affinity, queue depth in IIS, and CPU usage on each machine to direct traffic to the VMs that host your web site.</span></span>

![Balanceador de carga do ARR](introduction/_static/image6.png)

<span data-ttu-id="2c754-207">Se uma máquina falhar, Azure automaticamente extrair da rotação, gira uma nova instância de máquina virtual e direcionar o tráfego para a nova instância – tudo sem nenhum tempo de inatividade para seu aplicativo é iniciado.</span><span class="sxs-lookup"><span data-stu-id="2c754-207">If a machine goes down, Azure automatically pulls it from the rotation, spins up a new VM instance, and starts directing traffic to the new instance -- all with no down time for your application.</span></span>

![Recuperação automática de falha do computador](introduction/_static/image7.png)

<span data-ttu-id="2c754-209">Tudo isso ocorre automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2c754-209">All of this takes place automatically.</span></span> <span data-ttu-id="2c754-210">Tudo o que você precisa fazer é criar um site da web e implantar seu aplicativo, usando o Windows PowerShell, o Visual Studio ou o portal de gerenciamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="2c754-210">All you need to do is create a web site and deploy your application to it, using Windows PowerShell, Visual Studio, or the Azure management portal.</span></span>

<span data-ttu-id="2c754-211">Para obter um tutorial de passo a passo de rápida e fácil que mostra como criar um aplicativo web no Visual Studio e implantá-lo para um Site do Azure, consulte [Introdução ao Azure e ASP.NET](https://azure.microsoft.com/documentation/articles/web-sites-dotnet-get-started/).</span><span class="sxs-lookup"><span data-stu-id="2c754-211">For a quick and easy step-by-step tutorial that shows how to create a web application in Visual Studio and deploy it to a Azure Web Site, see [Get started with Azure and ASP.NET](https://azure.microsoft.com/documentation/articles/web-sites-dotnet-get-started/).</span></span>

<a id="summary"></a>
## <a name="summary"></a><span data-ttu-id="2c754-212">Resumo</span><span class="sxs-lookup"><span data-stu-id="2c754-212">Summary</span></span>

<span data-ttu-id="2c754-213">Esta introdução forneceu uma lista de tópicos aborda o catálogo, capturas de tela do aplicativo de exemplo e uma breve visão geral dos aplicativos Web no ambiente de nuvem do serviço de aplicativo do Azure.</span><span class="sxs-lookup"><span data-stu-id="2c754-213">This introduction has provided a list of topics the book will cover, screenshots of the sample application, and a brief overview of the Web Apps in Azure App Service cloud environment.</span></span> <span data-ttu-id="2c754-214">Uma das grandes vantagens do desenvolvimento de aplicativos de e para a nuvem é que ele é fácil de automatizar tarefas repetitivas de desenvolvimento, como criar um ambiente de teste e implantar seu código para ele.</span><span class="sxs-lookup"><span data-stu-id="2c754-214">One of the great advantages of developing apps in and for the cloud is that it's easy to automate repetitive development tasks such as creating a test environment and deploying your code to it.</span></span> <span data-ttu-id="2c754-215">Como fazer isto é o assunto do [próximo capítulo](automate-everything.md).</span><span class="sxs-lookup"><span data-stu-id="2c754-215">How to do that is the subject of the [next chapter](automate-everything.md).</span></span>

## <a name="resources"></a><span data-ttu-id="2c754-216">Recursos</span><span class="sxs-lookup"><span data-stu-id="2c754-216">Resources</span></span>

<span data-ttu-id="2c754-217">Para obter mais informações sobre os tópicos abordados neste capítulo, consulte os seguintes recursos.</span><span class="sxs-lookup"><span data-stu-id="2c754-217">For more information about the topics covered in this chapter, see the following resources.</span></span>

<span data-ttu-id="2c754-218">Documentação:</span><span class="sxs-lookup"><span data-stu-id="2c754-218">Documentation:</span></span>

- <span data-ttu-id="2c754-219">[Aplicativos no serviço de aplicativo do Azure Web](https://azure.microsoft.com/services/app-service/web/).</span><span class="sxs-lookup"><span data-stu-id="2c754-219">[Web Apps in Azure App Service](https://azure.microsoft.com/services/app-service/web/).</span></span> <span data-ttu-id="2c754-220">Página do portal para obter a documentação sobre os aplicativos Web do Azure.</span><span class="sxs-lookup"><span data-stu-id="2c754-220">Portal page for Azure documentation about Web Apps.</span></span>
- [<span data-ttu-id="2c754-221">Web de aplicativos, serviços de nuvem e VMs: quando usar o quê?</span><span class="sxs-lookup"><span data-stu-id="2c754-221">Web Apps, Cloud Services, and VMs: When to use which?</span></span>](https://azure.microsoft.com/documentation/articles/choose-web-site-cloud-service-vm/) <span data-ttu-id="2c754-222">WAWS, conforme mostrado neste capítulo é apenas uma das três maneiras que você pode executar aplicativos web no Azure.</span><span class="sxs-lookup"><span data-stu-id="2c754-222">WAWS as shown in this chapter is just one of three ways you can run web apps in Azure.</span></span> <span data-ttu-id="2c754-223">Este artigo explica as diferenças entre as três formas e fornece orientação sobre como escolher qual delas é adequada para seu cenário.</span><span class="sxs-lookup"><span data-stu-id="2c754-223">This article explains the differences between the three ways and gives guidance on how to choose which one is right for your scenario.</span></span> <span data-ttu-id="2c754-224">Como Sites, serviços de nuvem é um recurso de PaaS do Azure.</span><span class="sxs-lookup"><span data-stu-id="2c754-224">Like Web Sites, Cloud Services is a PaaS feature of Azure.</span></span> <span data-ttu-id="2c754-225">Máquinas virtuais são um recurso de IaaS.</span><span class="sxs-lookup"><span data-stu-id="2c754-225">VMs are an IaaS feature.</span></span> <span data-ttu-id="2c754-226">Para obter uma explicação de PaaS e IaaS, consulte o [opções de dados](data-storage-options.md#paasiaas) capítulo.</span><span class="sxs-lookup"><span data-stu-id="2c754-226">For an explanation of PaaS versus IaaS, see the [Data Options](data-storage-options.md#paasiaas) chapter.</span></span>

<span data-ttu-id="2c754-227">Vídeos:</span><span class="sxs-lookup"><span data-stu-id="2c754-227">Videos:</span></span>

- [<span data-ttu-id="2c754-228">Scott Guthrie começa na etapa 0 - o que é o sistema operacional em nuvem do Azure?</span><span class="sxs-lookup"><span data-stu-id="2c754-228">Scott Guthrie starts at Step 0 - What is the Azure Cloud OS?</span></span>](https://azure.microsoft.com/documentation/videos/what-is-the-cloud-os-scottgu/)
- <span data-ttu-id="2c754-229">[Arquitetura de Sites da Web - com Stefan Schackow](https://azure.microsoft.com/documentation/videos/why-azure-web-sites-plus-architecture/).</span><span class="sxs-lookup"><span data-stu-id="2c754-229">[Web Sites Architecture - with Stefan Schackow](https://azure.microsoft.com/documentation/videos/why-azure-web-sites-plus-architecture/).</span></span>
- <span data-ttu-id="2c754-230">[Recursos internos de Sites do Azure com Nir Mashkowski](https://channel9.msdn.com/Shows/Web+Camps+TV/Windows-Azure-Web-Sites-Internals-with-Nir-Mashkowski).</span><span class="sxs-lookup"><span data-stu-id="2c754-230">[Azure Web Sites Internals with Nir Mashkowski](https://channel9.msdn.com/Shows/Web+Camps+TV/Windows-Azure-Web-Sites-Internals-with-Nir-Mashkowski).</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="2c754-231">Avançar</span><span class="sxs-lookup"><span data-stu-id="2c754-231">Next</span></span>](automate-everything.md)