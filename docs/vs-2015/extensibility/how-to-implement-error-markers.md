---
title: '方法: エラーのマーカーの実装 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - error markers
ms.assetid: e8e78514-5720-4fc2-aa43-00b6af482e38
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2af9e0765fb5bc73a35bebfc2f50f5d2a41122d3
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63435964"
---
# <a name="how-to-implement-error-markers"></a>方法: エラーのマーカーを実装します。
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

エラーのマーカー (または赤色の波下線) は、テキスト エディターのカスタマイズを実装するが最も難しいです。 ただし、VSPackage のユーザーに提供する利点は、提供するコストを上回るまでことができます。 エラーのマーカーは、微妙、言語のパーサーが波線または波状の赤い線で正しくないと判断されるテキストをマークします。 このインジケーターには、不適切なコードを視覚的に表示することでプログラマが役立ちます。  
  
 テキスト マーカーを使用すると、赤い波線を実装します。 原則として、言語サービスに赤い波線がバッファーに追加テキスト、バック グラウンド パスとして、アイドル時、またはバック グラウンド スレッドでします。  
  
### <a name="to-implement-the-red-wavy-underline-feature"></a>赤い波線の機能を実装するには  
  
1. 赤い波線を配置するテキストを選択します。  
  
2. 型のマーカーを作成`MARKER_CODESENSE_ERROR`です。 詳細については、「[方法 :標準のテキスト マーカーを追加](../extensibility/how-to-add-standard-text-markers.md)します。  
  
3. その後、渡す、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient>インターフェイス ポインター。  
  
   このプロセスでは、特定のマーカーにツールヒントのテキストまたは特別なコンテキスト メニューを作成することもできます。 詳細については、「[方法 :標準のテキスト マーカーを追加](../extensibility/how-to-add-standard-text-markers.md)します。  
  
   エラーのマーカーを表示する前に、次のオブジェクトが必要です。  
  
- パーサーです。  
  
- タスク プロバイダー (の実装は、 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider2>) 再解析する行を識別するために行情報の変更の記録を保持します。  
  
- カレットをキャプチャするテキスト ビューのフィルターを使用して、ビューからイベントを変更する、 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEvents.OnChangeCaretLine%2A>) メソッドです。  
  
  パーサー、タスク プロバイダー、およびフィルターは、エラー マーカーを可能にするために必要なインフラストラクチャを提供します。 次の手順では、エラー マーカーを表示するため、プロセスを提供します。  
  
1. フィルター選択されるビューでは、フィルターは、そのビューのデータに関連付けられているタスク プロバイダーへのポインターを取得します。  
  
    > [!NOTE]
    > メソッドのヒント、ステートメント入力候補、エラーのマーカーを同じコマンド フィルターを使用することができます。  
  
2. フィルターは、別の行に移動したことを示すイベントを受信、エラーをチェックするタスクが作成されます。  
  
3. タスク ハンドラーでは、行のダーティを確認します。 そうである場合は、エラーの行を解析します。  
  
4. エラーが見つかった場合、タスク プロバイダーは、作業項目のインスタンスを作成します。 このインスタンスは、テキスト ビューでエラーのマーカーとして、環境を使用してテキスト マーカーを作成します。  
  
## <a name="see-also"></a>関連項目  
 [レガシ API を使用したテキスト マーカーの使用](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [方法: 標準のテキスト マーカーを追加します。](../extensibility/how-to-add-standard-text-markers.md)   
 [方法: カスタム テキスト マーカーを作成します。](../extensibility/how-to-create-custom-text-markers.md)   
 [方法: テキスト マーカーを使用する](../extensibility/how-to-use-text-markers.md)
