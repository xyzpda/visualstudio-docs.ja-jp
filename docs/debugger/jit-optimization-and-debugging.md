---
title: JIT の最適化とデバッグ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], optimized code
- optimized code, debugging
ms.assetid: 19bfabf3-1a2e-49dc-8819-a813982e86fd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 12752acf75da70fa30666f9b1780256c94bde859
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72731623"
---
# <a name="jit-optimization-and-debugging"></a>JIT の最適化とデバッグ
**.Net での最適化のしくみ:** コードをデバッグする場合は、そのコードが最適化されて**いない**と簡単になります。 これは、コードが最適化されている場合、コンパイラとランタイムが出力される CPU コードを変更して、より高速に実行できるようにするためですが、元のソースコードに対する直接のマッピングはあまりありません。 これは、多くの場合、デバッガーがローカル変数の値を示すことができず、コードのステップ実行やブレークポイントが期待どおりに機能しない可能性があることを意味します。

通常、リリースビルド構成によって最適化されたコードが作成され、デバッグビルド構成は作成されません。 @No__t_0 MSBuild プロパティは、コードを最適化するようにコンパイラに指示するかどうかを制御します。

.NET エコシステムでは、コードが2段階のプロセスでソースから CPU への命令に変換されC#ます。最初に、コンパイラは、入力したテキストを MSIL という中間バイナリ形式に変換し、これを .dll ファイルに書き込みます。 その後、.NET ランタイムは、この MSIL を CPU 命令に変換します。 どちらの手順でも程度を最適化できますが、.NET ランタイムによって実行される2番目のステップでは、より重要な最適化が実行されます。

[**モジュールの読み込み時に JIT 最適化を抑制する (マネージのみ)] オプション:** デバッガーは、最適化を有効にしてコンパイルされた DLL がターゲットプロセス内で読み込まれたときの動作を制御するオプションを公開します。 このオプションがオフの場合 (既定の状態)、.NET ランタイムが MSIL コードを CPU コードにコンパイルすると、最適化が有効になります。 このオプションをオンにすると、デバッガーは最適化を無効にするように要求します。

**[モジュールの読み込み時に JIT 最適化を抑制する (マネージのみ)]** オプションを見つけるには、[**ツール** > **オプション**] を選択し、 **[デバッグ]** ノードの下の **[全般]** ページを選択します。

**次のチェックボックスをオンにします。** このオプションは、nuget パッケージなどの別のソースから Dll をダウンロードし、この DLL のコードをデバッグする場合にオンにします。 これを機能させるには、この DLL のシンボル (.pdb) ファイルも検索する必要があります。

ローカルでビルドしているコードのデバッグにのみ関心がある場合は、このオプションをオフのままにすることをお勧めします。このオプションを有効にすると、デバッグが大幅に遅くなる場合があります。 この速度が低下する理由は2つあります。

* 最適化されたコードの実行速度が向上します。 多くのコードの最適化を無効にすると、パフォーマンスへの影響が大きくなる可能性があります。
* マイコードのみ有効にした場合、デバッガーは最適化された Dll のシンボルを試行したり読み込みを実行しなくなります。 シンボルの検索には長い時間がかかることがあります。

**このオプションの制限事項は次のとおりです。** このオプションが機能し**ない**場合は、次の2つの状況があります。

1. 既に実行中のプロセスにデバッガーをアタッチする場合、このオプションは、デバッガーがアタッチされた時点で既に読み込まれていたモジュールには影響しません。
2. このオプションは、ネイティブコードに対してプリコンパイル済み (. k. a...) の Dll には影響しません。 ただし、環境変数 ' COMPlus_ZapDisable ' を ' 1 ' に設定してプロセスを開始することで、プリコンパイル済みコードの使用を無効にすることができます。

## <a name="see-also"></a>関連項目
- [マネージド コードをデバッグする](../debugger/debugging-managed-code.md)
- [デバッガーでのコード間の移動](../debugger/navigating-through-code-with-the-debugger.md)
- [実行中のプロセスへのアタッチ](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)
- [マネージド実行プロセス](/dotnet/standard/managed-execution-process)
