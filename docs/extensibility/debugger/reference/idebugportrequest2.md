---
title: IDebugPortRequest2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortRequest2
helpviewer_keywords:
- IDebugPortRequest2 interface
ms.assetid: 556e610d-7c4b-44a8-965a-76a9d02b601a
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 83f70a9fe027f004ef3829827ba8af40f7fb72e3
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66340309"
---
# <a name="idebugportrequest2"></a>IDebugPortRequest2
このインターフェイスには、ポートがについて説明します。 この説明は、ポートのサプライヤーにポートを追加に使用されます。

## <a name="syntax"></a>構文

```
IDebugPortRequest2 : IUnknown
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 Visual Studio は、通常はポート サプライヤーからデバッグ ポートを取得する処理中には、このインターフェイスを実装します。

## <a name="notes-for-callers"></a>呼び出し元のノート
 このインターフェイスに渡される[AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)デバッグ ポートを作成します。 呼び出し[GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)このインターフェイスは、最初に、ポートの作成に使用される要求を表すを返します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 次の表は、メソッドの`IDebugPortRequest2`します。

|メソッド|説明|
|------------|-----------------|
|[GetPortName](../../../extensibility/debugger/reference/idebugportrequest2-getportname.md)|作成するポートの名前を取得します。|

## <a name="remarks"></a>Remarks
 通常、デバッグ エンジンは、ポート サプライヤーと対話しないし、このインターフェイスの使用はありません。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)
- [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)
- [GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)