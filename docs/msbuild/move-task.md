---
title: Move タスク | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Move task
- Move task [MSBuild]
ms.assetid: d1405347-1309-4f18-b565-905408093d59
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dc2e11a1466f359cebb60505f498c0df3ae6c45b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62817523"
---
# <a name="move-task"></a>Move タスク
ファイルを新しい場所に移動します。

## <a name="parameters"></a>パラメーター
 `Move` タスクのパラメーターの説明を次の表に示します。

|パラメーター|説明|
|---------------|-----------------|
|`DestinationFiles`|省略可能な <xref:Microsoft.Build.Framework.ITaskItem>`[]` 型の出力パラメーターです。<br /><br /> ソース ファイルの移動先ファイルの一覧を指定します。 この一覧は、`SourceFiles` パラメーターに指定された一覧の内容と 1 対 1 で対応している必要があります。 つまり、`SourceFiles` に指定された最初のファイルは、`DestinationFiles` に指定された最初の場所に移動され、2 番目以降のファイルも同様に処理されます。|
|`DestinationFolder`|省略可能な <xref:Microsoft.Build.Framework.ITaskItem> 型のパラメーターです。<br /><br /> ファイルの移動先ディレクトリを指定します。|
|`MovedFiles`|省略可能な <xref:Microsoft.Build.Framework.ITaskItem>`[]` 型の出力パラメーターです。<br /><br /> 正常に移動されたアイテムが格納されます。|
|`OverwriteReadOnlyFiles`|省略可能な `Boolean` 型のパラメーターです。<br /><br /> `true` の場合、ファイルが読み取り専用としてマークされている場合でも、ファイルを上書きします。|
|`SourceFiles`|必須の <xref:Microsoft.Build.Framework.ITaskItem>`[]` 型のパラメーターです。<br /><br /> 移動するファイルを指定します。|

## <a name="remarks"></a>解説
 `DestinationFolder` パラメーターか `DestinationFiles` パラメーターのいずれかを指定する必要がありますが、両方は指定できません。 両方を指定した場合、タスクは失敗し、エラーがログに記録されます。

 `Move` タスクでは、対象ファイルに必要なフォルダーを作成します。

 表に示されているパラメーターを使用できるだけでなく、このタスクは <xref:Microsoft.Build.Tasks.TaskExtension> クラスからパラメーターを継承します。このクラス自体は <xref:Microsoft.Build.Utilities.Task> クラスから継承されます。 これらの追加のパラメーターの一覧とその説明については、「[TaskExtension Base Class](../msbuild/taskextension-base-class.md)」を参照してください。

## <a name="see-also"></a>関連項目
- [タスク](../msbuild/msbuild-tasks.md)
- [タスク リファレンス](../msbuild/msbuild-task-reference.md)
