---
title: 複数 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- EVENTATTRIBUTES
helpviewer_keywords:
- EVENTATTRIBUTES enumeration
ms.assetid: 04db10f7-df31-4464-98e8-b3777428179e
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 3026845be9aa6623d6c5cd42406385e8c5c2a11e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68149375"
---
# <a name="eventattributes"></a>EVENTATTRIBUTES
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

イベントの属性を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
typedef DWORD EVENTATTRIBUTES;  
```  
  
```csharp  
public enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
```  
  
## <a name="members"></a>メンバー  
 EVENT_ASYNCHRONOUS  
 イベントは非同期イベントに応答が必要ないことを示します。  
  
 EVENT_SYNCHRONOUS  
 イベントが同期的です。返信して[ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)します。  
  
 EVENT_STOPPING  
 停止イベントであることを示します。 いずれかと組み合わせることは`EVENT_ASYNCHRONOUS`または`EVENT_SYNCHRONOUS`します。  
  
 EVENT_ASYNC_STOP  
 非同期の停止イベントを示します。 現在、このようなイベントはありません。 このフラグは、単なるプレース ホルダーです。  
  
 EVENT_SYNC_STOP  
 同期の停止イベントを示します (の組み合わせ`EVENT_SYNCHRONOUS`と`EVENT_STOPPING`)。 この値は、停止イベントを送信するときにデバッグ エンジン (DE) によって使用されます。 呼び出しを使用して、返信があった[Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md)、[手順](../../../extensibility/debugger/reference/idebugprogram2-step.md)、または[続行](../../../extensibility/debugger/reference/idebugprogram2-continue.md)します。  
  
 EVENT_IMMEDIATE  
 IDE に即座に同期的に送信されるイベントを示します。 このフラグはその他のフラグのような`EVENT_ASYNCHRONOUS`、 `EVENT_SYNCHRONOUS`、または`EVENT_SYNC_STOP`イベントと応答のメカニズム (あれば) が既知であるファクトの種類を示します。  
  
 EVENT_EXPRESSION_EVALUATION  
 イベントは、式の評価の結果です。  
  
## <a name="remarks"></a>Remarks  
 これらの値が渡された、`dwAttrib`のパラメーター、[イベント](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)メソッド。  
  
 これらの値は、演算と組み合わせることがあります`OR`します。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
