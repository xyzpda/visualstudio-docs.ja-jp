---
title: IEnumDebugErrorBreakpoints2::Skip |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumDebugErrorBreakpoints2::Skip
helpviewer_keywords:
- IEnumDebugErrorBreakpoints2::Skip
ms.assetid: a5a02b38-4e3a-4f0e-b529-f770c3485c8b
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 320abc1773ec3befde13ebb73514adb4f8a7d178
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68178488"
---
# <a name="ienumdebugerrorbreakpoints2skip"></a>IEnumDebugErrorBreakpoints2::Skip
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

指定した要素数をスキップします。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   uint celt  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `celt`  
 [in]スキップする要素の数。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`場合`celt`が残りの要素の数より大きい。 それ以外の場合、エラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 場合`celt`数より大きい値を指定します。 残りの要素の列挙体が最後に設定し、`S_FALSE`が返されます。  
  
## <a name="see-also"></a>関連項目  
 [IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)
