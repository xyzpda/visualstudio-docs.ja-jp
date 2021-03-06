---
title: DSL ライブラリを使用して dsl 間でクラスを共有する |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 509bd96b-3e66-47f4-8642-771421d0d0d5
caps.latest.revision: 9
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 093cc277fa1cbe1915099fd9663fc1ccb797ca3a
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671180"
---
# <a name="sharing-classes-between-dsls-by-using-a-dsl-library"></a>DSL ライブラリによる DSL 間でのクラスの共有
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

@No__t_0 の視覚化とモデリング SDK では、別の DSL にインポートできる不完全な DSL 定義を作成できます。 これにより、類似するモデルの一般的な部分を考慮することができます。

## <a name="creating-and-using-dsl-libraries"></a>DSL ライブラリの作成と使用

#### <a name="to-create-a-dsl-library"></a>DSL ライブラリを作成するには

1. 新しい DSL プロジェクトを作成し、DSL ライブラリソリューションテンプレートを選択します。

     空のモデルを使用して、単一の DSL プロジェクトが作成されます。

2. ドメインクラス、リレーションシップ、図形などを追加できます。

     ライブラリ内の要素は、1つの埋め込みツリーを形成する必要がありません。

     インポーターが使用できるリレーションシップを定義するには、2つのドメインクラスを作成し、それらの間にリレーションシップを作成します。

     ドメインクラスの**継承修飾子**を `Abstract` に設定することを検討してください。

3. DSL エクスプローラーで定義した要素 (接続ビルダーなど) を追加できます。

4. 検証制約など、追加のコードを必要とするカスタマイズを追加することができます。

5. **[すべてのテンプレートの変換]** をクリックします。

6. プロジェクトをビルドします。

7. 他のユーザーが使用できるように DSL を配布する場合は、コンパイルされたアセンブリ (DLL) とファイル `DslDefinition.dsl` の両方を指定する必要があります。 コンパイルされたアセンブリは、の下のフォルダーにあり `Dsl\bin\*`

#### <a name="to-import-a-dsl-library"></a>DSL ライブラリをインポートするには

1. 別の DSL 定義の**Dsl エクスプローラー**で、dsl のルートクラスを右クリックし、 **[新しい Dsllibrary インポートの追加]** をクリックします。

2. プロパティウィンドウで、ライブラリの**ファイルパス**を設定します。 相対パスと絶対パスのどちらを使用してもかまいません。

    インポートしたライブラリは、DSL エクスプローラーの読み取り専用モードで表示されます。

3. インポートしたクラスを基底クラスとして使用できます。 インポートする DSL にドメインクラスを作成し、プロパティウィンドウで、インポートされたクラスに**基本クラス**を設定します。

4. [すべてのテンプレートの変換] をクリックします。

5. Dsl ライブラリプロジェクトによって作成されたアセンブリ (DLL) への参照を DSL プロジェクトに追加します。

6. ソリューションをビルドします。

   DSL ライブラリは、他のライブラリをインポートできます。 ライブラリをインポートすると、そのインポートも DSL エクスプローラーに自動的に表示されます。

## <a name="see-also"></a>参照
 [方法: ドメイン固有言語を定義する](../modeling/how-to-define-a-domain-specific-language.md)
