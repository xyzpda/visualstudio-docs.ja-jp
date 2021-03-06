---
title: WPF アプリケーションでルックアップ テーブルを作成する
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- data [WPF], displaying
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio]
- displaying data, WPF
- WPF [WPF], data
- WPF Designer, data binding
- data binding, WPF
ms.assetid: 56a1fbff-c7e8-4187-a1c1-ffd17024bc1b
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: a2a2179a759bc11a9466361d3c8cc2df45c12f20
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72648592"
---
# <a name="create-lookup-tables-in-wpf-applications"></a>WPF アプリケーションでルックアップ テーブルを作成する

用語*参照テーブル*(*参照バインド*と呼ばれることもあります) は、別のテーブルの外部キーフィールドの値に基づいて1つのデータテーブルの情報を表示するコントロールを表します。 参照テーブルを作成するには、 **[データソース]** ウィンドウで親テーブルまたはオブジェクトのメインノードを、関連付けられている子テーブルの列またはプロパティに既にバインドされているコントロールにドラッグします。

たとえば、販売データベースの `Orders` テーブルであれば、次のように使用されます。 @No__t_0 テーブルの各レコードには、どの顧客が注文を配置したかを示す `CustomerID` が含まれています。 @No__t_0 は、`Customers` テーブル内の顧客レコードを指す外部キーです。 @No__t_0 テーブルから注文の一覧を表示する場合は、`CustomerID` ではなく実際の顧客名を表示することができます。 顧客名は `Customers` テーブルにあるため、顧客名を表示するルックアップテーブルを作成する必要があります。 参照テーブルは、`Orders` レコードの `CustomerID` 値を使用してリレーションシップをナビゲートし、顧客名を返します。

## <a name="to-create-a-lookup-table"></a>ルックアップ テーブルを作成するには

1. 次のいずれかの種類のデータソースを関連データと共にプロジェクトに追加します。

    - データセットまたは Entity Data Model。

    - WCF Data Service、WCF サービス、または web サービス。 詳細については、「[方法: サービスのデータに接続する](../data-tools/how-to-connect-to-data-in-a-service.md)」を参照してください。

    - オブジェクト。 詳細については、「 [Visual Studio でのオブジェクトへのバインド](bind-objects-in-visual-studio.md)」を参照してください。

    > [!NOTE]
    > ルックアップテーブルを作成するには、2つの関連するテーブルまたはオブジェクトがプロジェクトのデータソースとして存在している必要があります。

2. **WPF デザイナー**を開き、 **[データソース]** ウィンドウ内の項目の有効なドロップ先であるコンテナーがデザイナーに含まれていることを確認します。

     有効なドロップターゲットの詳細については、「 [Visual Studio でのデータへの WPF コントロールのバインド](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)」を参照してください。

3. **[データ]** メニューの **[データ ソースの表示]** をクリックして **[データ ソース]** ウィンドウを開きます。

4. 親テーブルまたはオブジェクト、および関連する子テーブルまたはオブジェクトが表示されるまで、 **[データソース]** ウィンドウのノードを展開します。

    > [!NOTE]
    > 関連する子テーブルまたはオブジェクトは、親テーブルまたはオブジェクトの下に展開可能な子ノードとして表示されるノードです。

5. 子ノードのドロップダウンメニューをクリックし、 **[詳細]** をクリックします。

6. 子ノードを展開します。

7. 子ノードの下で、子データと親データを関連付けるアイテムのドロップダウンメニューをクリックします。 (前の例では、これは**CustomerID**ノードです)。参照バインドをサポートするコントロールの種類を次の中から1つ選択します。

    - **ComboBox**

    - **ListBox**

    - **ListView**

        > [!NOTE]
        > リスト**ボックス**または**ListView**コントロールが一覧に表示されない場合は、これらのコントロールを一覧に追加できます。 詳細については、「[[データソース] ウィンドウからドラッグしたときに作成されるコントロールを設定する](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)」を参照してください。

    - @No__t_0 から派生した任意のカスタムコントロール。

        > [!NOTE]
        > **[データソース]** ウィンドウで項目に対して選択できるコントロールの一覧にカスタムコントロールを追加する方法については、「[[データソース] ウィンドウにカスタムコントロールを追加](../data-tools/add-custom-controls-to-the-data-sources-window.md)する」を参照してください。

8. **[データソース]** ウィンドウから、WPF デザイナーのコンテナーに子ノードをドラッグします。 (前の例では、子ノードは**Orders**ノードです)。

     Visual Studio では、ドラッグする各項目に対して新しいデータバインドコントロールを作成する XAML が生成されます。 また、XAML は、子テーブルまたはオブジェクトの新しい <xref:System.Windows.Data.CollectionViewSource> をドロップ先のリソースに追加します。 一部のデータソースでは、Visual Studio によって、テーブルまたはオブジェクトにデータを読み込むためのコードも生成されます。 詳細については、「 [Visual Studio でのデータへの WPF コントロールのバインド](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)」を参照してください。

9. **データソース** ウィンドウから、前に作成した 参照バインド コントロールに親ノードをドラッグします。 (前の例では、親ノードは**Customers**ノードです)。

     Visual Studio では、参照バインドを構成するためにコントロールのいくつかのプロパティを設定します。 次の表に、Visual Studio によって変更されるプロパティを示します。 必要に応じて、XAML または **[プロパティ]** ウィンドウでこれらのプロパティを変更できます。

    |property|設定の説明|
    |--------------| - |
    |<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>|このプロパティは、コントロールに表示されるデータを取得するために使用されるコレクションまたはバインディングを指定します。 このプロパティは、コントロールにドラッグした親データの <xref:System.Windows.Data.CollectionViewSource> に設定されます。|
    |<xref:System.Windows.Controls.ItemsControl.DisplayMemberPath%2A>|このプロパティは、コントロールに表示されるデータ項目のパスを指定します。 Visual Studio は、このプロパティを、主キーの後に文字列データ型の親データの最初の列またはプロパティに設定します。<br /><br /> 親データに別の列またはプロパティを表示する場合は、このプロパティを別のプロパティのパスに変更します。|
    |<xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>|このプロパティは、Visual Studio によって、デザイナーにドラッグした子データの列またはプロパティにバインドされます。 これは、親データへの外部キーです。|
    |<xref:System.Windows.Controls.Primitives.Selector.SelectedValuePath%2A>|Visual Studio は、このプロパティを、親データへの外部キーである子データの列またはプロパティのパスに設定します。|

## <a name="see-also"></a>関連項目

- [Visual Studio でデータに WPF コントロールをバインドする](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)
- [WPF アプリケーションで関連データを表示する](../data-tools/display-related-data-in-wpf-applications.md)
- [チュートリアル: WPF アプリケーションでの関連データの表示](../data-tools/display-related-data-in-wpf-applications.md)