---
title: '手順 1: Windows フォーム アプリケーション プロジェクトの作成 | Microsoft ドキュメント'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16ac2422-e720-4e3a-b511-bc2a54201a86
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2d494cb565e00633e36af35f230b0208ee0378a9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47547840"
---
# <a name="step-1-create-a-windows-forms-application-project"></a>手順 1: Windows フォーム アプリケーション プロジェクトの作成
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[手順 1: Windows フォーム アプリケーション プロジェクトを作成](https://docs.microsoft.com/visualstudio/ide/step-1-create-a-windows-forms-application-project)です。  
  
ピクチャ ビューアーを作成する場合、最初の手順は、Windows フォーム アプリケーション プロジェクトを作成することです。  
  
 ![ビデオへのリンク](../data-tools/media/playvideo.gif "PlayVideo")このトピックのビデオ版については、「[チュートリアル 1: Visual Basic によるピクチャ ビューアーの作成 - ビデオ 1](http://go.microsoft.com/fwlink/?LinkId=205209)」または「[チュートリアル 1: C# によるピクチャ ビューアーの作成 - ビデオ 1](http://go.microsoft.com/fwlink/?LinkId=205199)」を参照してください。 これらのビデオでは、旧バージョンの Visual Studio を使用しているため、一部のメニュー コマンドやその他のユーザー インターフェイス要素が若干異なります。 ただし、概念および手順は、現在のバージョンの Visual Studio でも同様です。  
  
### <a name="to-create-a-windows-forms-application-project"></a>Windows フォーム アプリケーション プロジェクトを作成するには  
  
1.  メニュー バーで、 **[ファイル]**、 **[新規作成]**、 **[プロジェクト]** の順にクリックします。 ダイアログ ボックスは次のようになります。  
  
     ![[新しいプロジェクト] ダイアログ ボックス](../ide/media/newprojectdialogcallouts.png "NewProjectDialogCallouts")  
[新しいプロジェクト] ダイアログ ボックス  
  
2.  **[インストールされたテンプレート]** で **[Visual C#]** または **[Visual Basic]** を選択します。  
  
3.  テンプレートの一覧で、**[Windows フォーム アプリケーション]** アイコンをクリックします。 新しいフォームに「**PictureViewer**」という名前を付け、**[OK]** をクリックします。  
  
     Visual Studio はプログラムのソリューションを作成します。 ソリューションは、プログラムに必要なすべてのプロジェクトとファイルのコンテナーとして機能します。 これらについては、このチュートリアルで後ほど詳しく説明します。  
  
4.  次の図は、Visual Studio に表示される内容を示しています。  
  
    > [!NOTE]
    >  ウィンドウ レイアウトは、この図とは多少異なる場合があります。 実際のウィンドウ レイアウトは、Visual Studio のバージョン、使用しているプログラミング言語、その他の要素によって異なります。 ただし、3 つのウィンドウがすべて表示されることを確認する必要があります。  
  
     ![IDE ウィンドウ](../ide/media/express-ideoverview-visio.png "Express_IDEOverview_Visio")  
IDE ウィンドウ  
  
     インターフェイスには、3 つのウィンドウ (メイン ウィンドウ、**ソリューション エクスプローラー**、**[プロパティ]** ウィンドウ) があります。  
  
     これらのウィンドウのいずれかが表示されていない場合は、メニュー バーで **[ウィンドウ]**、**[ウィンドウ レイアウトのリセット]** の順に選択して、既定のウィンドウ レイアウトを復元します。 メニュー コマンドを使用してウィンドウを表示することもできます。 メニュー バーで、**[表示]**、**[プロパティ ウィンドウ]** または **[ソリューション エクスプローラー]** の順に選択します。 他のウィンドウが開いている場合は、右上隅の **[閉じる]** (x) ボタンを選択して閉じます。  
  
5.  図に表示されているウィンドウは次のとおりです (左上から時計回り順)。  
  
    -   **メイン ウィンドウ** このウィンドウでは、フォームの操作やコードの編集など、ほとんどの作業を行います。 図では、このウィンドウでフォーム エディターにフォームが表示されています。 ウィンドウの上部には、**[スタート ページ]** タブと **[Form1.cs [デザイン]]** タブが表示されています  (Visual Basic では、タブの名前は .cs ではなく .vb で終わります)。  
  
    -   **ソリューション エクスプローラーウィンドウ** このウィンドウでは、ソリューション内のすべての項目を確認し、各項目に移動できます。 ファイルを選択すると、**[プロパティ]** ウィンドウの内容が変わります。 コード ファイル (Visual C# の場合は .cs、Visual Basic の場合は .vb で終わるファイル) を開くと、コード ファイルまたはコード ファイルのデザイナーが表示されます。 デザイナーは、ボタンやリストなどのコントロールを追加できるビジュアル サーフェイスです。 Visual Studio のフォームでは、デザイナーは Windows フォーム デザイナーと呼ばれます。  
  
    -   **[プロパティ] ウィンドウ** このウィンドウでは、他のウィンドウで選択した項目のプロパティを変更できます。 たとえば、Form1 を選択した場合、**Text** プロパティを設定してタイトルを変更し、**Backcolor** プロパティを設定して背景色を変更することができます。  
  
    > [!NOTE]
    >  **ソリューション エクスプローラー**の先頭行には、"**ソリューション 'PictureViewer' (1 プロジェクト)**" と表示されています。これは、Visual Studio によってソリューションが作成されたことを意味します。 ソリューションには複数のプロジェクトを含めることができますが、ここでは、プロジェクトを 1 つだけ含むソリューションを使用します。  
  
6.  メニュー バーで、**[ファイル]**、**[すべてを保存]** の順に選択します。  
  
     または、次の図に示すツール バーの **[すべて保存]** ボタンを選択します。  
  
     ![[すべてを保存] ツール バー ボタン](../ide/media/express-iconsaveall.png "Express_IconSaveAll")  
[すべてを保存] ツール バー ボタン  
  
     Visual Studio によって自動的にフォルダー名およびプロジェクト名が指定され、projects フォルダーにプロジェクトが保存されます。  
  
### <a name="to-continue-or-review"></a>続行または確認するには  
  
-   チュートリアルの次の手順に進むには、「[手順 2: プログラムの実行](../ide/step-2-run-your-program.md)」を参照してください。  
  
-   概要のトピックに戻るには、「[チュートリアル 1: ピクチャ ビューアーの作成](../ide/tutorial-1-create-a-picture-viewer.md)」を参照してください。


