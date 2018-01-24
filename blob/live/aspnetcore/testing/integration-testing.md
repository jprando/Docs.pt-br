---
title: "Integração de teste no núcleo do ASP.NET"
author: ardalis
description: "Como usar a integração do ASP.NET Core testes para garantir que os componentes de um aplicativo funcionem corretamente."
ms.author: riande
manager: wpickett
ms.date: 09/25/2017
ms.topic: article
ms.technology: aspnet
ms.prod: asp.net-core
uid: testing/integration-testing
ms.openlocfilehash: 8b0d741c05a723ad80fe812254c9a500a9fd9204
ms.sourcegitcommit: 3e303620a125325bb9abd4b2d315c106fb8c47fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/19/2018
---
# <a name="integration-testing-in-aspnet-core"></a><span data-ttu-id="db4f1-103">Integração de teste no núcleo do ASP.NET</span><span class="sxs-lookup"><span data-stu-id="db4f1-103">Integration testing in ASP.NET Core</span></span>

<span data-ttu-id="db4f1-104">Por [Steve Smith](https://ardalis.com/)</span><span class="sxs-lookup"><span data-stu-id="db4f1-104">By [Steve Smith](https://ardalis.com/)</span></span>

<span data-ttu-id="db4f1-105">Testes de integração garantem que componentes de um aplicativo funcionam corretamente quando montado juntos.</span><span class="sxs-lookup"><span data-stu-id="db4f1-105">Integration testing ensures that an application's components function correctly when assembled together.</span></span> <span data-ttu-id="db4f1-106">ASP.NET Core dá suporte a teste de integração usando estruturas de teste de unidade e um host da web internos de teste que pode ser usado para tratar as solicitações sem sobrecarga de rede.</span><span class="sxs-lookup"><span data-stu-id="db4f1-106">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="db4f1-107">[Exibir ou baixar código de exemplo](https://github.com/aspnet/Docs/tree/master/aspnetcore/testing/integration-testing/sample) ([como baixar](xref:tutorials/index#how-to-download-a-sample))</span><span class="sxs-lookup"><span data-stu-id="db4f1-107">[View or download sample code](https://github.com/aspnet/Docs/tree/master/aspnetcore/testing/integration-testing/sample) ([how to download](xref:tutorials/index#how-to-download-a-sample))</span></span>

## <a name="introduction-to-integration-testing"></a><span data-ttu-id="db4f1-108">Introdução ao teste de integração</span><span class="sxs-lookup"><span data-stu-id="db4f1-108">Introduction to integration testing</span></span>

<span data-ttu-id="db4f1-109">Testes de integração verificar que diferentes partes de um aplicativo funcionem corretamente.</span><span class="sxs-lookup"><span data-stu-id="db4f1-109">Integration tests verify that different parts of an application work correctly together.</span></span> <span data-ttu-id="db4f1-110">Ao contrário de [testes de unidade](https://docs.microsoft.com/dotnet/articles/core/testing/unit-testing-with-dotnet-test), testes de integração com frequência envolvem preocupações de infraestrutura de aplicativo, como um banco de dados, sistema de arquivos, recursos de rede, ou web solicitações e respostas.</span><span class="sxs-lookup"><span data-stu-id="db4f1-110">Unlike [Unit testing](https://docs.microsoft.com/dotnet/articles/core/testing/unit-testing-with-dotnet-test), integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="db4f1-111">Testes de unidade usam falsificações ou objetos fictícios no lugar essas preocupações, mas a finalidade de testes de integração é confirmar se o sistema está funcionando conforme o esperado com esses sistemas.</span><span class="sxs-lookup"><span data-stu-id="db4f1-111">Unit tests use fakes or mock objects in place of these concerns, but the purpose of integration tests is to confirm that the system works as expected with these systems.</span></span>

<span data-ttu-id="db4f1-112">Testes de integração, porque praticados maior de segmentos de código e como eles se basear em elementos de infraestrutura, tendem a ser ordens de magnitude menor do que testes de unidade.</span><span class="sxs-lookup"><span data-stu-id="db4f1-112">Integration tests, because they exercise larger segments of code and because they rely on infrastructure elements, tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="db4f1-113">Portanto, é uma boa ideia limitar quantos testes de integração que você escreve, especialmente se você pode testar o mesmo comportamento com um teste de unidade.</span><span class="sxs-lookup"><span data-stu-id="db4f1-113">Thus, it's a good idea to limit how many integration tests you write, especially if you can test the same behavior with a unit test.</span></span>

> [!NOTE]
> <span data-ttu-id="db4f1-114">Se algum comportamento pode ser testado usando um teste de unidade ou um teste de integração, prefira o teste de unidade, já que ele é quase sempre ser mais rápido.</span><span class="sxs-lookup"><span data-stu-id="db4f1-114">If some behavior can be tested using either a unit test or an integration test, prefer the unit test, since it will be almost always be faster.</span></span> <span data-ttu-id="db4f1-115">Você pode ter dúzias ou centenas de testes de unidade com muitas entradas diferentes, mas apenas uma série de testes de integração que cobrem os cenários mais importantes.</span><span class="sxs-lookup"><span data-stu-id="db4f1-115">You might have dozens or hundreds of unit tests with many different inputs but just a handful of integration tests covering the most important scenarios.</span></span>

<span data-ttu-id="db4f1-116">A lógica dentro de seus próprios métodos de teste é geralmente o domínio de testes de unidade.</span><span class="sxs-lookup"><span data-stu-id="db4f1-116">Testing the logic within your own methods is usually the domain of unit tests.</span></span> <span data-ttu-id="db4f1-117">Testar o funcionamento do seu aplicativo em sua estrutura, por exemplo, com ASP.NET Core, ou com um banco de dados é onde os testes de integração entram em ação.</span><span class="sxs-lookup"><span data-stu-id="db4f1-117">Testing how your application works within its framework, for example with ASP.NET Core, or with a database is where integration tests come into play.</span></span> <span data-ttu-id="db4f1-118">Ele não tem muitos testes de integração para confirmar que você é capaz de gravar uma linha para o banco de dados e lê-lo novamente.</span><span class="sxs-lookup"><span data-stu-id="db4f1-118">It doesn't take too many integration tests to confirm that you're able to write a row to the database and read it back.</span></span> <span data-ttu-id="db4f1-119">Não é necessário testar cada permutação possíveis do seu código de acesso de dados - você precisa testar suficiente para que você a certeza de que seu aplicativo está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="db4f1-119">You don't need to test every possible permutation of your data access code - you only need to test enough to give you confidence that your application is working properly.</span></span>

## <a name="integration-testing-aspnet-core"></a><span data-ttu-id="db4f1-120">Integração de teste ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="db4f1-120">Integration testing ASP.NET Core</span></span>

<span data-ttu-id="db4f1-121">Para obter configurou a testes de integração de execução, você precisará criar um projeto de teste, adicione uma referência ao projeto web ASP.NET Core e instalar um executor de teste.</span><span class="sxs-lookup"><span data-stu-id="db4f1-121">To get set up to run integration tests, you'll need to create a test project, add a reference to your ASP.NET Core web project, and install a test runner.</span></span> <span data-ttu-id="db4f1-122">Esse processo é descrito no [testes de unidade](https://docs.microsoft.com/dotnet/articles/core/testing/unit-testing-with-dotnet-test) documentação, junto com instruções mais detalhadas sobre como executar testes e recomendações para nomear suas classes de teste e testes.</span><span class="sxs-lookup"><span data-stu-id="db4f1-122">This process is described in the [Unit testing](https://docs.microsoft.com/dotnet/articles/core/testing/unit-testing-with-dotnet-test) documentation, along with more detailed instructions on running tests and recommendations for naming your tests and test classes.</span></span>

> [!NOTE]
> <span data-ttu-id="db4f1-123">Separe os testes de unidade e os testes de integração usando projetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="db4f1-123">Separate your unit tests and your integration tests using different projects.</span></span> <span data-ttu-id="db4f1-124">Isso ajuda a garantir que você não acidentalmente introduzir problemas de infraestrutura em seus testes de unidade e permite que você escolher facilmente qual conjunto de testes para executar.</span><span class="sxs-lookup"><span data-stu-id="db4f1-124">This helps ensure you don't accidentally introduce infrastructure concerns into your unit tests and lets you easily choose which set of tests to run.</span></span>

### <a name="the-test-host"></a><span data-ttu-id="db4f1-125">O Host de teste</span><span class="sxs-lookup"><span data-stu-id="db4f1-125">The Test Host</span></span>

<span data-ttu-id="db4f1-126">ASP.NET Core inclui um host de teste que pode ser adicionado a projetos de teste de integração e usado para hospedar o ASP.NET Core aplicativos, solicitações de serviço de teste sem a necessidade de um host da web real.</span><span class="sxs-lookup"><span data-stu-id="db4f1-126">ASP.NET Core includes a test host that can be added to integration test projects and used to host ASP.NET Core applications, serving test requests without the need for a real web host.</span></span> <span data-ttu-id="db4f1-127">O exemplo fornecido inclui um projeto de teste de integração que foi configurado para usar [xUnit](https://xunit.github.io) e o Host de teste.</span><span class="sxs-lookup"><span data-stu-id="db4f1-127">The provided sample includes an integration test project which has been configured to use [xUnit](https://xunit.github.io) and the Test Host.</span></span> <span data-ttu-id="db4f1-128">Ele usa o `Microsoft.AspNetCore.TestHost` pacote NuGet.</span><span class="sxs-lookup"><span data-stu-id="db4f1-128">It uses the `Microsoft.AspNetCore.TestHost` NuGet package.</span></span>

<span data-ttu-id="db4f1-129">Uma vez o `Microsoft.AspNetCore.TestHost` pacote está incluído no projeto, você poderá criar e configurar um `TestServer` em seus testes.</span><span class="sxs-lookup"><span data-stu-id="db4f1-129">Once the `Microsoft.AspNetCore.TestHost` package is included in the project, you'll be able to create and configure a `TestServer` in your tests.</span></span> <span data-ttu-id="db4f1-130">O teste a seguir mostra como verificar uma solicitação feita para a raiz de um site retorna "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="db4f1-130">The following test shows how to verify that a request made to the root of a site returns "Hello World!"</span></span> <span data-ttu-id="db4f1-131">e deve ser executado com êxito em relação ao padrão modelo de Web do ASP.NET Core vazio criado pelo Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="db4f1-131">and should run successfully against the default ASP.NET Core Empty Web template created by Visual Studio.</span></span>

[!code-csharp[Main](../testing/integration-testing/sample/test/PrimeWeb.IntegrationTests/PrimeWebDefaultRequestShould.cs?name=snippet_WebDefault&highlight=7,16,22)]

<span data-ttu-id="db4f1-132">Este teste é usando o padrão de organizar Act declaração.</span><span class="sxs-lookup"><span data-stu-id="db4f1-132">This test is using the Arrange-Act-Assert pattern.</span></span> <span data-ttu-id="db4f1-133">A etapa de organizar é feita no construtor, que cria uma instância de `TestServer`.</span><span class="sxs-lookup"><span data-stu-id="db4f1-133">The Arrange step is done in the constructor, which creates an instance of `TestServer`.</span></span> <span data-ttu-id="db4f1-134">Configurado `WebHostBuilder` será usado para criar um `TestHost`; neste exemplo, o `Configure` método do sistema em teste (SUT) `Startup` classe é passada para o `WebHostBuilder`.</span><span class="sxs-lookup"><span data-stu-id="db4f1-134">A configured `WebHostBuilder` will be used to create a `TestHost`; in this example, the `Configure` method from the system under test (SUT)'s `Startup` class is passed to the `WebHostBuilder`.</span></span> <span data-ttu-id="db4f1-135">Esse método será usado para configurar o pipeline de solicitação do `TestServer` identicamente a como o servidor SUT deve ser configurado.</span><span class="sxs-lookup"><span data-stu-id="db4f1-135">This method will be used to configure the request pipeline of the `TestServer` identically to how the SUT server would be configured.</span></span>

<span data-ttu-id="db4f1-136">Na parte do Act do teste, é feita uma solicitação para a `TestServer` instância para o caminho "/" e a resposta é lido novamente em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="db4f1-136">In the Act portion of the test, a request is made to the `TestServer` instance for the "/" path, and the response is read back into a string.</span></span> <span data-ttu-id="db4f1-137">Essa cadeia de caracteres é comparada com a cadeia de caracteres esperada de "Hello World!".</span><span class="sxs-lookup"><span data-stu-id="db4f1-137">This string is compared with the expected string of "Hello World!".</span></span> <span data-ttu-id="db4f1-138">Se elas corresponderem, o teste seja aprovado; Caso contrário, ele falhará.</span><span class="sxs-lookup"><span data-stu-id="db4f1-138">If they match, the test passes; otherwise, it fails.</span></span>

<span data-ttu-id="db4f1-139">Agora você pode adicionar alguns testes de integração adicionais para confirmar que o primo verificando funcionalidade funciona por meio do aplicativo web:</span><span class="sxs-lookup"><span data-stu-id="db4f1-139">Now you can add a few additional integration tests to confirm that the prime checking functionality works via the web application:</span></span>

[!code-csharp[Main](../testing/integration-testing/sample/test/PrimeWeb.IntegrationTests/PrimeWebCheckPrimeShould.cs?name=snippet_CheckPrime)]

<span data-ttu-id="db4f1-140">Observe que não é realmente está tentando testar a exatidão do verificador de número primo com esses testes, mas em vez disso, que o aplicativo web está fazendo o que você espera.</span><span class="sxs-lookup"><span data-stu-id="db4f1-140">Note that you're not really trying to test the correctness of the prime number checker with these tests but rather that the web application is doing what you expect.</span></span> <span data-ttu-id="db4f1-141">Você já tem cobertura de teste de unidade que proporciona confiança em `PrimeService`, como você pode ver aqui:</span><span class="sxs-lookup"><span data-stu-id="db4f1-141">You already have unit test coverage that gives you confidence in `PrimeService`, as you can see here:</span></span>

![Gerenciador de Testes](integration-testing/_static/test-explorer.png)

<span data-ttu-id="db4f1-143">Você pode aprender mais sobre os testes de unidade no [testes de unidade](https://docs.microsoft.com/dotnet/articles/core/testing/unit-testing-with-dotnet-test) artigo.</span><span class="sxs-lookup"><span data-stu-id="db4f1-143">You can learn more about the unit tests in the [Unit testing](https://docs.microsoft.com/dotnet/articles/core/testing/unit-testing-with-dotnet-test) article.</span></span>


### <a name="integration-testing-mvcrazor"></a><span data-ttu-id="db4f1-144">Integração de teste/Razor do Mvc</span><span class="sxs-lookup"><span data-stu-id="db4f1-144">Integration testing Mvc/Razor</span></span>

<span data-ttu-id="db4f1-145">Projetos de teste que contêm modos de exibição Razor exigem `<PreserveCompilationContext>` ser definido como true no *. csproj* arquivo:</span><span class="sxs-lookup"><span data-stu-id="db4f1-145">Test projects that contain Razor views require `<PreserveCompilationContext>` be set to true in the *.csproj* file:</span></span>


```xml
    <PreserveCompilationContext>true</PreserveCompilationContext>
```

<span data-ttu-id="db4f1-146">Este elemento de projetos irá gerar um erro semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="db4f1-146">Projects missing this element will generate an error similar to the following:</span></span>
```
Microsoft.AspNetCore.Mvc.Razor.Compilation.CompilationFailedException: 'One or more compilation failures occurred:
ooebhccx.1bd(4,62): error CS0012: The type 'Attribute' is defined in an assembly that is not referenced. You must add a reference to assembly 'netstandard, Version=2.0.0.0, Culture=neutral, PublicKeyToken=cc7b13ffcd2ddd51'.
```


## <a name="refactoring-to-use-middleware"></a><span data-ttu-id="db4f1-147">Para usar o middleware de refatoração</span><span class="sxs-lookup"><span data-stu-id="db4f1-147">Refactoring to use middleware</span></span>

<span data-ttu-id="db4f1-148">Refatoração é o processo de alteração de código do aplicativo para melhorar seu design sem alterar seu comportamento.</span><span class="sxs-lookup"><span data-stu-id="db4f1-148">Refactoring is the process of changing an application's code to improve its design without changing its behavior.</span></span> <span data-ttu-id="db4f1-149">Idealmente deve ser feito quando há um conjunto de passar os testes, pois esses ajuda garantir o que comportamento do sistema permanece a mesma antes e após as alterações.</span><span class="sxs-lookup"><span data-stu-id="db4f1-149">It should ideally be done when there is a suite of passing tests, since these help ensure the system's behavior remains the same before and after the changes.</span></span> <span data-ttu-id="db4f1-150">Examinar a maneira na qual o primo lógica de verificação é implementado no aplicativo da web `Configure` método, consulte:</span><span class="sxs-lookup"><span data-stu-id="db4f1-150">Looking at the way in which the prime checking logic is implemented in the web application's `Configure` method, you see:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.Run(async (context) =>
    {
        if (context.Request.Path.Value.Contains("checkprime"))
        {
            int numberToCheck;
            try
            {
                numberToCheck = int.Parse(context.Request.QueryString.Value.Replace("?", ""));
                var primeService = new PrimeService();
                if (primeService.IsPrime(numberToCheck))
                {
                    await context.Response.WriteAsync($"{numberToCheck} is prime!");
                }
                else
                {
                    await context.Response.WriteAsync($"{numberToCheck} is NOT prime!");
                }
            }
            catch
            {
                await context.Response.WriteAsync("Pass in a number to check in the form /checkprime?5");
            }
        }
        else
        {
            await context.Response.WriteAsync("Hello World!");
        }
    });
}
```

<span data-ttu-id="db4f1-151">Esse código funciona, mas está longe de como você deseja implementar esse tipo de funcionalidade em um aplicativo ASP.NET Core, até mesmo simple como este é.</span><span class="sxs-lookup"><span data-stu-id="db4f1-151">This code works, but it's far from how you would like to implement this kind of functionality in an ASP.NET Core application, even as simple as this is.</span></span> <span data-ttu-id="db4f1-152">Imagine que o `Configure` método seria semelhante, se necessário para adicionar essa quantidade código para ele sempre que você adicionar outro ponto de extremidade de URL!</span><span class="sxs-lookup"><span data-stu-id="db4f1-152">Imagine what the `Configure` method would look like if you needed to add this much code to it every time you add another URL endpoint!</span></span>

<span data-ttu-id="db4f1-153">Adição de uma opção a ser considerada [MVC](xref:mvc/overview) para o aplicativo e criando um controlador para lidar com a verificação principal.</span><span class="sxs-lookup"><span data-stu-id="db4f1-153">One option to consider is adding [MVC](xref:mvc/overview) to the application and creating a controller to handle the prime checking.</span></span> <span data-ttu-id="db4f1-154">No entanto, supondo que você atualmente não precisa de qualquer outra MVC funcionalidade, que é um bit exageros.</span><span class="sxs-lookup"><span data-stu-id="db4f1-154">However, assuming you don't currently need any other MVC functionality, that's a bit overkill.</span></span>

<span data-ttu-id="db4f1-155">No entanto, você pode tirar proveito do ASP.NET Core [middleware](xref:fundamentals/middleware), que nos ajudarão a encapsular o primo verificação lógica em sua própria classe e obter melhor [separação de preocupações](http://deviq.com/separation-of-concerns/) no `Configure` método.</span><span class="sxs-lookup"><span data-stu-id="db4f1-155">You can, however, take advantage of ASP.NET Core [middleware](xref:fundamentals/middleware), which will help us encapsulate the prime checking logic in its own class and achieve better [separation of concerns](http://deviq.com/separation-of-concerns/) in the `Configure` method.</span></span>

<span data-ttu-id="db4f1-156">Para permitir que o caminho do middleware usa a ser especificado como um parâmetro para a classe de middleware espera um `RequestDelegate` e um `PrimeCheckerOptions` instância em seu construtor.</span><span class="sxs-lookup"><span data-stu-id="db4f1-156">You want to allow the path the middleware uses to be specified as a parameter, so the middleware class expects a `RequestDelegate` and a `PrimeCheckerOptions` instance in its constructor.</span></span> <span data-ttu-id="db4f1-157">Se o caminho da solicitação não corresponde ao que este middleware configurado para esperar, basta chamar o próximo middleware da cadeia e não fazer nada.</span><span class="sxs-lookup"><span data-stu-id="db4f1-157">If the path of the request doesn't match what this middleware is configured to expect, you simply call the next middleware in the chain and do nothing further.</span></span> <span data-ttu-id="db4f1-158">O restante do código de implementação que estava no `Configure` está agora no `Invoke` método.</span><span class="sxs-lookup"><span data-stu-id="db4f1-158">The rest of the implementation code that was in `Configure` is now in the `Invoke` method.</span></span>

> [!NOTE]
> <span data-ttu-id="db4f1-159">Desde que o middleware depende do `PrimeService` serviço, você também está solicitando uma instância do serviço com o construtor.</span><span class="sxs-lookup"><span data-stu-id="db4f1-159">Since the middleware depends on the `PrimeService` service, you're also requesting an instance of this service with the constructor.</span></span> <span data-ttu-id="db4f1-160">A estrutura oferecer esse serviço por meio de [injeção de dependência](xref:fundamentals/dependency-injection), supondo que ele tiver sido configurado, por exemplo, em `ConfigureServices`.</span><span class="sxs-lookup"><span data-stu-id="db4f1-160">The framework will provide this service via [Dependency Injection](xref:fundamentals/dependency-injection), assuming it has been configured, for example in `ConfigureServices`.</span></span>

[!code-csharp[Main](../testing/integration-testing/sample/src/PrimeWeb/Middleware/PrimeCheckerMiddleware.cs?highlight=39-63)]

<span data-ttu-id="db4f1-161">Como este middleware atua como um ponto de extremidade da cadeia de delegado solicitação quando o caminho corresponde, não há nenhuma chamada para `_next.Invoke` quando este middleware manipula a solicitação.</span><span class="sxs-lookup"><span data-stu-id="db4f1-161">Since this middleware acts as an endpoint in the request delegate chain when its path matches, there is no call to `_next.Invoke` when this middleware handles the request.</span></span>

<span data-ttu-id="db4f1-162">Com este middleware em vigor e alguns útil métodos de extensão criados para facilitar a configuração, o refatorado `Configure` método tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="db4f1-162">With this middleware in place and some helpful extension methods created to make configuring it easier, the refactored `Configure` method looks like this:</span></span>

[!code-csharp[Main](../testing/integration-testing/sample/src/PrimeWeb/Startup.cs?highlight=9&range=19-33)]

<span data-ttu-id="db4f1-163">Seguindo essa refatoração estiver certo de que o aplicativo web ainda funciona como antes, desde que os testes de integração estão passando.</span><span class="sxs-lookup"><span data-stu-id="db4f1-163">Following this refactoring, you're confident that the web application still works as before, since your integration tests are all passing.</span></span>

> [!NOTE]
> <span data-ttu-id="db4f1-164">É uma boa ideia para confirmar as alterações ao controle de origem depois de concluir uma refatoração e transmitir seus testes.</span><span class="sxs-lookup"><span data-stu-id="db4f1-164">It's a good idea to commit your changes to source control after you complete a refactoring and your tests pass.</span></span> <span data-ttu-id="db4f1-165">Se você está praticando desenvolvimento orientado por testes, [considere a adição de confirmação para o ciclo de vermelho-verde-refatorar](https://ardalis.com/rgrc-is-the-new-red-green-refactor-for-test-first-development).</span><span class="sxs-lookup"><span data-stu-id="db4f1-165">If you're practicing Test Driven Development, [consider adding Commit to your Red-Green-Refactor cycle](https://ardalis.com/rgrc-is-the-new-red-green-refactor-for-test-first-development).</span></span>

## <a name="resources"></a><span data-ttu-id="db4f1-166">Recursos</span><span class="sxs-lookup"><span data-stu-id="db4f1-166">Resources</span></span>

* [<span data-ttu-id="db4f1-167">Teste de unidade</span><span class="sxs-lookup"><span data-stu-id="db4f1-167">Unit testing</span></span>](https://docs.microsoft.com/dotnet/articles/core/testing/unit-testing-with-dotnet-test)
* [<span data-ttu-id="db4f1-168">Middleware</span><span class="sxs-lookup"><span data-stu-id="db4f1-168">Middleware</span></span>](xref:fundamentals/middleware)
* [<span data-ttu-id="db4f1-169">Testando os controladores</span><span class="sxs-lookup"><span data-stu-id="db4f1-169">Testing controllers</span></span>](xref:mvc/controllers/testing)