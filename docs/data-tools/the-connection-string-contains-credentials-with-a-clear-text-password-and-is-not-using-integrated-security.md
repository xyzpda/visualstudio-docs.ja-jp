---
title: 接続文字列にはクリア テキスト パスワード付きの資格情報が含まれていて、統合セキュリティは使用されていません
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 501d85af-92e0-4471-b280-8a59c0688575
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 0a8cb18e84263d7b7144764d007a2928956fc77b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72641021"
---
# <a name="the-connection-string-contains-credentials-with-a-clear-text-password-and-is-not-using-integrated-security"></a>接続文字列にはクリア テキスト パスワード付きの資格情報が含まれていて、統合セキュリティは使用されていません

重要情報を含む接続文字列を現在の DBML ファイルとアプリケーション構成ファイルに保存しますか?  重要情報を含めずに接続文字列を保存する場合は、 **[いいえ]** をクリックします。

機密情報 (接続文字列に含まれているパスワード) を含むデータ接続を扱う場合は、接続文字列をプロジェクトの DBML ファイルおよびアプリケーション構成ファイルに保存するときに、機密情報を含めるかどうかを選択するオプションが提供されます。

> [!WARNING]
> **[接続]** プロパティの **[アプリケーション設定]** プロパティが明示的に **[False]** に設定されている場合、パスワードは DBML ファイルに追加されます。

## <a name="save-options"></a>保存オプション

- 接続文字列を機密情報と共に保存するには、[**はい]** を選択します。

   接続文字列がアプリケーション設定として格納されます。 接続文字列には、プレーンテキストの機密情報が含まれます。 DBML ファイルには機密情報は含まれません。

- 機密情報を使用せずに接続文字列を保存するには、 **[いいえ]** を選択します。

   接続文字列がアプリケーション設定として格納されますが、パスワードは含まれません。

## <a name="see-also"></a>関連項目

- [Visual Studio の LINQ to SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)