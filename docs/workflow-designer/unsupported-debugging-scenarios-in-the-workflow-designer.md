---
title: ワークフロー デザイナーでサポートされていないデバッグ シナリオ
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 6adbe379-41d0-4681-9cd0-b91f187c3c2c
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
author: jillre
ms.openlocfilehash: bfc4e0995a9abb88f73ff27186ed4e0d1dc81648
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72649781"
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>ワークフロー デザイナーでサポートされていないデバッグ シナリオ

ワークフローデザイナーでは、次のデバッグシナリオはサポートされていません。

- コードを編集した後では実行を続行できません。

- ワークフローの任意の場所から実行を続行することはできません (次の設定)。

- カーソルが到達するまで実行を続行できません (カーソル行の前まで実行)。

- デザイナーを使用せずにコード内に作成されたワークフローをデバッグするためにワークフロー デザイナーを使用することはできません。

- 以前のバージョンの Windows Workflow Foundation (WF) で作成されたワークフローは、.NET Framework 4 以降ではデバッグできません。

- アクティビティまたは <xref:System.Activities.Statements.Flowchart> ノード間のリンクにブレークポイントを定義することはできません。

- クリップボードは、デバッグ時には使用できません。

- アクティビティをコピーまたは貼り付けた場合にはブレークポイントは保持されません。

- ワークフローのブレークポイントを呼び出し履歴ウィンドウに設定することはできません。

- デザイナーでブレークポイントを作成するときに、[**ブレークポイントの新規**作成] ダイアログボックスの**行**と**文字**の設定は使用されません。

- [ブレークポイント] ウィンドウまたはショートカット メニューは、ワークフローのデバッグで、次の列またはオプションをサポートしていません。

  - 条件

  - ヒット カウント

  - ヒット時

  - 機能

  - データ

  - プロセス

  - 逆アセンブルを表示
