---
title: '方法: アプリケーションにカスタム作業ウィンドウを追加します。'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- task panes [Office development in Visual Studio], adding to application
- custom task panes [Office development in Visual Studio], adding to application
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 88ac74d0e2c666926c5b88976146878991729628
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63427924"
---
# <a name="how-to-add-a-custom-task-pane-to-an-application"></a>方法: アプリケーションにカスタム作業ウィンドウを追加します。
  VSTO アドインを使用して、上記にリストしたアプリケーションにカスタム作業ウィンドウを追加できます。 詳細については、次を参照してください。[カスタム作業ウィンドウ](../vsto/custom-task-panes.md)します。

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

> [!NOTE]
> 次の手順で参照している Visual Studio ユーザー インターフェイス要素の一部は、お使いのコンピューターでは名前や場所が異なる場合があります。 これらの要素は、使用している Visual Studio のエディションや独自の設定によって決まります。 詳細については、「[Visual Studio IDE のカスタマイズ](../ide/personalizing-the-visual-studio-ide.md)」を参照してください。

## <a name="add-a-custom-task-pane-to-an-application"></a>アプリケーションにカスタム作業ウィンドウを追加します。

### <a name="to-add-a-custom-task-pane-to-an-application"></a>カスタム作業ウィンドウをアプリケーションに追加するには

1. 上記のアプリケーションのいずれかの VSTO アドイン プロジェクトを開くか、作成します。 詳細については、「[方法 :Visual Studio で Office プロジェクトを作成する方法](../vsto/how-to-create-office-projects-in-visual-studio.md)」を参照してください。

2. **[プロジェクト]** メニューの **[ユーザー コントロールの追加]** をクリックします。

3. **新しい項目の追加** ダイアログ ボックスに新しいユーザー コントロールの名前に変更**MyUserControl**、 をクリックし、**追加**します。

     ユーザー コントロールがデザイナーで開きます。

4. 1 つまたは複数の Windows フォーム コントロールを追加、**ツールボックス**をユーザー コントロール。

5. 開く、 **ThisAddIn.cs**または**ThisAddIn.vb**コード ファイル。

6. `ThisAddIn` クラスに次のコードを追加します。 このコードは `MyUserControl` と <xref:Microsoft.Office.Tools.CustomTaskPane> のインスタンスを `ThisAddIn` クラスのメンバーとして宣言します。

     [!code-vb[Trin_TaskPaneBasic#1](../vsto/codesnippet/VisualBasic/Trin_TaskPaneBasic/ThisAddIn.vb#1)]
     [!code-csharp[Trin_TaskPaneBasic#1](../vsto/codesnippet/CSharp/Trin_TaskPaneBasic/ThisAddIn.cs#1)]

7. `ThisAddIn_Startup` イベント ハンドラーに次のコードを追加します。 このコードは <xref:Microsoft.Office.Tools.CustomTaskPane> オブジェクトを `MyUserControl` コレクションに追加することにより、新しい `CustomTaskPanes` を作成します。 コードでは、作業ウィンドウも表示されます。

     [!code-vb[Trin_TaskPaneBasic#2](../vsto/codesnippet/VisualBasic/Trin_TaskPaneBasic/ThisAddIn.vb#2)]
     [!code-csharp[Trin_TaskPaneBasic#2](../vsto/codesnippet/CSharp/Trin_TaskPaneBasic/ThisAddIn.cs#2)]

    > [!NOTE]
    > このコードは、カスタム作業ウィンドウをアプリケーションのアクティブ ウィンドウに関連付けます。 一部のアプリケーションでは、他のドキュメントやアプリケーションのアイテムで作業ウィンドウが表示されるように、このコードを変更する場合があります。 詳細については、次を参照してください。[カスタム作業ウィンドウ](../vsto/custom-task-panes.md)します。

## <a name="see-also"></a>関連項目
- [Office UI のカスタマイズ](../vsto/office-ui-customization.md)
- [カスタム作業ウィンドウ](../vsto/custom-task-panes.md)
- [チュートリアル: カスタム作業ウィンドウからアプリケーションを自動化します。](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md)
