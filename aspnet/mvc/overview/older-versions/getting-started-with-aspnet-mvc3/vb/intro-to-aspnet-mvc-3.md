---
uid: mvc/overview/older-versions/getting-started-with-aspnet-mvc3/vb/intro-to-aspnet-mvc-3
title: Introdução ao ASP.NET MVC 3 (VB) | Microsoft Docs
author: Rick-Anderson
description: Este tutorial ensinará as noções básicas da criação de um aplicativo Web ASP.NET MVC usando o Microsoft Visual Web Developer 2010 Express Service Pack 1, que é...
ms.author: riande
ms.date: 01/12/2011
ms.assetid: a1b3d789-93b4-487f-b90d-80c9c9b4f8fa
msc.legacyurl: /mvc/overview/older-versions/getting-started-with-aspnet-mvc3/vb/intro-to-aspnet-mvc-3
msc.type: authoredcontent
ms.openlocfilehash: 24f7de303ef7f5a457bd509ecc6bd0e3be7e3d9d
ms.sourcegitcommit: 7709c0a091b8d55b7b33bad8849f7b66b23c3d72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77456295"
---
# <a name="intro-to-aspnet-mvc-3-vb"></a>Introdução ao ASP.NET MVC 3 (VB)

por [Rick Anderson](https://twitter.com/RickAndMSFT)

> Este tutorial ensinará as noções básicas da criação de um aplicativo Web ASP.NET MVC usando o Microsoft Visual Web Developer 2010 Express Service Pack 1, que é uma versão gratuita do Microsoft Visual Studio. Antes de começar, verifique se você instalou os pré-requisitos listados abaixo. Você pode instalar todos eles clicando no seguinte link: [Web Platform Installer](https://www.microsoft.com/web/gallery/install.aspx?appid=VWD2010SP1Pack). Como alternativa, você pode instalar os pré-requisitos individualmente usando os seguintes links:
> 
> - [Pré-requisitos do Visual Studio Web Developer Express SP1](https://www.microsoft.com/web/gallery/install.aspx?appid=VWD2010SP1Pack)
> - [Atualização de ferramentas do ASP.NET MVC 3](https://www.microsoft.com/web/gallery/install.aspx?appsxml=&amp;appid=MVC3)
> - [SQL Server Compact 4,0](https://www.microsoft.com/web/gallery/install.aspx?appid=SQLCE;SQLCEVSTools_4_0)(suporte + ferramentas de tempo de execução)
> 
> Se você estiver usando o Visual Studio 2010 em vez do Visual Web Developer 2010, instale os pré-requisitos clicando no seguinte link: [pré-requisitos do Visual Studio 2010](https://www.microsoft.com/web/gallery/install.aspx?appsxml=&amp;appid=VS2010SP1Pack).
> 
> Um projeto do Visual Web Developer com código-fonte VB.NET está disponível para acompanhar este tópico. [Baixe a versão do VB.net](https://code.msdn.microsoft.com/Introduction-to-MVC-3-10d1b098). Se preferir C#, alterne para a [ C# versão](../cs/intro-to-aspnet-mvc-3.md) deste tutorial.

Este tutorial ensinará as noções básicas da criação de um aplicativo Web ASP.NET MVC usando o Microsoft Visual Web Developer 2010 Express Service Pack 1, que é uma versão gratuita do Microsoft Visual Studio. Antes de começar, verifique se você instalou os pré-requisitos listados abaixo. Você pode instalar todos eles clicando no seguinte link: [Web Platform Installer](https://www.microsoft.com/web/gallery/install.aspx?appid=VWD2010SP1Pack). Como alternativa, você pode instalar os pré-requisitos individualmente usando os seguintes links:

- [Pré-requisitos do Visual Studio Web Developer Express SP1](https://www.microsoft.com/web/gallery/install.aspx?appid=VWD2010SP1Pack)
- [Atualização de ferramentas do ASP.NET MVC 3](https://www.microsoft.com/web/gallery/install.aspx?appsxml=&amp;appid=MVC3)
- [SQL Server Compact 4,0](https://www.microsoft.com/web/gallery/install.aspx?appid=SQLCE;SQLCEVSTools_4_0)(suporte + ferramentas de tempo de execução)

Se você estiver usando o Visual Studio 2010 em vez do Visual Web Developer 2010, instale os pré-requisitos clicando no seguinte link: [pré-requisitos do Visual Studio 2010](https://www.microsoft.com/web/gallery/install.aspx?appsxml=&amp;appid=VS2010SP1Pack).

Um projeto do Visual Web Developer com o código-fonte VB está disponível para acompanhar este tópico. [Baixe a versão do VB aqui](https://code.msdn.microsoft.com/Project/Download/FileDownload.aspx?ProjectName=aspnetmvcsamples&amp;DownloadId=14824). Se preferir CSharp, mude para a [versão Csharp](../cs/intro-to-aspnet-mvc-3.md) deste tutorial.

## <a name="what-youll-build"></a>O que você vai construir

Você implementará um aplicativo simples de listagem de filmes que dá suporte à criação, edição e listagem de filmes de um banco de dados. Abaixo estão duas capturas de tela do aplicativo que você criará. Ele inclui uma página que exibe uma lista de filmes de um banco de dados:

[![MoviesWithVariousSm](intro-to-aspnet-mvc-3/_static/image2.png)](intro-to-aspnet-mvc-3/_static/image1.png)

O aplicativo também permite que você adicione, edite e exclua filmes, bem como veja detalhes sobre aqueles individuais. Todos os cenários de entrada de dados incluem validação para garantir que os dados armazenados no banco de dado estejam corretos.

[![createforms](intro-to-aspnet-mvc-3/_static/image4.png)](intro-to-aspnet-mvc-3/_static/image3.png)

## <a name="skills-youll-learn"></a>Qualificações que você aprenderá

Eis o que você vai aprender:

- Como criar um novo projeto MVC do ASP.NET
- Como criar um novo banco de dados usando Entity Framework código-primeiro
- Como criar controladores e exibições do ASP.NET MVC
- Como recuperar e exibir dados
- Como editar dados e habilitar a validação de dados

## <a name="getting-started"></a>Introdução

Comece executando o Visual Web Developer 2010 Express ("VWD" para curto) e selecione **novo projeto** na página **inicial** .

O Visual Web Developer é um IDE ou ambiente de desenvolvimento integrado. Assim como você usa o Microsoft Word para escrever documentos, você usará um IDE para criar aplicativos. No Visual Web Developer há uma barra de ferramentas ao longo da parte superior mostrando várias opções disponíveis para você. Há também um menu que fornece outra maneira de executar tarefas no IDE. (Por exemplo, em vez de selecionar **novo projeto** na página **inicial** , você pode usar o menu e selecionar **arquivo** &gt; **novo projeto**.)

[![](intro-to-aspnet-mvc-3/_static/image6.png)](intro-to-aspnet-mvc-3/_static/image5.png)

## <a name="creating-your-first-application"></a>Criando seu primeiro aplicativo

Você pode criar aplicativos usando sua escolha de Visual Basic ou Visual C# como linguagem de programação. Para este tutorial, selecione Visual Basic à esquerda e, em seguida, selecione **aplicativo Web ASP.NET MVC 3**. Nomeie seu projeto como "MvcMovie" e clique em **OK**.

![1NewMVCproj_sm](intro-to-aspnet-mvc-3/_static/image7.png)

Na caixa de diálogo **novo projeto do ASP.NET MVC 3** , selecione **aplicativo de Internet**. Deixe o **Razor** como o mecanismo de exibição padrão.

![1InternetAppRazor_SM](intro-to-aspnet-mvc-3/_static/image8.png)

Clique em **OK**. O Visual Web Developer usou um modelo padrão para o projeto ASP.NET MVC que você acabou de criar, portanto, você tem um aplicativo funcional agora sem fazer nada! Este é um "Olá, Mundo!" simples projeto, e é um bom lugar para iniciar seu aplicativo.

[![](intro-to-aspnet-mvc-3/_static/image10.png)](intro-to-aspnet-mvc-3/_static/image9.png)

No menu **Depuração**, selecione **Iniciar Depuração**.

![](intro-to-aspnet-mvc-3/_static/image11.png)

Observe que o atalho de teclado para iniciar a depuração é F5.

F5 faz com que o Visual Web Developer inicie um servidor Web de desenvolvimento e execute seu aplicativo Web. Em seguida, o VWD inicia um navegador e abre a home page do aplicativo. Observe que a barra de endereços do navegador indica `localhost` e não algo como `example.com`. Isso ocorre porque `localhost` sempre aponta para seu próprio computador local, que nesse caso está executando o aplicativo que você acabou de criar. Quando o VWD executa um projeto Web, uma porta aleatória é usada para o projeto. Na imagem abaixo, o número da porta aleatória é 43246. Seu projeto provavelmente usará um número de porta diferente.

![](intro-to-aspnet-mvc-3/_static/image12.png)

Esse modelo padrão fornece duas páginas para você visitar e uma página de logon básica. Vamos alterar como esse aplicativo funciona e aprender um pouco sobre o ASP.NET MVC no processo. Feche o navegador e vamos alterar algum código.

> [!div class="step-by-step"]
> [Próximo](adding-a-controller.md)
