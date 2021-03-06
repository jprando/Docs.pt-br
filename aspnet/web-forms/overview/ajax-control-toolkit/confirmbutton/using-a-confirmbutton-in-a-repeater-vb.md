---
uid: web-forms/overview/ajax-control-toolkit/confirmbutton/using-a-confirmbutton-in-a-repeater-vb
title: Usando um ConfirmButton em um repetidor (VB) | Microsoft Docs
author: wenz
description: "O Kit de ferramentas de controle AJAX do extensor de ConfirmButton cria um Sim/não pop-up quando o usuário clica em um botão (incluindo controle LinkButton). Somente se Sim for..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 06/02/2008
ms.topic: article
ms.assetid: 18c31709-3f9d-4d93-8b01-f1356bf610b4
ms.technology: dotnet-webforms
ms.prod: .net-framework
msc.legacyurl: /web-forms/overview/ajax-control-toolkit/confirmbutton/using-a-confirmbutton-in-a-repeater-vb
msc.type: authoredcontent
ms.openlocfilehash: 5da8491c157ad6f35c2c25803680f262a35ce6e1
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2017
---
<a name="using-a-confirmbutton-in-a-repeater-vb"></a>Usando um ConfirmButton em um repetidor (VB)
====================
por [Christian Wenz](https://github.com/wenz)

[Baixar o código](http://download.microsoft.com/download/8/6/d/86dea6c6-bb92-4fa6-aa14-f8c0f82100f5/ConfirmButton1.vb.zip) ou [baixar PDF](http://download.microsoft.com/download/b/6/a/b6ae89ee-df69-4c87-9bfb-ad1eb2b23373/confirmbutton1VB.pdf)

> O Kit de ferramentas de controle AJAX do extensor de ConfirmButton cria um Sim/não pop-up quando o usuário clica em um botão (incluindo controle LinkButton). Somente se Sim for selecionada, a ação do botão é executada, caso contrário cancelada. Isso também é possível em um repetidor.


## <a name="overview"></a>Visão Geral

O Kit de ferramentas de controle AJAX do extensor de ConfirmButton cria um Sim/não pop-up quando o usuário clica em um botão (incluindo controle LinkButton). Somente se Sim for selecionada, a ação do botão é executada, caso contrário cancelada. Isso também é possível em um repetidor.

## <a name="steps"></a>Etapas

Em primeiro lugar, uma fonte de dados é necessária. Este exemplo usa o banco de dados AdventureWorks e o Microsoft SQL Server 2005 Express Edition. O banco de dados é uma parte opcional de uma instalação do Visual Studio (incluindo a edição express) e também está disponível como um download separado em [https://go.microsoft.com/fwlink/?LinkId=64064](https://go.microsoft.com/fwlink/?LinkId=64064). O banco de dados AdventureWorks faz parte dos bancos de dados de exemplo e exemplos do SQL Server 2005 (download em [https://www.microsoft.com/downloads/details.aspx?FamilyID=e719ecf7-9f46-4312-af89-6ad8702e4e6e&amp;DisplayLang = en](https://www.microsoft.com/downloads/details.aspx?FamilyID=e719ecf7-9f46-4312-af89-6ad8702e4e6e&amp;DisplayLang=en)). A maneira mais fácil de configurar o banco de dados é usar o Microsoft SQL Server Management Studio Express ([https://www.microsoft.com/downloads/details.aspx? FamilyID = c243a5ae-4bd1-4e3d-94b8-5a0f62bf7796&amp;DisplayLang = en](https://www.microsoft.com/downloads/details.aspx?FamilyID=c243a5ae-4bd1-4e3d-94b8-5a0f62bf7796&amp;DisplayLang=en)) e conecte o `AdventureWorks.mdf` arquivo de banco de dados.

Para este exemplo, vamos supor que a instância do SQL Server 2005 Express Edition é chamada `SQLEXPRESS` e reside no mesmo computador que o servidor web; isso também é a configuração padrão. Se sua configuração for diferente, você precisa se adaptar as informações de conexão para o banco de dados.

Para ativar a funcionalidade do ASP.NET AJAX e o Kit de ferramentas de controle, o `ScriptManager` controle deve ser colocado em qualquer lugar na página (mas dentro do `<form>` elemento):

[!code-aspx[Main](using-a-confirmbutton-in-a-repeater-vb/samples/sample1.aspx)]

Em seguida, uma fonte de dados é necessária. Para simplificar, somente as primeiras cinco entradas na tabela de fornecedores de AdventureWorks são recuperadas. Observe que ao usar o Assistente do Visual Studio para criar a fonte de dados, o nome da tabela (`Vendors`) atualmente não está corretamente prefixado com `Purchasing`. A seguinte marcação está correto:

[!code-aspx[Main](using-a-confirmbutton-in-a-repeater-vb/samples/sample2.aspx)]

Esta fonte de dados, em seguida, pode ser usada dentro de um repetidor. Como de costume, o `DataBinder.Eval()` método recupera dados da fonte de dados. O `ConfirmButtonExtender` controle deve ser colocado dentro de `<ItemTemplate>` seção do repetidor para que ele apareça para cada entrada na fonte de dados.

[!code-aspx[Main](using-a-confirmbutton-in-a-repeater-vb/samples/sample3.aspx)]


[![Botão Confirmar aparece ao lado de cada entrada da fonte de dados](using-a-confirmbutton-in-a-repeater-vb/_static/image2.png)](using-a-confirmbutton-in-a-repeater-vb/_static/image1.png)

Botão Confirmar aparece ao lado de cada entrada da fonte de dados ([clique para exibir a imagem em tamanho normal](using-a-confirmbutton-in-a-repeater-vb/_static/image3.png))

>[!div class="step-by-step"]
[Anterior](using-a-confirmbutton-in-a-repeater-cs.md)
