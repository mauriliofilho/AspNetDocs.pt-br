---
uid: web-forms/overview/ajax-control-toolkit/animation/dynamically-controlling-updatepanel-animations-vb
title: Controlando dinamicamente animações UpdatePanel (VB) | Microsoft Docs
author: wenz
description: O controle de animação no ASP.NET AJAX Control Toolkit não é apenas um controle, mas uma estrutura inteira para adicionar animações a um controle. Para o conteúdo de um...
ms.author: riande
ms.date: 06/02/2008
ms.assetid: bea66072-59b6-42b4-98fa-211812f5925f
msc.legacyurl: /web-forms/overview/ajax-control-toolkit/animation/dynamically-controlling-updatepanel-animations-vb
msc.type: authoredcontent
ms.openlocfilehash: 97a52bd75fdf63ad62282afd9df772f0a9e4f931
ms.sourcegitcommit: 22fbd8863672c4ad6693b8388ad5c8e753fb41a2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74599713"
---
# <a name="dynamically-controlling-updatepanel-animations-vb"></a>Controlar dinamicamente animações UpdatePanel (VB)

por [Christian Wenz](https://github.com/wenz)

[Baixar código](https://download.microsoft.com/download/9/3/f/93f8daea-bebd-4821-833b-95205389c7d0/UpdatePanelAnimation2.vb.zip) ou [baixar PDF](https://download.microsoft.com/download/b/6/a/b6ae89ee-df69-4c87-9bfb-ad1eb2b23373/updatepanelanimation2VB.pdf)

> O controle de animação no ASP.NET AJAX Control Toolkit não é apenas um controle, mas uma estrutura inteira para adicionar animações a um controle. Para o conteúdo de um UpdatePanel, existe um extensor especial que depende muito da estrutura de animação: UpdatePanelAnimation. Ele também pode trabalhar junto com gatilhos UpdatePanel.

## <a name="overview"></a>{1&gt;Visão Geral&lt;1}

O controle de animação no ASP.NET AJAX Control Toolkit não é apenas um controle, mas uma estrutura inteira para adicionar animações a um controle. Para o conteúdo de um `UpdatePanel`, existe um extensor especial que depende muito da estrutura de animação: `UpdatePanelAnimation`. Ele também pode trabalhar junto com `UpdatePanel` gatilhos.

## <a name="steps"></a>Etapas

A primeira etapa é normalmente para incluir o `ScriptManager` na página para que a biblioteca ASP.NET AJAX seja carregada e o kit de ferramentas de controle possa ser usado:

[!code-aspx[Main](dynamically-controlling-updatepanel-animations-vb/samples/sample1.aspx)]

A animação neste cenário será aplicada a uma exibição da hora atual. Essas informações podem ser gravadas em um rótulo usando o método `Page_Load()` ou (para simplificar) o seguinte código embutido é usado:

[!code-aspx[Main](dynamically-controlling-updatepanel-animations-vb/samples/sample2.aspx)]

Além disso, um botão para disparar a atualização da hora é criado:

[!code-aspx[Main](dynamically-controlling-updatepanel-animations-vb/samples/sample3.aspx)]

Em seguida, esse código é colocado na seção `<ContentTemplate>` de um elemento `UpdatePanel`. O atributo de `UpdateMode` do painel deve ser definido como `"Conditional"`, já que somente gatilhos podem atualizar o conteúdo do painel. Na seção `<Triggers>` do `UpdatePanel`, um gatilho de postback assíncrono é criado e vinculado ao evento `Click` do botão. Portanto, se o usuário clicar no botão, a `UpdatePanel` será atualizada. Aqui está a marcação para o controle de `UpdatePanel`:

[!code-aspx[Main](dynamically-controlling-updatepanel-animations-vb/samples/sample4.aspx)]

Por fim, o `UpdatePanelAnimationExtender` deve ser configurado: defina o atributo `TargetControlID` para a ID do painel e defina uma animação dentro do extensor. O esmaecimento faz sentido, o que cria uma boa ênfase visual no tempo atualizado. A marcação do extensor pode ter a seguinte aparência:

[!code-aspx[Main](dynamically-controlling-updatepanel-animations-vb/samples/sample5.aspx)]

Execute o arquivo no navegador. Sempre que você clicar no botão, a hora atual será mostrada no painel, sempre esmaecida pela duração de um segundo.

[![a hora atual está esmaecida](dynamically-controlling-updatepanel-animations-vb/_static/image2.png)](dynamically-controlling-updatepanel-animations-vb/_static/image1.png)

A hora atual está esmaecida ([clique para exibir a imagem em tamanho normal](dynamically-controlling-updatepanel-animations-vb/_static/image3.png))

> [!div class="step-by-step"]
> [Anterior](animating-an-updatepanel-control-vb.md)
