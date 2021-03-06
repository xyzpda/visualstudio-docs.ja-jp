---
title: トレースポイントを使用して情報を記録する |Microsoft Docs
ms.date: 10/28/2019
ms.topic: conceptual
helpviewer_keywords:
- tracepoints, about tracepoints
author: Sagar-S-S
ms.author: sashe
manager: AndSter
ms.workload:
- multiple
ms.openlocfilehash: fcc9f01315d3783af1a1f124785cd74fafb215bf
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73187302"
---
# <a name="log-info-to-the-output-window-using-tracepoints-in-visual-studio"></a>Visual Studio でトレースポイントを使用して出力ウィンドウに情報を記録する

トレースポイントを使用すると、コードの変更や停止を行わずに、構成可能な条件の下で出力ウィンドウに情報を記録できます。 この機能は、マネージ言語 (C#、Visual Basic F#) とネイティブコードの両方でサポートされています。また、JavaScript や Python などの言語でもサポートされています。

## <a name="let39s-take-an-example"></a>例&#39;を見てみましょう

次のサンプルプログラムは、ループが別の反復処理を実行するたびに1ずつ増加するカウンター変数を持つ単純な `for` ループです。

![カウンターの例](../debugger/media/counterexample.png "カウンターの例")

## <a name="set-tracepoints-in-source-code"></a>ソースコードでのトレースポイントの設定

トレースポイントを設定するには、 **[ブレークポイントの設定]** ウィンドウの **[アクション]** チェックボックスで出力文字列を指定します。

1. トレースポイントを初期化するには、まず、トレースポイントを設定する行番号の左側の余白をクリックします。

   ![ブレークポイントの初期化](../debugger/media/breakpointinitialization.png "ブレークポイントの初期化")

2. 赤い円の上にマウスポインターを移動し、歯車アイコンをクリックします。
3. **[ブレークポイントの設定]** ウィンドウが開きます。

   ![ブレークポイントウィンドウ](../debugger/media/breakpointwindow.png "ブレークポイントウィンドウ")

4. **[アクション]** チェックボックスをオンにします。

   ![[チェックされたアクション] ボックス](../debugger/media/checkedactionsbox.png "[チェックされたアクション] ボックス")

   赤い円がひし形に変わり、ブレークポイントからトレースポイントに切り替えたことを示します。

5. [**出力ウィンドウのメッセージを表示**する] ボックスに、ログインするメッセージを入力します (詳細については、この記事の後半のセクションを参照してください)。

   これで、トレースポイントが設定されました。 すべての情報を出力ウィンドウに記録するだけの場合は、&quot;Close &quot; ボタンをクリックします。

6. メッセージを表示するかどうかを決定する条件を追加する場合は、 **[条件]** チェックボックスをオンにします。

   ![チェックされた条件ボックス](../debugger/media/checkedconditionsbox.png "チェックされた条件ボックス")

   条件には、**条件式**、**フィルター**、**ヒットカウント**という3つの選択肢があります。

## <a name="actions-menu"></a>[アクション] メニュー

このメニューを使用すると、[出力] ウィンドウにメッセージを記録できます。 メッセージボックスに出力する文字列を入力します (引用符は必要ありません)。 変数の値を表示する場合は、中かっこで囲まれていることを確認してください。

たとえば、出力コンソールで `counter` 変数の値を表示する場合は、メッセージテキストボックスに「{counter}」と入力します。

![カウンターの出力メッセージ](../debugger/media/counteroutputmessage.png "カウンターの出力メッセージ")

**[閉じる]** をクリックし、プログラムをデバッグする (**F5 キーを押す**) と、出力ウィンドウに次の出力が表示されます。

![出力ウィンドウのアクションメッセージ](../debugger/media/actionsmessageinoutputwindow.png "出力ウィンドウのアクションメッセージ")

特別なキーワードを使用して、より具体的な情報を表示することもできます。 次に示すように、キーワードを正確に入力します (各キーワードの前に "$" を使用し、キーワード自体にはすべて大文字を使用します)。

| キーワード | 表示される内容 |
| --- | --- |
| $ADDRESS | 現在の命令 |
| $CALLER | 関数名の呼び出し |
| $CALLSTACK | [呼び出し履歴] |
| $FUNCTION | 現在の関数名 |
| $PID | [プロセス ID] |
| $PNAME | プロセス名 |
| $TID | スレッド ID |
| $TNAME   | スレッド名 |
| $TICK | ティック数 (Windows GetTickCount から) |

## <a name="conditions-menu"></a>[条件] メニュー

条件を使用すると、出力メッセージをフィルター処理できるため、特定のシナリオでのみ表示されます。 使用できる条件には、3つの主要な種類があります。

### <a name="conditional-expression"></a>条件式
条件式では、特定の条件が満たされた場合にのみ出力メッセージが表示されます。

条件式では、特定の条件が true の場合、または変更された場合に、メッセージを出力するようにトレースポイントを設定できます。 たとえば、`for` ループの反復処理中にカウンターの値のみを表示する場合は、 **[true]** オプションを選択し、メッセージテキストボックスに「`i%2 == 0`」と入力します。

![条件式が True です](../debugger/media/conditionalexpressionistrue.png "条件式が True です")

`for` ループの繰り返しが変化したときに counter の値を印刷する場合は、 **[変更された場合]** オプションを選択し、メッセージテキストボックスに「`i`」と入力します。

![変更時の条件式](../debugger/media/conditionalexpressionwhenchanged.png "変更時の条件式")

**[変更された場合]** オプションの動作は、プログラミング言語によって異なります。

- ネイティブコードの場合、デバッガーは条件の最初の評価を変更と見なしません。そのため、最初の評価ではトレースポイントにヒットしません。
- マネージコードの場合、デバッガーは、[変更された**場合**] が選択された後の最初の評価でトレースポイントにヒットします。

条件の設定時に使用できる有効な式の詳細については、「[デバッガーの式](expressions-in-the-debugger.md)」を参照してください。

### <a name="hit-count"></a>ヒットカウント
ヒットカウント条件を使用すると、トレースポイントが設定されているコード行が指定された回数だけ実行された後にのみ、出力を送信できます。

[ヒットカウント] では、トレースポイントが設定されているコード行が、に等しいか、の倍数であるか、または指定されたヒットカウント値以上の場合に、メッセージを出力するように選択できます。 ニーズに最も適したオプションを選択し、目的のイテレーションを表すフィールド (たとえば、5) に整数値を入力します。

![条件式のヒットカウント](../debugger/media/conditionalexpressionhitcount.png "条件式のヒットカウント")

### <a name="filter"></a>フィルター
フィルター条件として、に対して出力されるデバイス、プロセス、またはスレッドを指定します。

![条件式フィルター](../debugger/media/conditionalexpressionfilter.png "条件式フィルター")

フィルター式の一覧:

- MachineName = "name"
- ProcessId = value
- ProcessName = "name"
- ThreadId = value
- ThreadName = "name"

文字列 (名前など) を二重引用符で囲みます。 値は、引用符なしで入力できます。 句を結合するには、`&` (`AND`)、`||` (`OR`)、`!` (`NOT`)、およびかっこを使用します。

## <a name="considerations"></a>注意事項

トレースポイントは、クリーンでスムーズなエクスペリエンスを実現することを目的としていますが、使用するタイミングに注意する必要がある考慮事項がいくつかあります。

オブジェクトのプロパティまたは属性を検査するときに、その値が変化することがあります。 検査中に値が変化した場合、トレースポイント機能自体に起因するバグではありません。 ただし、トレースポイントを使用してオブジェクトを検査しても、これらの偶発的な変更は回避されません。

**アクション**メッセージボックスで式を評価する方法は、現在開発に使用している言語とは異なる場合があります。 たとえば、文字列を出力する場合、通常は `Debug.WriteLine()` または `console.log()` を使用する場合でも、メッセージを引用符で囲む必要はありません。 また、出力式の中かっこ構文 (`{ }`) も、開発言語で値を出力する場合とは異なる場合があります。 (ただし、中かっこ (`{ }`) 内の内容は、開発言語の構文を使用して記述する必要があります。

ライブアプリケーションをデバッグして同様の機能を探している場合は、スナップショットデバッガーのログポイント機能を確認してください。 スナップショットデバッガーは、実稼働アプリケーションの問題を調査するために使用されるツールです。 また、ログポイントを使用すると、ソースコードを変更せずに、実行中のアプリケーションに影響を与えない出力ウィンドウにメッセージを送信することもできます。 詳細については、「[デバッグライブ Azure アプリケーション](../debugger/debug-live-azure-applications.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [デバッグとは](../debugger/what-is-debugging.md)
- [Visual Studio C#を使用してより優れたコードを記述する](../debugger/write-better-code-with-visual-studio.md)
- [デバッグに関する最初の確認](../debugger/debugger-feature-tour.md)
- [デバッガー内の式](expressions-in-the-debugger.md)
- [ブレークポイントの使用](../debugger/using-breakpoints.md)
- [ライブ Azure アプリケーションのデバッグ](../debugger/debug-live-azure-applications.md)
