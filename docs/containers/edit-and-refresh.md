---
title: ローカルの Docker コンテナーでアプリをデバッグする | Microsoft Docs
description: 編集と更新を使用して、ローカルの Docker コンテナーで実行されているアプリに変更を加え、デバッグのブレークポイントを設定する方法について説明します。
ms.author: ghogen
author: ghogen
manager: jillfra
ms.assetid: 480e3062-aae7-48ef-9701-e4f9ea041382
ms.topic: conceptual
ms.workload: multiple
ms.date: 07/25/2019
ms.technology: vs-azure
ms.openlocfilehash: 5af092bbcb987f45b10121f37d40eaa5466c3da5
ms.sourcegitcommit: 2db01751deeee7b2bdb1db25419ea6706e6fcdf8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71126155"
---
# <a name="debug-apps-in-a-local-docker-container"></a>ローカルの Docker コンテナーでのアプリのデバッグ

Visual Studio を使用すると、一貫した方法でアプリケーションの開発と検証を Docker コンテナーでローカルで実行できます。 コード変更のたびにコンテナーを再起動する必要はありません。

この記事では、Visual Studio を使用して、ローカルの Docker コンテナーで ASP.NET Core Web アプリを起動し、変更を行い、その変更を反映するためにブラウザーの表示を更新する方法について説明します。 この記事では、コンテナー化された ASP.NET Core Web アプリと .NET Framework コンソール アプリにデバッグ用のブレークポイントを設定する方法についても説明します。

## <a name="prerequisites"></a>必須コンポーネント

ローカルの Docker コンテナーでアプリをデバッグするには、次のツールをインストールする必要があります。

::: moniker range="vs-2017"

* Web 開発ワークロードがインストールされている [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download)

::: moniker-end

::: moniker range="vs-2019"

* Web 開発ワークロードがインストールされている [Visual Studio 2019](https://visualstudio.microsoft.com/downloads)

::: moniker-end

ローカルで Docker コンテナーを実行するには、ローカルの Docker クライアントを用意する必要があります。 [Docker Toolbox](https://www.docker.com/products/docker-toolbox) を使用できますが、Hyper-V を無効にする必要があります。 [Docker for Windows](https://www.docker.com/get-docker) を使用することもできますが、Hyper-V が使用され、Windows 10 が必須となります。 

Docker コンテナーは .NET Framework プロジェクトと .NET Core プロジェクトで利用できます。 2 つの例を見てみましょう。 まず、.NET Core Web アプリを見てみます。 次に、.NET Framework コンソール アプリを見てみます。

## <a name="create-a-web-app"></a>Web アプリの作成

::: moniker range="vs-2017"
[!INCLUDE [create-aspnet5-app](../azure/includes/create-aspnet5-app.md)]
::: moniker-end
::: moniker range=">= vs-2019"
[!INCLUDE [create-aspnet5-app-2019](../azure/includes/vs-2019/create-aspnet5-app-2019.md)]
::: moniker-end

### <a name="edit-your-code-and-refresh"></a>コードを編集して更新する

変更をすばやく反復する目的で、コンテナーでアプリケーションを起動できます。 次に、変更を続け、IIS Express の場合と同じように変更を表示します。

1. **[ソリューション構成]** を **[デバッグ]** に設定します。 次に、**Ctrl**+**F5** を押し、Docker イメージをビルドしてローカルで実行します。

    コンテナー イメージがビルドされ、Docker コンテナーで実行されると、Visual Studio では、既定のブラウザーでその Web アプリが起動します。

2. *インデックス* ページに移動します。 このページで変更を行います。
3. Visual Studio に戻り、*Index.cshtml* を開きます。
4. ファイルの最後に次の HTML コンテンツを追加し、変更を保存します。

    ```html
    <h1>Hello from a Docker container!</h1>
    ```

5. 出力ウィンドウで、.NET ビルドが完了して次の行が表示されたら、お使いのブラウザーに戻り、ページを更新します。

   ```output
   Now listening on: http://*:80
   Application started. Press Ctrl+C to shut down.
   ```

変更が適用されました。

### <a name="debug-with-breakpoints"></a>ブレークポイントを使用してデバッグする

変更にはさらなる調査が必要になることがしばしばあります。 この作業には、Visual Studio のデバッグ機能を利用できます。

1. Visual Studio で *Index.cshtml.cs* を開きます。
2. `OnGet` メソッドの内容を次のコードに置き換えます。

   ```csharp
       ViewData["Message"] = "Your application description page from within a container";
   ```

3. コード行の左側にブレークポイントを設定します。
4. デバッグを開始してブレークポイントまで進めるには、F5 キーを押します。
5. Visual Studio に切り替えるとブレークポイントが表示されます。 値を調べます。

   ![ブレークポイント](media/edit-and-refresh/breakpoint.png)

## <a name="create-a-net-framework-console-app"></a>.NET Framework コンソール アプリを作成する

.NET Framework コンソール アプリ プロジェクトを使用するとき、オーケストレーションなしで Docker サポートを追加することはできません。 ただし、Docker プロジェクトを 1 つだけ使用している場合でも、次の手順を使用できます。

1. .NET Framework コンソール アプリ プロジェクトを新規作成する
1. ソリューション エクスプローラーでプロジェクト ノードを右クリックし、 **[追加]** 、 **[Container Orchestration Support]\(コンテナー オーケストレーションのサポート\)** の順に選択します。  ダイアログ ボックスが表示されたら、 **[Docker Compose]** を選択します。 Dockerfile がプロジェクトに追加され、Docker Compose プロジェクトと関連サポート ファイルが追加されます。

### <a name="debug-with-breakpoints"></a>ブレークポイントを使用してデバッグする

1. ソリューション エクスプローラーで、*Program.cs* を開きます。
2. `Main` メソッドの内容を次のコードに置き換えます。

   ```csharp
       System.Console.WriteLine("Hello, world!");
   ```

3. ブレークポイントをコード行の左側に設定します。
4. F5 キーを押すと、デバッグが開始され、ブレークポイントまで進みます。
5. Visual Studio に切り替えてブレークポイントを表示し、値を調べます。

   ![ブレークポイント](media/edit-and-refresh/breakpoint-console.png)

## <a name="container-reuse"></a>コンテナーの再利用

開発サイクル中、Dockerfile を変更したとき、Visual Studio では、コンテナー イメージとコンテナー自体だけが再構築されます。 Dockerfile を変更しない場合、Visual Studio では、以前の実行からのコンテナーが再利用されます。

コンテナーを手動で修正した後、クリーンなコンテナー イメージで再開する場合、Visual Studio で **[ビルド]** の **[クリーン]** コマンドを使用し、その後、通常どおりビルドします。

## <a name="troubleshoot"></a>トラブルシューティング

[Visual Studio Docker 開発で発生する問題を解決する](troubleshooting-docker-errors.md)方法について説明します。

## <a name="more-about-docker-with-visual-studio-windows-and-azure"></a>Visual Studio、Windows、および Azure での Docker の詳細について

* [Visual Studio でコンテナーを開発する](/visualstudio/containers)方法について説明します。
* Docker コンテナーをビルドし、デプロイする方法については、「[Azure Pipelines 向けの Docker の統合](https://aka.ms/dockertoolsforvsts)」を参照してください。
* Windows Server と Nano Server に関する記事の索引が必要であれば、「[Windows コンテナー情報](https://aka.ms/containers)」を参照してください。
* Azure Kubernetes Service の詳細は[こちら](https://azure.microsoft.com/services/kubernetes-service/)をご覧ください。また、[Azure Kubernetes Service ドキュメント](/azure/aks)を確認してください。
