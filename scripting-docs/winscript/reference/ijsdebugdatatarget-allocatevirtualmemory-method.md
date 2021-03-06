---
title: 'IJsDebugDataTarget:: AllocateVirtualMemory メソッド |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugDataTarget.AllocateVirtualMemory
apilocation:
- jscript9diag.dll
ms.assetid: 1d3a77b0-c1de-4a0c-a759-3e0c68fd96dd
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 30ad8a3eb277823271fbfb4c2e10364b8602775c
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577636"
---
# <a name="ijsdebugdatatargetallocatevirtualmemory-method"></a>IJsDebugDataTarget::AllocateVirtualMemory メソッド
ターゲット プロセスの仮想アドレス空間内のメモリ領域を予約/コミットします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT AllocateVirtualMemory(  
   UINT64 address,  
   DWORD size,  
   DWORD allocationType,  
   DWORD pageProtection,  
   UINT64 *pAllocatedAddress  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `address`  
 [入力] メモリをコミット/予約する必要があるターゲット プロセス内のアドレス。 この値は通常ゼロであり、その場合はシステムによってアドレスが選択されます。  
  
 `size`  
 [入力] 割り当てるメモリ領域のサイズ (バイト単位)。 システムによって次のページ境界に自動的に切り上げられます。  
  
 `allocationType`  
 [入力] 実行する割り当ての種類を指定します。 これは通常、 &#124; 1 つのステップで割り当てを予約してコミットする MEM_COMMIT MEM_RESERVE (0x3000) です。  
  
 `pageProtection`  
 [入力] 割り当てるページ領域のメモリ保護。 ページをコミットする場合は、メモリ保護定数 (PAGE_READWRITE、PAGE_EXECUTE など) のいずれかを指定できます。  
  
 `pAllocatedAddress`  
 [出力] 割り当てられたページ領域のベース アドレス。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="remarks"></a>Remarks  
 この関数は、MEM_RESET が使用されない限り、割り当てるメモリをゼロに初期化します。 詳細については、「VirtualAlloc Win32 API」を参照してください。  
  
## <a name="requirements"></a>［要件］  
 **ヘッダー:** jscript9diag.h  
  
## <a name="see-also"></a>関連項目  
 [IJsDebugDataTarget インターフェイス](../../winscript/reference/ijsdebugdatatarget-interface.md)