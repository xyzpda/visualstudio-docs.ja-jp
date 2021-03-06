---
title: ポート サプライヤーの実装 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], implementing port suppliers
- port suppliers, implementing
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ffa6daa20c08bd236657c88e762b2f453554cb74
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68152682"
---
# <a name="implementing-a-port-supplier"></a>ポートのサプライヤーの実装
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

ポート サプライヤーは、セッション デバッグ マネージャー (SDM) への要求でポートを提供します。 ポート サプライヤーは、DCOM ではないマシンをデバッグするときに、または新しいデバイスをサポートする必要がある場合に実装する必要があります。 たとえば、携帯電話へのデバッグを提供するに (おそらくによって IR またはセルの接続)、携帯電話に接続し、プロセスと、スマート フォンで実行されているプログラムを列挙するポートを提供するポートのサプライヤーを実装する可能性があります。  
  
 (リモート デバッグも含めて)、Windows ベースのコンピューターでプログラムのデバッグのため、このような場合、独自のポート サプライヤーを実装する必要はありません、Visual Studio はネイティブ モードと共通言語ランタイム (CLR) のプロセス、ポート サプライヤーを提供します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [ポート サプライヤーの実装および登録](../../extensibility/debugger/implementing-and-registering-a-port-supplier.md)  
 ポート サプライヤーとそのポートで、SDM をやり取りする方法について説明します。  
  
 [必須のポート サプライヤー インターフェイス](../../extensibility/debugger/required-port-supplier-interfaces.md)  
 ポート サプライヤーを取得する実装する必要があるインターフェイスについて説明します。  
  
## <a name="related-sections"></a>関連項目  
 [デバッガーの概念](../../extensibility/debugger/debugger-concepts.md)  
 デバッグ アーキテクチャの主要な概念をについて説明します。  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio デバッガーの拡張性](../../extensibility/debugger/visual-studio-debugger-extensibility.md)
