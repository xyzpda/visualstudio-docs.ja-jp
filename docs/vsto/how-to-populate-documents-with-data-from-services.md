---
title: '方法: サービスのデータをドキュメントに読み込む'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], populating with data
- Web services [Office development in Visual Studio], populating documents
- data [Office development in Visual Studio], adding to documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 4f53000f7d6aa8bdd8261bbe5658607918b6b449
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72985870"
---
# <a name="how-to-populate-documents-with-data-from-services"></a>方法: サービスのデータをドキュメントに読み込む

Microsoft Office のドキュメント レベルのプロジェクトでは、Windows フォーム プロジェクトと同じ方法でデータにアクセスできます。 同じツールとコードを使用してソリューションにデータを取り込むことができ、Windows フォーム コントロールを使用してデータを表示できます。 さらに、ホスト コントロールと呼ばれるコントロールを利用できます。これは、Microsoft Office Excel および Microsoft Office Word のネイティブ オブジェクトであり、イベントやデータ バインディング機能が強化されています。 詳細については、「[ホスト項目とホストコントロールの概要](../vsto/host-items-and-host-controls-overview.md)」を参照してください。

[!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

次の例は、デザイン時にドキュメントにデータ バインド コントロールを追加する方法を示しています。 実行時に VSTO アドインのデータバインドコントロールを追加する方法の例については、「[チュートリアル: Vsto アドインプロジェクトのサービスからのデータへのバインド](../vsto/walkthrough-binding-to-data-from-a-service-in-a-vsto-add-in-project.md)」を参照してください。

## <a name="to-populate-a-document-level-project-with-data-from-a-web-service"></a>ドキュメントレベルのプロジェクトに web サービスのデータを設定するには

1. **[データ ソース]** ウィンドウを開き、プロジェクトのサービス データ ソースを作成します。 詳細については、「[新しいデータ ソースの追加](../data-tools/add-new-data-sources.md)」を参照してください。

2. 目的のテーブルまたはフィールドを **[データ ソース]** ウィンドウからドキュメントまでドラッグします。

     コントロールがドキュメント内に作成され、 <xref:System.Windows.Forms.BindingSource> が作成されてプロジェクト内のオブジェクトのクラスにバインドされ、サービスのクラスが生成されます。

3. コードで、手順 1. で接続した web サービスクラスのインスタンスを作成します。

4. Web サービスとの通信に必要なプロパティがある場合は、それらのプロパティのインスタンスを作成します。

5. Web サービスが公開しているメソッドと、手順 4 で作成したプロパティ インスタンスを使用し、データ要求を作成して送信します。

     使用する方法は、web サービスが提供する内容によって異なります。

6. Web サービスからのデータ応答を、<xref:System.Windows.Forms.BindingSource>の <xref:System.Windows.Forms.BindingSource.DataSource%2A> プロパティに割り当てます。

プロジェクトを実行すると、データ ソースの先頭のレコードがコントロールに表示されます。 レコードのスクロールを有効にするには、 <xref:System.Windows.Forms.BindingSource>のオブジェクトを使用して通貨のイベントを処理します。

## <a name="see-also"></a>関連項目

- [Office ソリューションのコントロールにデータをバインドする](../vsto/binding-data-to-controls-in-office-solutions.md)
- [新しいデータ ソースの追加](../data-tools/add-new-data-sources.md)
- [Visual Studio でのデータへの Windows フォーム コントロールのバインド](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [方法: データベースのデータをワークシートに読み込む](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)
- [方法: オブジェクトのデータをドキュメントに読み込む](../vsto/how-to-populate-documents-with-data-from-objects.md)
- [方法: データベースのデータをドキュメントに読み込む](../vsto/how-to-populate-documents-with-data-from-a-database.md)
- [方法: ホストコントロールのデータを使用してデータソースを更新する](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)