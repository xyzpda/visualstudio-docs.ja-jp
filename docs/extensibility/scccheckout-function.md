---
title: SccCheckout 関数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccCheckout
helpviewer_keywords:
- SccCheckout function
ms.assetid: 06e9ecd7-fc09-40c1-9dd1-2b56c622c80b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e5160a2600a8eb3250702dd0836d812b668a3d1b
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66333873"
---
# <a name="scccheckout-function"></a>SccCheckout 関数
完全修飾ファイル名の一覧を指定するには、この関数はそれらローカル ドライブに。 コメントは、チェック アウトされているすべてのファイルに適用されます。コメントの引数を指定できます、`null`文字列。

## <a name="syntax"></a>構文

```cpp
SCCRTN SccCheckout (
   LPVOID    pvContext,
   HWND      hWnd,
   LONG      nFiles,
   LPCSTR*   lpFileNames,
   LPCSTR    lpComment,
   LONG      fOptions,
   LPCMDOPTS pvOptions
);
```

### <a name="parameters"></a>パラメーター
 pvContext

[in]ソース管理プラグイン コンテキスト構造体。

 hWnd

[in]ソース管理プラグインが提供される任意のダイアログ ボックスの親として使用できる IDE ウィンドウへのハンドル。

 nFiles

[in]選択したファイルをチェック アウトの数。

 lpFileNames

[in]チェック アウトするファイルの完全修飾パス名の配列。

 lpComment

[in]これらのチェック アウトされている選択したファイルに適用されるコメントです。

 方法は限られて

[in]コマンドのフラグ (を参照してください[特定のコマンドで使用されるビットフラグ](../extensibility/bitflags-used-by-specific-commands.md))。

 pvOptions

[in]ソース管理プラグインに固有のオプション。

## <a name="return-value"></a>戻り値
 この関数のソース管理プラグイン実装は、次の値のいずれかを返すが必要です。

|[値]|説明|
|-----------|-----------------|
|SCC_OK|チェック アウトは成功しました。|
|SCC_E_FILENOTCONTROLLED|選択したファイルはソース コード管理下ではありません。|
|SCC_E_ACCESSFAILURE|ソース管理システムのネットワークまたは競合の問題の可能性へのアクセスに問題が発生しました。 再試行をお勧めします。|
|SCC_E_NOTAUTHORIZED|この操作を実行できません。|
|SCC_E_NONSPECIFICERROR|不特定のエラーです。 ファイル チェック アウトされませんでした。|
|SCC_E_ALREADYCHECKEDOUT|ユーザーが既にファイルをチェック アウトします。|
|SCC_E_FILEISLOCKED|新しいバージョンの作成を禁止するファイルがロックされています。|
|SCC_E_FILEOUTEXCLUSIVE|別のユーザーには、このファイルの排他チェック アウトが行われます。|
|SCC_I_OPERATIONCANCELED|操作が完了する前に取り消されました。|

## <a name="see-also"></a>関連項目
- [ソース管理プラグイン API 関数](../extensibility/source-control-plug-in-api-functions.md)
- [特定のコマンドで使用されるビットフラグ](../extensibility/bitflags-used-by-specific-commands.md)