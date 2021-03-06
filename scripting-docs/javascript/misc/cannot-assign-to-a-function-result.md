---
title: 関数の結果 | を割り当てることはできません。Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5003
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ee8ffb3a-1451-4cb3-99bf-5e9cf8b77d79
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aca09fe3b516fbb8f27def982bf34a22d33d4ada
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572367"
---
# <a name="cannot-assign-to-a-function-result"></a>関数の結果に割り当てられません。
関数の結果に値を割り当てようとしました。 関数の結果を変数に代入することはできますが、変数として使用することはできません。 関数自体に新しい値を代入する場合は、かっこ (関数呼び出し演算子) を省略します。 次の例は、このエラーが生成される状況を示しています。  
  
```js
myFunction() = 42;  // Attempting to assign the value 42 to the result of the function call.  
```  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
- 関数呼び出しの結果の値は、*割り当て*可能なものとして使用しないでください。 関数呼び出しの結果を*変数に*割り当てることができます。  
  
    ```JavaScript  
    myVar = myFunction(42);  
    ```  
  
- または、関数自体 (戻り値ではなく) を変数に代入することもできます。  
  
    ```JavaScript  
    myFunction = new Function("return 42;");  
    ```  
  
## <a name="see-also"></a>参照
 [Function オブジェクト](../../javascript/reference/function-object-javascript.md)
 [JavaScript コードの記述](../../javascript/writing-javascript-code.md)
 [関数](../../javascript/functions-javascript.md)
