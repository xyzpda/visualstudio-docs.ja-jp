---
title: 'CA1824: NeutralResourcesLanguageAttribute | を使用してアセンブリをマークします。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1824
- MarkAssembliesWithNeutralResourcesLanguage
helpviewer_keywords:
- MarkAssembliesWithNeutralResourcesLanguage
- CA1824
ms.assetid: 10e97f8a-aa6e-47aa-b253-1e5d3a295d82
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: efa328fdff9c357e0183fc2ca80e4d77d4f6782e
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661118"
---
# <a name="ca1824-mark-assemblies-with-neutralresourceslanguageattribute"></a>CA1824: アセンブリを NeutralResourcesLanguageAttribute に設定します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MarkAssembliesWithNeutralResourcesLanguage|
|CheckId|CA1824|
|カテゴリ|Microsoft. パフォーマンス|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 アセンブリには、 **ResX**ベースのリソースが含まれていますが、<xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> が適用されていません。

## <a name="rule-description"></a>規則の説明
 **NeutralResourcesLanguage**属性は、アセンブリのニュートラルカルチャのリソースを表示するために使用された言語を**ResourceManager**に通知します。 ニュートラルリソース言語と同じカルチャのリソースを検索する場合、 **ResourceManager**はメインアセンブリにあるリソースを自動的に使用します。 これは、現在のスレッドの現在のユーザーインターフェイスカルチャを持つサテライトアセンブリを検索する代わりに、これを行います。 これにより、読み込んだ最初のリソースに対する検索のパフォーマンスが向上し、ワーキング セットを縮小できます。

## <a name="fixing-violations"></a>違反の修正
 この規則違反を修正するには、属性をアセンブリに追加し、ニュートラルカルチャのリソースの言語を指定します。

## <a name="specifying-the-language"></a>言語の指定

#### <a name="to-specify-the-language-of-the-resource-of-the-neutral-culture"></a>ニュートラルカルチャのリソースの言語を指定するには

1. **ソリューションエクスプローラー**で、プロジェクトを右クリックし、 **[プロパティ]** をクリックします。

2. 左側のナビゲーションバーから **[アプリケーション]** を選択し、 **[アセンブリ情報]** をクリックします。

3. **[アセンブリ情報]** ダイアログボックスで、 **[ニュートラル言語]** ボックスの一覧から言語を選択します。

4. **[OK]** をクリックします。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 このルールからの警告を抑制することができます。 ただし、起動のパフォーマンスが低下する可能性があります。
