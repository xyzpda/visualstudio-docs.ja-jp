---
title: ToolTaskExtension 基本クラス | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- MSBuild.ToolTask.ToolCommandFailed
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 258ae433-f68a-49f1-b276-da20e3472e68
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd535e28c7d229aa0a0468b60ee7e68181350dba
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47544844"
---
# <a name="tooltaskextension-base-class"></a>ToolTaskExtension 基本クラス
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[ToolTaskExtension 基本クラス](https://docs.microsoft.com/visualstudio/msbuild/tooltaskextension-base-class)します。  
  
  
多くのタスクが <xref:Microsoft.Build.Tasks.ToolTaskExtension> クラスを継承します。このクラスは <xref:Microsoft.Build.Utilities.ToolTask> クラスから継承され、さらに、このクラス自体は <xref:Microsoft.Build.Utilities.Task> から継承されます。 この継承チェーンにより、これらのクラスから派生したタスクにいくつかのパラメーターが追加されます。 このドキュメントでは、これらのパラメーターを示します。  
  
## <a name="parameters"></a>パラメーター  
 基本クラスのパラメーターの説明を次の表に示します。  
  
|パラメーター|説明|  
|---------------|-----------------|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|省略可能な <xref:Microsoft.Build.Framework.IBuildEngine> 型のパラメーターです。<br /><br /> タスクで使用できるビルド エンジン インターフェイスを指定します。 ビルド エンジンは、自動的にこのパラメーターを設定して、タスクによるコールバックを可能にします。|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|省略可能な <xref:Microsoft.Build.Framework.IBuildEngine2> 型のパラメーターです。<br /><br /> タスクで使用できるビルド エンジン インターフェイスを指定します。 ビルド エンジンは、自動的にこのパラメーターを設定して、タスクによるコールバックを可能にします。<br /><br /> この便利なプロパティにより、このクラスから継承するタスクの作成者は、`IBuildEngine2` から `IBuildEngine` に値をキャストする必要がなくなります。|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|省略可能な <xref:Microsoft.Build.Framework.IBuildEngine3> 型のパラメーターです。<br /><br /> ホストによって提供されるビルド エンジン インターフェイスを指定します。|  
|<xref:Microsoft.Build.Utilities.ToolTask.EchoOff%2A>|省略可能な `bool` 型のパラメーターです。<br /><br /> `true` に設定すると、このタスクは **/Q** を cmd.exe コマンド ラインに渡して、コマンド ラインが stdout にコピーされないようにします。|  
|<xref:Microsoft.Build.Utilities.ToolTask.EnvironmentVariables%2A>|省略可能な `String` 型の配列パラメーターです。<br /><br /> 等号で区切られた環境変数のペアの配列です。 これらの変数は、標準の環境ブロックに加え (または標準の環境ブロックを選択的にオーバーライドして)、子の実行可能ファイルに渡されます。|  
|<xref:Microsoft.Build.Utilities.ToolTask.ExitCode%2A>|省略可能な `Int32` 型の読み取り専用出力パラメーターです。<br /><br /> 実行したコマンドの終了コードを示します。 タスクがエラーを記録した一方で、プロセスの終了コードが 0 (成功) だった場合、これは -1 に設定されます。|  
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|省略可能な <xref:Microsoft.Build.Framework.ITaskHost> 型のパラメーターです。<br /><br /> ホスト オブジェクト インスタンスを指定します (null も指定できます)。 ビルド エンジンは、ホスト IDE によってホスト オブジェクトがこの特定のタスクに関連付けられている場合にこのプロパティを設定します。|  
|<xref:Microsoft.Build.Tasks.ToolTaskExtension.Log%2A>|省略可能な <xref:Microsoft.Build.Utilities.TaskLoggingHelper> 型の読み取り専用パラメーターです。<br /><br /> タスク ログ メソッドを格納している <xref:Microsoft.Build.Tasks.TaskLoggingHelperExtension> クラスのインスタンスを取得します。|  
|<xref:Microsoft.Build.Utilities.ToolTask.LogStandardErrorAsError%2A>|省略可能な `bool` 型のパラメーターです。<br /><br /> `true` の場合、標準エラー ストリームで受け取ったすべてのメッセージがエラーとして記録されます。|  
|<xref:Microsoft.Build.Utilities.ToolTask.StandardErrorImportance%2A>|省略可能な `String` 型のパラメーターです。<br /><br /> 標準出力ストリームのテキストを記録するときに使用する重要度です。|  
|<xref:Microsoft.Build.Utilities.ToolTask.StandardOutputImportance%2A>|省略可能な `String` 型のパラメーターです。<br /><br /> 標準出力ストリームのテキストを記録するときに使用する重要度です。|  
|<xref:Microsoft.Build.Utilities.ToolTask.Timeout%2A>|仮想の省略可能な `Int32` 型のパラメーターです。<br /><br /> タスク実行を終了するまでの時間をミリ秒単位で指定します。 既定値は `Int.MaxValue` であり、タイムアウト期限がないことを示します。タイムアウトはミリ秒単位です。|  
|<xref:Microsoft.Build.Utilities.ToolTask.ToolExe%2A>|仮想の省略可能な `string` 型のパラメーターです。<br /><br /> プロジェクトで実装すると、ToolName をオーバーライドできます。 タスクでオーバーライドすると、ToolName を保持できます。|  
|<xref:Microsoft.Build.Utilities.ToolTask.ToolPath%2A>|省略可能な `string` 型のパラメーターです。<br /><br /> タスクで基になる実行可能ファイルを読み込む場所を指定します。 このパラメーターを指定しないと、[!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] を実行しているフレームワークのバージョンに対応する SDK インストール パスが使用されます。|  
|<xref:Microsoft.Build.Utilities.ToolTask.UseCommandProcessor%2A>|省略可能な `bool` 型のパラメーターです。<br /><br /> `true` に設定した場合、このタスクで直接コマンドを実行する代わりに、コマンド ラインのバッチ ファイルを作成し、そのファイルをコマンド プロセッサで実行します。|  
|<xref:Microsoft.Build.Utilities.ToolTask.YieldDuringToolExecution%2A>|省略可能な `bool` 型のパラメーターです。<br /><br /> `true` に設定した場合、このタスクは、その実行時にノードを生成します。|  
  
## <a name="see-also"></a>関連項目  
 [Task Reference (タスク リファレンス)](../msbuild/msbuild-task-reference.md)   
 [タスク](../msbuild/msbuild-tasks.md)


