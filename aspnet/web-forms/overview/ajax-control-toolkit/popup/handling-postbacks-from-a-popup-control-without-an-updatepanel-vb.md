---
uid: web-forms/overview/ajax-control-toolkit/popup/handling-postbacks-from-a-popup-control-without-an-updatepanel-vb
title: Manipulando postbacks de um controle Popup sem um UpdatePanel (VB) | Microsoft Docs
author: wenz
description: O extensor PopupControl no AJAX Control Toolkit oferece uma maneira fácil de disparar um popup quando qualquer outro controle é ativado. Quando um postback ocorre no Su...
ms.author: riande
ms.date: 06/02/2008
ms.assetid: a0b9186c-0912-4fff-916a-6d17e696a50b
msc.legacyurl: /web-forms/overview/ajax-control-toolkit/popup/handling-postbacks-from-a-popup-control-without-an-updatepanel-vb
msc.type: authoredcontent
ms.openlocfilehash: aaecf77c1d25f2c99ef4e9948d79fc01b837169b
ms.sourcegitcommit: 22fbd8863672c4ad6693b8388ad5c8e753fb41a2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74611720"
---
# <a name="handling-postbacks-from-a-popup-control-without-an-updatepanel-vb"></a>Tratamento de postbacks de um controle pop-up sem um UpdatePanel (VB)

por [Christian Wenz](https://github.com/wenz)

[Baixar código](https://download.microsoft.com/download/9/3/f/93f8daea-bebd-4821-833b-95205389c7d0/PopupControl3.vb.zip) ou [baixar PDF](https://download.microsoft.com/download/2/d/c/2dc10e34-6983-41d4-9c08-f78f5387d32b/popupcontrol3VB.pdf)

> O extensor PopupControl no AJAX Control Toolkit oferece uma maneira fácil de disparar um popup quando qualquer outro controle é ativado. Quando ocorre um postback nesse painel e há vários painéis na página, é difícil determinar qual painel foi clicado.

## <a name="overview"></a>{1&gt;Visão Geral&lt;1}

O extensor PopupControl no AJAX Control Toolkit oferece uma maneira fácil de disparar um popup quando qualquer outro controle é ativado. Quando ocorre um postback nesse painel e há vários painéis na página, é difícil determinar qual painel foi clicado.

## <a name="steps"></a>Etapas

Ao usar um `PopupControl` com um postback, mas sem ter uma `UpdatePanel` na página, o kit de ferramentas de controle não oferece uma maneira de determinar qual elemento de cliente disparou o Popup que, por sua vez, causou o postback. No entanto, um pequeno truque fornece uma solução alternativa para esse cenário.

Em primeiro lugar, aqui está a configuração básica: duas caixas de texto que disparam o mesmo pop-up, um calendário. Dois `PopupControlExtenders` trazer caixas de texto e pop-up juntos.

[!code-aspx[Main](handling-postbacks-from-a-popup-control-without-an-updatepanel-vb/samples/sample1.aspx)]

A ideia básica é adicionar um campo de formulário oculto no elemento &lt;`form`&gt; que contém a caixa de texto que abriu o Popup:

[!code-aspx[Main](handling-postbacks-from-a-popup-control-without-an-updatepanel-vb/samples/sample2.aspx)]

Quando a página é carregada, o código JavaScript adiciona um manipulador de eventos a ambas as caixas de texto: sempre que o usuário clica em uma caixa de texto, seu nome é gravado no campo de formulário oculto:

[!code-html[Main](handling-postbacks-from-a-popup-control-without-an-updatepanel-vb/samples/sample3.html)]

No código do servidor, o valor do campo oculto deve ser lido. Como os campos de formulário ocultos são triviais para manipular, é necessária uma abordagem de lista de permissões para validar o valor oculto. Depois que a caixa de texto correta tiver sido identificada, a data do calendário será gravada nela.

[!code-aspx[Main](handling-postbacks-from-a-popup-control-without-an-updatepanel-vb/samples/sample4.aspx)]

[![o calendário aparece quando o usuário clica na caixa de texto](handling-postbacks-from-a-popup-control-without-an-updatepanel-vb/_static/image2.png)](handling-postbacks-from-a-popup-control-without-an-updatepanel-vb/_static/image1.png)

O calendário é exibido quando o usuário clica na caixa de texto ([clique para exibir a imagem em tamanho normal](handling-postbacks-from-a-popup-control-without-an-updatepanel-vb/_static/image3.png))

[![clicar em uma data a coloca na caixa de texto](handling-postbacks-from-a-popup-control-without-an-updatepanel-vb/_static/image5.png)](handling-postbacks-from-a-popup-control-without-an-updatepanel-vb/_static/image4.png)

Clicar em uma data a coloca na caixa de texto ([clique para exibir a imagem em tamanho normal](handling-postbacks-from-a-popup-control-without-an-updatepanel-vb/_static/image6.png))

> [!div class="step-by-step"]
> [Anterior](handling-postbacks-from-a-popup-control-with-an-updatepanel-vb.md)
