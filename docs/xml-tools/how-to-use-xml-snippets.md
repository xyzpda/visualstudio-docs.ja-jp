---
title: XML スニペットの使用方法
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 3a27375b-81cc-48f6-a884-e1cb8c4f78f5
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 163fcddb8553da39b035e649155e04c3da4b430e
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72601797"
---
# <a name="how-to-use-xml-snippets"></a>方法: XML スニペットを使用する

Xml エディターのショートカットメニューで次の2つのコマンドを使用すると、XML スニペットを呼び出すことができます。 **[スニペットの挿入]** コマンドを実行すると、XML スニペットがカーソル位置に挿入されます。 [**ブロック**の挿入] コマンドは、選択したテキストの周囲に XML スニペットをラップします。 各 XML スニペットには、スニペット型が指定されています。 スニペットの種類は、 **[スニペットの挿入]** コマンド、 **[ブロック]** の挿入 コマンド、またはその両方でスニペットを使用できるかどうかを決定します。

XML スニペットがエディターに追加されると、スニペット内の編集可能なフィールドがすべて黄色で強調表示され、カーソルが最初の編集可能なフィールドに置かれます。

## <a name="insert-snippet"></a>スニペットの挿入

次の手順では、 **[スニペットの挿入]** コマンドにアクセスする方法について説明します。

> [!NOTE]
> **[スニペットの挿入]** コマンドは、ショートカットキー (**ctrl** +**K**、 **ctrl** +**X**) でも使用できます。

### <a name="to-insert-snippets-from-the-shortcut-menu"></a>ショートカット メニューからスニペットを挿入するには

1. XML スニペットを挿入する位置にカーソルを置きます。

2. 右クリックして **[スニペットの挿入]** を選択します。

   使用可能な XML スニペットの一覧が表示されます。

3. マウスを使用するか、スニペットの名前を入力し、 **tab**キーまたは**enter**キーを押して、スニペットを一覧から選択します。

### <a name="to-insert-snippets-using-the-intellisense-menu"></a>IntelliSense メニューを使用してスニペットを挿入するには

1. XML スニペットを挿入する位置にカーソルを置きます。

2. **[編集]** メニューの **[IntelliSense]** をポイントし、 **[スニペットの挿入]** を選択します。

   使用可能な XML スニペットの一覧が表示されます。

3. マウスを使用するか、スニペットの名前を入力し、 **tab**キーまたは**enter**キーを押して、スニペットを一覧から選択します。

### <a name="to-insert-snippets-through-the-intellisense-complete-word-list"></a>IntelliSense の入力候補一覧を使用してスニペットを挿入するには

1. XML スニペットを挿入する位置にカーソルを置きます。

2. ファイルに追加する XML スニペットの名前の入力を開始します。 オートコンプリートがオンになっている場合は、IntelliSense の入力候補の一覧が表示されます。 表示されない場合は、 **Ctrl** +**Space**キーを押してアクティブ化します。

3. 入力候補の一覧から XML スニペットを選択します。

4. Tab**キーを**押して XML**スニペットを呼び出し**ます。

> [!NOTE]
> XML スニペットが呼び出されない場合があります。 たとえば、`xs:complexType` ノード内に `xs:element` 要素を挿入しようとした場合、エディターは XML スニペットを生成しません。 `xs:complexType` ノード内で `xs:element` 要素が使用された場合、必須の属性やサブ要素がないため、エディターに挿入するデータが存在しないことになります。

### <a name="to-insert-snippets-using-the-shortcut-name"></a>ショートカット名を使用してスニペットを挿入するには

1. XML スニペットを挿入する位置にカーソルを置きます。

2. エディターのペインに「`<`」と入力します。

3. **Esc**キーを押して、IntelliSense の入力候補一覧を閉じます。

4. スニペットのショートカット名を入力し、 **tab**キーを押して XML スニペットを呼び出します。

## <a name="surround-with"></a>ブロックの挿入

次の手順では、[**ブロック**の挿入] コマンドにアクセスする方法について説明します。

> [!NOTE]
> [**ブロック**の挿入] コマンドは、ショートカットキー (**ctrl** +**K**、 **ctrl** +**S**) でも使用できます。

### <a name="to-use-surround-with-from-the-context-menu"></a>コンテキストメニューから [ブロックの挿入] を使用するには

1. XML エディターで、囲むテキストを選択します。

2. 右クリックして、[**ブロックの**挿入] を選択します。

   [ブロックの挿入] で使用可能な XML スニペットの一覧が表示されます。

3. マウスを使用するか、スニペットの名前を入力し、 **tab**キーまたは**enter**キーを押して、スニペットを一覧から選択します。

### <a name="to-use-surround-with-from-the-intellisense-menu"></a>IntelliSense メニューから [ブロックの挿入] を使用するには

1. XML エディターで、囲むテキストを選択します。

2. **[編集]** メニューの **[IntelliSense]** をポイントし、 **[ブロック]** の挿入 をクリックします。

   [ブロックの挿入] で使用可能な XML スニペットの一覧が表示されます。

3. マウスを使用するか、スニペットの名前を入力し、 **tab**キーまたは**enter**キーを押して、スニペットを一覧から選択します。

## <a name="use-xml-snippets"></a>XML スニペットを使用する

XML スニペットを選択すると、カーソルの位置にコード スニペットのテキストが自動的に挿入されます。 スニペット内の編集可能なフィールドがすべて強調表示され、最初の編集可能なフィールドが自動的に選択されます。 現在選択されているフィールドは枠で囲まれます。

フィールドが選択されているときには、フィールドの新しい値を入力できます。 **Tab**キーを押すと、スニペットの編集可能なフィールドが切り替わります。**Shift** +**tab**キーを押すと、逆の順序で順番に切り替わります。 フィールドをクリックすると、フィールド内にカーソルが置かれ、フィールドをダブルクリックするとフィールドが選択されます。 フィールドが強調表示されているときには、そのフィールドについて説明するツール ヒントが表示されることがあります。

編集することができるのは、特定のフィールドの最初のインスタンスだけです。 そのフィールドが強調されているときには、そのフィールドにある他のインスタンスは中抜き表示されます。 編集可能なフィールドの値を変更すると、スニペット内でフィールドが使用されているすべての場所で、そのフィールドが変更されます。

**Enter**キーまたは**Esc**キーを押すと、フィールドの編集がキャンセルされ、エディターが通常のモードに戻ります。

編集可能なコードスニペットフィールドの既定の色を変更するには、 **[オプション]** ダイアログボックスの **[フォントおよび色]** ペインで [**コードスニペットフィールド]** 設定を変更します。 詳細については、「[方法: エディターでフォントおよび色を変更する](../ide/reference/how-to-change-fonts-and-colors-in-the-editor.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [XML スニペット](../xml-tools/xml-snippets.md)
- [方法: xml スキーマから XML スニペットを生成する](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)
- [方法: XML スニペットを作成する](../xml-tools/how-to-create-xml-snippets.md)