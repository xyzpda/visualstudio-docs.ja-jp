---
title: プロジェクトおよびソリューションのプロパティの管理
ms.date: 11/04/2016
ms.topic: conceptual
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 99786cc2b646c011a0398e973e0fd3d4dd97583f
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72603435"
---
# <a name="manage-project-and-solution-properties"></a>プロジェクトおよびソリューションのプロパティの管理

プロジェクトのプロパティでは、コンパイル、デバッグ、テストおよび配置の多くの側面を制御します。 プロジェクトのすべての種類に共通のプロパティや、特定の言語またはプラットフォームに固有のプロパティがあります。 プロジェクトのプロパティにアクセスするには、**ソリューション エクスプローラー**でプロジェクト ノードを右クリックして **[プロパティ]** を選択するか、メニュー バーの検索ボックスに「**プロパティ**」と入力し、結果から **[プロパティ ウィンドウ]** を選択します。

![プロジェクト コンテキスト メニュー](../ide/media/vs2015_proj_prop_menu.gif)

.NET プロジェクトでは、プロジェクト ツリー自体にプロパティ ノードが含まれる場合もあります。

![ソリューション エクスプローラー ツリーの [プロパティ] ノード](../ide/media/vs2015_props_se.png)

> [!NOTE]
> このトピックは、Windows 上の Visual Studio に適用されます。 Visual Studio for Mac については、「[プロジェクトおよびソリューションのプロパティの管理 (Visual Studio for Mac)](/visualstudio/mac/managing-solutions-and-project-properties)」を参照してください。

## <a name="project-properties"></a>プロジェクト プロパティ

プロジェクトのプロパティはグループに分類されており、グループごとに専用のプロパティ ページがあります。 ページは、言語およびプロジェクト タイプによって異なる場合があります。

### <a name="c-visual-basic-and-f-projects"></a>C# プロジェクト、Visual Basic プロジェクト、F# プロジェクト

C# プロジェクト、Visual Basic プロジェクト、F# プロジェクトでは、プロパティは**プロジェクト デザイナー**で公開されます。 C# の WPF プロジェクトの **[ビルド]** プロパティ ページを次の図に示します。

![Visual Studio プロジェクト デザイナー](../ide/media/vs2015_proppage_build.png)

**プロジェクト デザイナー**のそれぞれのプロパティ ページについては、「[プロジェクト プロパティのリファレンス](../ide/reference/project-properties-reference.md)」を参照してください。

> [!TIP]
> ソリューションには少数のプロパティがあり、プロジェクト項目にも少数のプロパティがあります。これらのプロパティは、**プロジェクト デザイナー**ではなく、[プロパティ ウィンドウ](../ide/reference/properties-window.md)からアクセスします。

### <a name="c-and-javascript-projects"></a>C++ プロジェクトおよび JavaScript プロジェクト

C++ プロジェクトおよび JavaScript プロジェクトには、プロジェクトのプロパティを管理するために別のユーザー インターフェイスが用意されています。 この図は、C++ プロジェクトのプロパティ ページを示しています (JavaScript ページはほぼ同じです)。

![Visual C&#43;&#43; プロジェクトのプロパティ](../ide/media/vs2015_projprops_cpp.png)

C++ プロジェクトのプロパティについては、[C++ プロジェクトのプロパティの操作](/cpp/build/working-with-project-properties)に関するページを参照してください。 JavaScript のプロパティの詳細については、「[プロパティ ページ、JavaScript](../ide/reference/property-pages-javascript.md)」を参照してください。

## <a name="solution-properties"></a>ソリューションのプロパティ

ソリューションのプロパティにアクセスするには、**ソリューション エクスプローラー**でソリューション ノードを右クリックし、 **[プロパティ]** を選択します。 このダイアログでは、**デバッグ** ビルドまたは**リリース** ビルド用にプロジェクト構成を設定し、**F5** キーを押した時点でのスタートアップ プロジェクトとなるプロジェクトを選択し、コード分析のオプションを設定します。

## <a name="see-also"></a>関連項目

- [Visual Studio のソリューションおよびプロジェクト](../ide/solutions-and-projects-in-visual-studio.md)
- [プロジェクトおよびソリューションのプロパティの管理 (Visual Studio for Mac)](/visualstudio/mac/managing-solutions-and-project-properties)
