---
title: IDebugMethodField |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugMethodField
helpviewer_keywords:
- IDebugMethodField interface
ms.assetid: a7dc9030-fc98-4cf1-b943-37a4003300b6
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4d7f6fc12a3366200ca1e14c0e2d55f4f6d797f5
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65694345"
---
# <a name="idebugmethodfield"></a>IDebugMethodField
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このインターフェイスには、メソッドについて説明します。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugMethodField : IDebugContainerField  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 シンボル プロバイダーを実装する同一のオブジェクトにこのインターフェイスを実装する、 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)インターフェイス。 このインターフェイスは、特殊化する方法を示します。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 使用[QueryInterface](https://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3)からこのインターフェイスを取得する、 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)インターフェイスの場合は[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)返します`FIELD_TYPE_METHOD`します。 さらに、メソッド、 [GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md)、 [GetPropertySetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertysetter.md)、および[EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md)、すべての戻り、`IDebugMethodField`インターフェイス。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 メソッドだけでなく、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)と[IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)インターフェイスでは、このインターフェイスは、次のメソッドを実装します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)|メソッドのパラメーターの列挙子を作成します。|  
|[GetThis](../../../extensibility/debugger/reference/idebugmethodfield-getthis.md)|メソッドを含むオブジェクトの"this"ポインターを取得します。|  
|[EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md)|メソッドのすべてのローカル変数の列挙子を作成します。|  
|[EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)|メソッドの選択されたローカル変数の列挙子を作成します。|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugmethodfield-iscustomattributedefined.md)|特定のカスタム属性が定義されているかどうかを判断します。|  
|[EnumStaticLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumstaticlocals.md)|メソッドの静的ローカル変数の列挙子を作成します。|  
|[GetGlobalContainer](../../../extensibility/debugger/reference/idebugmethodfield-getglobalcontainer.md)|メソッドのグローバル コンテナーを取得します。|  
|[EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)|メソッドの呼び出しに必要な各引数の型の列挙子を作成します。|  
  
## <a name="remarks"></a>Remarks  
 メソッドは、ローカル変数とパラメーターに含めることができます。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: sh.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [シンボルプロバイダーのインターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
