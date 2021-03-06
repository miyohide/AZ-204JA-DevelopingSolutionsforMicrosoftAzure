﻿---
lab:
    title: 'ラボ: Azure コンテンツ配信ネットワークを使用して Web アプリケーションを強化する'
    module: 'モジュール 13: キャッシュとコンテンツ配信をソリューション内で統合する'
    type: 'Answer Key'
---

# ラボ: Azure コンテンツ配信ネットワークを使用して Web アプリケーションを強化
# 学生課題解答キー

## Microsoft Azure ユーザー インターフェイス

Microsoft クラウド ツールのダイナミックな特性を考えると、このトレーニング コンテンツの開発後に Azure ユーザー インターフェイスの変更が発生する可能性があります。これらの変更により、ラボの指示と手順が一致しない場合があります。

Microsoft では、コミュニティから必要な変更要望を受けたときにトレーニング コースを更新します。ただし、クラウドの更新は頻繁に行われるため、トレーニング コンテンツの更新前に UI が変更される場合もあります。**その場合は、変更に適宜対応して、ラボで要求されている内容を処理してください。**

## 指示

### 開始する前に

#### ラボの仮想マシンへのログイン

次の認証情報を使用して、Windows 10 仮想マシン (VM) にログインします。
    
-   ユーザー名: **Admin**

-   パスワード: **Pa55w.rd**

> **注意**: 仮想ラボ環境に接続する手順は講師が説明します。

#### インストールされたアプリケーションのレビュー

Windows 10 デスクトップでタスク バーを探します。タスク バーには、このラボで使用するアプリケーションのアイコンが含まれています。
    
-   Microsoft Edge

### 演習 1: Azure のリソースを作成

#### タスク 1: Azure portal を開く

1.  タスク バーで、**Microsoft Edge** アイコンを選択します。

1.  開いているブラウザー ウィンドウで、「Azure portal」(<https://portal.azure.com>)に移動します。

1.  Microsoft アカウントの電子メール アドレスを入力し、 「**次へ**」 を選択します。

1.  Microsoft アカウントのパスワードを入力し、「**サインイン**」 を選択します。

    > **注**: Azure portal に初めてログインする場合は、ポータルのツアーが表示されます。ツアーをスキップしてポータルの使用を開始するには、「**開始する**」 を選択します。


#### タスク 2: ストレージ アカウントの作成

1.  Azure portal のナビゲーション ペインで、「**すべてのサービス**」 を選択します。

1.  「**すべてのサービス**」 ブレードで、「**ストレージ アカウント**」 を選択します。

1.  「**ストレージ アカウント**」 ブレードで、ストレージ インスタンスの一覧を表示します。

1.  「**ストレージ アカウント**」 ブレードで、「**追加**」 を選択します。

1.  「**ストレージ アカウントの作成**」 ブレードで、「**基本**」 などのタブを探します。

    > **注**: 各タブは、新しいストレージ アカウントを作成するための、ワークフロー内のステップを表しています。いつでも 「**確認および作成**」 を選択して、残りのタブをスキップできます。

1.  「**基本**」 タブで、次の操作を実行します:
    
    1.  「**サブスクリプション**」 テキスト ボックスは既定値のままにします。

    1.  「**リソース グループ**」 セクションで、「**新規作成**」 を選択し、「**MarketingContent**」を入力し、「**OK**」 を選択します。

    1.  「**ストレージ アカウント名**」 テキスト ボックスに 「**contenthost*[yourname]***」と入力します。

    1.  「**場所**」 ドロップダウン リストで、 「**(US) 米国東部**」 リージョンを選択します。

    1.  「**パフォーマンス**」 セクションで、「**標準**」 を選択します。

    1.  「**アカウントの種類**」 ドロップダウン リストで、「**StorageV2 (汎用 v2)**」 を選択します。

    1.  「**レプリケーション**」 リストで、**読み取りアクセス geo 冗長ストレージ (RA-GRS)** を選択します。

    1.  「**アクセス層**」 セクションで、「**Hot**」 が選択されていることを確認します。

    1.  「**確認および作成**」 を選択します。

1.  「**レビュー + 作成**」 タブで、前の手順で選択したオプションをレビューします。

1.  指定した構成を使用してストレージ アカウントを作成するには、「**作成**」 を選択します。 

    > **注**: 演習を進める前に、作成タスクが完了するまで待ちます。
    
#### タスク 3: Azure App Service を使用して Web アプリを作成する

1.  Azure potalのナビゲーション ペインで、**リソースの作成** を選択します。

1.  「**新規**」 ブレードで、「**Marketplace を検索**」 テキスト ボックスを見つけます。

1.  検索ボックスに「**Web**」と入力し、Enter キーを押します。

1.  「**すべて**」 の検索結果ブレードで 「**Web アプリ**」 の結果を選択します。

1.  「**Web アプリ**」 ブレードで 「**作成**」 を選択します。

1.  2 番目の 「**Web アプリ**」 ブレードで、「**基本**」 などのブレードのタブを見つけます。

    > **注**: 各タブは、ワークフローで新しい Web アプリを作成するためのステップを表します。いつでも 「**確認および作成**」 を選択して、残りのタブをスキップできます。

1.  「**基本**」 タブで、次の操作を実行します
    
    1.  「**サブスクリプション**」 テキスト ボックスは既定値のままにします。
    
    1.  「**リソース グループ**」 の一覧で、「**MarketingContent**」 を選択します。

    1.  「**名前**」 ボックスに、**landingpage*[yourname]*** を入力します。

    1.  「**発行**」 セクションで、「**Docker コンテナー**」 を選択します。

    1.  「**オペレーティング システム**」 セクションで、「**Linux**」 を選択します。

    1.  「**リージョン**」 ドロップダウンで、「**米国東部**」 のリージョンを選択します。

    1.  「**Linux プラン (米国東部)**」 セクションで、「**新規作成**」 を選択し、「**名前**」 ボックスに 「**MarketingPlan**」 の値を入力して、「**OK**」 を選択します。

    1.  「**SKU とサイズ**」 セクションを既定値のままにします。

    1.  「**次へ: Docker**。

1.  「**Docker**」 タブで次の操作を実行します。

    1.  **オプション** ドロップダウン リストで、**シングル コンテナー**を選択します。

    1.  **イメージ ソース** ドロップダウン リストで、**Docker Hub**を選択します。

    1.  「**アクセス タイプ**」 ドロップダウン リストで、「**公開**」 を選択します。

    1.  「**イメージとタグ**」 ボックスに 「**microsoftlearning/edx-html-landing-page:latest**」と入力します。

    1.  **「確認および作成」** を選択します。

1.  「**レビュー + 作成**」 タブで、前の手順で選択したオプションをレビューします。

1.  指定された構成を使用して Web アプリを作成するには、「**作成**」 を選択します。 

    > **注**: 演習を進める前に、作成タスクが完了するまで待ちます。

1.  Azure potal の左側のナビゲーション ペインで、「**リソース グループ**」 を選択します。

1.  「**リソース グループ**」 ブレードで、この課題で先ほど作成した **MarketingContent** リソースグループを選択します。

1.  「**MarketingContent**」 ブレードで、 この課題で先ほど作成した **landingpage*[yourname]*** Web アプリを選択します。

1.  「**App Service**」 ブレードの 「**設定**」 で、「**プロパティ**」 リンクを選択します。

1.  「**プロパティ**」 セクションで、「**URL**」 テキスト ボックスの値を記録します。この値は、このラボの後半で使用します。

#### レビュー

この演習では、この課題の後で使用する Azure ストレージ アカウントと Azure Web アプリを作成しました。

### 演習 2: コンテンツ配信ネットワークとエンドポイントを構成する

#### タスク 1: Azure Cloud Shell を開く

1.  ポータルで、**Cloud Shell** アイコンを選択して新しいシェル インスタンスを開きます。

    > **注**: **Cloud Shell** アイコンは、大なり記号 () とアンダースコア文字 (\_) で表されます。

1.  サブスクリプションを使用して Cloud Shell を初めて開く場合は、**Azure Cloud Shell へようこそウィザード** を使って、初めて使用する Cloud Shell を構成できます。ウィザードで次の操作を実行します。
    
    -   シェルを使用して開始する新しいストレージ アカウントを作成するよう求めるダイアログ ボックスが表示されます。既定の設定を受け入れ、「**ストレージの作成**」 を選択します。 

    > **注**: Cloud Shell が初回のセットアップ手順を完了するのを待ってから、ラボを進めます。**Cloud Shell** の構成オプションが表示されない場合、最も可能性が高い原因は、このコースのラボで既存のサブスクリプションを使用していることだと考えられます。新しいサブスクリプションを使用しているという前提で課題を記述します。

1.  ポータルの **Cloud Shell** コマンド プロンプトで、次のコマンドを入力し、Enter キーを選択して Azure コマンド ライン インターフェイス (Azure CLI) ツールのバージョンを取得します。

    ```
    az --version
    ```

#### タスク 2: Microsoft.CDN プロバイダーを登録する

1.  ポータルの **Cloud Shell** コマンド プロンプトで、次の操作を実行します。

    1.  次のコマンドを入力し、Enter キーを押すと、Azure CLI のルート レベルにあるサブグループとコマンドの一覧が表示されます。

        ```
        az --help
        ```

    1.  次のコマンドを入力し、Enter キーを選択すると、リソース プロバイダーで使用できるコマンドの一覧が表示されます。

        ```
        az provider --help
        ```

    1.  次のコマンドを入力して Enter を選択すると、現在登録されているすべてのプロバイダーが一覧表示されます。

        ```
        az provider list
        ```

    1.  次のコマンドを入力してから Enter キーを選択すると、現在登録されているプロバイダーの名前空間のみが一覧表示されます。

        ```
        az provider list --query "[].namespace"
        ```

    1.  現在登録されているプロバイダーのリストを監視します。  **Microsoft.CDN** プロバイダーは、現在プロバイダーのリストに含まれている必要があります。

1.  ポータルの Cloud Shell ペインを閉じます。

#### タスク 3: コンテンツ配信ネットワーク プロファイルを作成する

1.  Azure potalのナビゲーション ペインで、**リソースの作成** を選択します。

1.  「**新規**」 ブレードで、「**Marketplace を検索**」 テキスト ボックスを見つけます。

1.  検索ボックスに **CDN** を入力し、Enter キーを押します。

1.  「**すべての検索結果**」 ブレードで、**CDN** の結果を選択します。

1.  **CDN** ブレードで、 **作成** を選択 します。

1.  **CDN profile** ブレードで、次の操作を実行します。

    1.  「**名前**」 ボックスに、「**contentdeliverynetwork**」を入力します。
    
    1.  **サブスクリプション** ボックスは既定値のままにします。

    1.  「**リソース グループ**」 の一覧で、「**MarketingContent**」 を選択します。
    
    1.  **リソースグループの場所** ドロップダウン リストは、既定値に設定したままにします。

    1.  「**価格レベル**」 ドロップダウン リストで、「**Standard Akamai**」 を選択します。

    1.  「**新しい CDN エンドポイントを今すぐ作成する**」 チェック ボックスがオフになっていることを確認します。

    1.  「**作成**」 を選択します。
  
    > **注**: Azure がCDN アプリの作成を完了するのを待ってから、ラボに進みます。アプリの作成時に通知が届きます。

#### タスク 4: ストレージ コンテナーの構成

1.  Azure potal の左側のナビゲーション ペインで、「**リソース グループ**」 を選択します。

1.  「**リソース グループ**」 ブレードで、この課題で先ほど作成した **MarketingContent** リソースグループを選択します。

1.  **MarketingContent** ブレードで、 この実習ラボで前に作成した **contenthost*[yourname]*** ストレージ アカウントを選択します。

1.  「**ストレージ アカウント**」 ブレードで、「**Blob サービス**」 セクションにある 「**コンテナー**」 を選択します。

1.  **Containers** セクションで、**+ コンテナー** を選択します。

1.  「**新規コンテナー**」 ポップアップ ウィンドウで、次の操作を実行します。
    
    1.  「**名前**」 テキスト ボックスに、「**media**」を入力します。
    
    1.  **パブリック アクセス レベル**ドロップダウン リストで、**BLOB (BLOBのみの匿名読み取りアクセス)** を選択します。 
    
    1.  「**OK**」 を選択します。

1.  **Containers** セクションで、**+ コンテナ** をもう一度選択します。

1.  「**新規コンテナー**」 ポップアップ ウィンドウで、次の操作を実行します。
    
    1.  **名前** テキスト ボックスに、**video** を入力します。
    
    1.  **パブリック アクセス レベル**ドロップダウン リストで、**BLOB (BLOBのみの匿名読み取りアクセス)** を選択します。 
    
    1.  「**OK**」 を選択します。

1.  更新されたコンテナーのリストを監視します。

#### タスク 5: コンテンツ配信ネットワーク エンドポイントの作成

1.  Azure portal のナビゲーション ペインで、「**リソース グループ**」 リンクを選択します。

1.  「**リソース グループ**」 ブレードで、 この実習ラボで前に作成した **MarketingContent** リソース グループを探して選択します。

1.  **MarketingContent** ブレードで、 この実習ラボで前に作成した **contentdeliverynetwork** CDN プロファイル を選択します。

1.  **CDN プロファイル** ブレードで、「**+ エンドポイント**」 を選択 します。

1.  「**エンドポイントの追加**」 ポップアップ ダイアログ ボックスで、次のアクションを実行します。

    1.  **名前** テキスト ボックスに、**cdnmedia*[yourname]*** を入力します。

    1.  「**配信元の種類**」 ドロップダウン リストで、「**ストレージ**」 を選択します。

    1.  **配信元のホスト名** ドロップダウン リストで、 この実習ラボで前に作成した **contenthost*[yourname]*.blob.core.windows.net** ストレージ アカウント オプションを選択します。

    1.  **配信元のパス** テキスト ボックスに **/media**と入力します。

    1.  **配信元のホスト ヘッダー**テキスト ボックスは既定値のままにします。

    1.  **プロトコル**と**配信元のポート**のセクションは、既定値のままにします。

    1.  **最適化の対象** ドロップダウン リストで、**一般的な Web 配信** を選択します。

    1.  「**追加**」 を選択します。

1.  **CDN プロファイル** ブレードに戻り、「**+ エンドポイント**」 を再度選択します。

1.  「**エンドポイントの追加**」 ポップアップ ダイアログ ボックスで、次のアクションを実行します。

    1.  「**名前**」 テキスト ボックスに、**cdnvideo*[yourname]*** を入力します。

    1.  「**配信元の種類**」 ドロップダウン リストで、「**ストレージ**」 を選択します。

    1.  **配信元のホスト名** ドロップダウン リストで、 この実習ラボで前に作成した **contenthost*[yourname]*.blob.core.windows.net** ストレージ アカウント オプションを選択します。

    1.  「**配信元のパス**」 テキスト ボックスに「**/video**」 と入力します。

    1.  **配信元のホスト ヘッダー** テキスト ボックスは既定値のままにします。

    1.  **プロトコル**と**配信元のポート** のセクションは、既定値のままにします。

    1.  **最適化の対象** ドロップダウン リストで、**ビデオ オンデマンド メディア ストリーミング** を選択します。

    1.  「**追加**」 を選択します。

1.  **CDN プロファイル** ブレードに戻り、「**+ エンドポイント**」 を再度選択します。

1.  「**エンドポイントの追加**」 ポップアップ ダイアログ ボックスで、次のアクションを実行します。

    1.  「**名前**」 テキスト ボックスに、**cdnweb*[yourname]*** を入力します。

    1.  「**配信元の種類**」 ドロップダウン リストで、「**Web アプリ**」 を選択します。

    1.  「**配信元のホスト名**」 ドロップダウン リストで、 このラボで前に作成した **landingpage*[yourname]*.azurewebsites.net** Web アプリ オプションを選択します。

    1.  **配信元のパス** テキスト ボックスは、既定値のままにしておきます。

    1.  **配信元のホスト ヘッダー** テキスト ボックスは既定値のままにします。

    1.  **プロトコル**と**配信元のポート** のセクションは、既定値のままにします。

    1.  **最適化の対象** ドロップダウン リストで、**一般的な Web 配信** を選択します。

    1.  「**追加**」 を選択します。

#### レビュー

この演習では、コンテンツ配信ネットワークのリソースプロバイダーを登録し、そのプロバイダーを使用して CDN プロファイルとエンドポイント リソースの両方を作成しました。

### エクササイズ 3: 静的 Web コンテンツ をアップロード、構成する

#### タスク 1: ランディング ページを監視する

1.  Azure potal の左側のナビゲーション ペインで、「**リソース グループ**」 を選択します。

1.  「**リソース グループ**」 ブレードで、この課題で先ほど作成した **MarketingContent** リソースグループを選択します。

1.  「**MarketingContent**」 ブレードで、 この課題で先ほど作成した **landingpage*[yourname]*** Web アプリを選択します。

1.  「**App サービス**」 ブレードで、「**Browse**」 を選択します。新しいブラウザー ウインドウまたはタブが開き、現在の Web サイトが表示されます。

1.  画面に表示されるエラー メッセージを監視します。マルチメディア コンテンツを参照するように指定した設定を構成するまで、Web サイトは機能しません。

1.  Azure potal を表示しており、現在開いているブラウザー ウインドウに戻ります。

#### タスク 2: ストレージ BLOB のアップロード

1.  Azure potal の左側のナビゲーション ペインで、「**リソース グループ**」 を選択します。

1.  「**リソース グループ**」 ブレードで、この課題で先ほど作成した **MarketingContent** リソースグループを選択します。

1.  **MarketingContent** ブレードで、 この実習ラボで前に作成した **contenthost*[yourname]*** ストレージ アカウントを選択します。

1.  「**ストレージ アカウント**」 ブレードで、「**Blob サービス**」 セクションにある 「**コンテナー**」 を選択します。

1.  **コンテナ** セクションで、**メディア** コンテナを選択します。

1.  「**コンテナー**」 ブレードで、「**アップロード**」 を選択します。

1.  「**BLOB のアップロード**」 ポップアップ ウィンドウで、次の操作を実行します。
    
    1.  「**ファイル**」 セクションで、「**フォルダー**」 アイコンを選択します。
    
    1.  **エクスプローラー** ウィンドウで、**Allfiles (F):\\Allfiles\\Labs\\13\\Starter** を参照し、次のファイルを選択し、「**開く**」 を選択します。

        -   **campus.jpg**
        
        -   **conference.jpg**
        
        -   **poster.jpg**
    
    1.  「**ファイルが既に存在する場合は上書き**」 が選択されていることを確認し、「**アップロード**」 を選択します。  

    > **注**: この演習を続行する前に、BLOB がアップロードされるのを待ちます。

1.  「**コンテナー**」 ブレードに戻り 、「**設定**」 セクションの 「**プロパティ**」 を選択します。

1.  「**URL**」 テキスト ボックスの値を記録します。この値は、この課題の後半で使用します。

1.  **コンテナー** ブレードを閉じます。

1.  **コンテナー** ブレードに戻り、**ビデオ** コンテナーを選択します。

1.  「**コンテナー**」 ブレードで、「**アップロード**」 を選択します。

1.  「**BLOB のアップロード**」 ポップアップ ウィンドウで、次の操作を実行します。
    
    1.  「**ファイル**」 セクションで、「**フォルダー」**」 アイコンを選択します。
    
    1.  **エクスプローラー** ウィンドウで、**Allfiles (F):\\Allfiles\\Labs\\13\\Starter** を参照し、**welcome.mp4** ファイルを選択し、「**開く**」 を選択します。
    
    1.  「**ファイルが既に存在する場合は上書き**」 が選択されていることを確認し、「**アップロード**」 を選択します。  

    > **注**: この演習を続行する前に、BLOB がアップロードされるのを待ちます。

1.  「**コンテナー**」 ブレードに戻り 、「**設定**」 セクションの 「**プロパティ**」 を選択します。

1.  「**URL**」 テキスト ボックスの値を記録します。この値は、この課題の後半で使用します。

#### タスク 3: Web アプリの設定を構成する

1.  Azure potal の左側のナビゲーション ペインで、「**リソース グループ**」 を選択します。

1.  「**リソース グループ**」 ブレードで、この課題で先ほど作成した **MarketingContent** リソースグループを選択します。

1.  「**MarketingContent**」 ブレードで、 この課題で先ほど作成した **landingpage*[yourname]*** Web アプリを選択します。

1.  **App Service** ブレードの**設定**カテゴリで**構成**リンクを選択します。

1.  **構成**セクションで、次の操作を実行します：
    
    1.  「**アプリケーションの設定**」 タブを選択し、「**新しいアプリケーション設定**」 を選択します。
    
    1.  表示される 「**アプリケーションの追加/編集 設定**」 ポップアップで、「**名前**」 テキストボックスに「**CDNMediaEndpoint**」と入力します。
    
    1.  「**値**」 テキスト ボックス に、この課題で先ほど記録した **contenthost*[yourname]*** ストレージ アカウントの**メディア** コンテナーの **URI** 値を入力します。
    
    1.  **デプロイ スロット 設定** テキスト ボックスを既定値のままにし、「**OK**」 を選択してポップアップ ウィンドウを閉じます。
    
    1.  「**構成**」セクションに戻り、「**新しいアプリケーション設定**」 を選択します。
    
    1.  表示される 「**アプリケーションの追加/編集 設定**」 ポップアップ ウインドウで、「**名前**」 テキストボックスに「**CDNVideoEndpoint**」と入力します。
    
    1.  「**値**」 テキスト ボックスに、この演習で前に記録した **contenthost*[yourname]*** ストレージ アカウントの**ビデオ** コンテナの**URI** 値を入力します。
    
    1.  **デプロイ スロット 設定** テキスト ボックスを既定値のままにし、「**OK**」 を選択してポップアップ ウィンドウを閉じます。
    
    1.  「**構成**」 セクションに戻り、 ブレードの 「**保存**」 を選択して設定を保持します。  

    > **注**: 課題を進める前に、アプリケーションの設定が保持されるまで待ちます。

#### タスク 4: 修正されたランディング ページの検証

1.  Azure potal の左側のナビゲーション ペインで、「**リソース グループ**」 を選択します。

1.  「**リソース グループ**」 ブレードで、この課題で先ほど作成した **MarketingContent** リソースグループを選択します。

1.  「**MarketingContent**」 ブレードで、 この課題で先ほど作成した **landingpage*[yourname]*** Web アプリを選択します。

1.  **App Service** ブレードで、「**再起動**」 を選択します。この操作により、Web アプリが再起動します。

    > **注**: ラボを進める前に、再起動操作が完了するまで待ちます。操作の完了時に通知が届きます。

1.  **App Service** ブレードに戻る場合は、「**閲覧**」 を選択します。新しいブラウザー ウインドウまたはタブが開き、現在の Web サイトが表示されます。

1.  さまざまな種類のマルチメディア コンテンツをレンダリングする更新された Web サイトを監視します。

1.  Azure potal を表示しており、現在開いているブラウザー ウインドウに戻ります。

#### レビュー

この演習では、ストレージ コンテナーに BLOB としてマルチメディア コンテンツをアップロードし、ストレージ BLOB を直接指すように Web アプリを更新します。

### 演習 4: コンテンツ配信ネットワーク エンドポイントを使用する

#### タスク 1: エンドポイント URI の取得

1.  Azure portal のナビゲーション ペインで、「**リソース グループ**」 リンクを選択します。

1.  「**リソース グループ**」 ブレードで、 この実習ラボで前に作成した **MarketingContent** リソース グループを探して選択します。

1.  **MarketingContent** ブレードで、 この実習ラボで前に作成した**contentdeliverynetwork** CDN プロファイル を選択します。

1.  **CDN プロファイル** ブレードで、**cdnmedia*[yourname]*** エンドポイントを選択します。 

1.  **エンドポイント** ブレードで、「**エンドポイント ホスト名**」 テキスト ボックスの値をコピーします。この値は、この課題の後半で使用します。

1.  **エンド ポイント** ブレードを閉じます。

1.  **CDN プロファイル** ブレードに戻り、**cdnvideo*[yourname]***  エンドポイントを選択します。

1.  **エンドポイント** ブレードで、「**エンドポイント ホスト名**」 テキスト ボックスの値をコピーします。これらの値は、この演習の後半で使用します。

1.  **エンド ポイント** ブレードを閉じます。

#### タスク 2: マルチメディア コンテンツのテスト

1.  ラボで前にコピーした **cdnmedia*[yourname]*** エンドポイントからの**エンドポイント ホスト名** URL と相対パス **/campus.jpg** を組み合わせて、**campus.jpg** リソースの URL を構築します。

    > **注**: たとえば、 **エンドポイント ホスト名** URL が **https://cdnmediastudent.azureedge.net/** である場合、 新しく構築される URL は **https://cdnmediastudent.azureedge.net/campus.jpg** になります。     

1.  ラボで前にコピーした **cdnmedia*[yourname]*** エンドポイントからの**エンドポイント ホスト名** URL と相対パス **/conference.jpg**  を組み合わせて、**conference.jpg** リソースの URL を構築します。

    > **注**: たとえば、 **エンドポイント ホスト名** URL が **https://cdnmediastudent.azureedge.net/** である場合  、新しく作成される URL は **https://cdnmediastudent.azureedge.net/conference.jpg** になります。     

1.  ラボで前にコピーした **cdnmedia*[yourname]*** エンドポイントからの **エンドポイント ホスト名** URLと相対パス **/poster.jpg** を組み合わせて、**poster.jpg** リソースの URL を構築します。

    > **注**: たとえば、 **エンドポイント ホスト名**の URL が **https://cdnmediastudent.azureedge.net/** である場合、 新しく作成される URL は **https://cdnmediastudent.azureedge.net/poster.jpg** になります。     

1.  課題で前にコピーした **cdnvideo*[yourname]*** エンドポイントからの **エンドポイント ホスト名** URLと相対パス **/welcome.mp4** を組み合わせて、**welcome.mp4** リソースの URL を構築します。

    > **注**: たとえば、 **エンドポイント ホスト名** URL が **https://cdnvideostudent.azureedge.net/** の場合、 新しく作成される URL は **https://cdnvideostudent.azureedge.net/welcome.mp4** になります。     

1.  タスク バーで、「**Microsoft Edge**」 アイコンを右クリックするか、ショートカットメニューを有効化したら、「**新しいウインドウ**」 を選択します。

1.  新しいブラウザー ウィンドウで、**campus.jpg** メディア リソース用に構築した URL に移動し、リソースが正常に見つかったことを確認します。 

    > **注**: コンテンツがまだ利用できない場合、CDN エンドポイントは初期化中です。この初期化プロセスは、5 分から 15 分かかり任意の場所で実行できます。

1.  **conference.jpg** メディア リソース用に構築した URL に移動し、リソースが正常に見つかったことを確認します。 

1.  **poster.jpg** メディア リソース用に作成した URL に移動し、リソースが正常に見つかったことを確認します。 

1.  **welcome.mp4** ビデオ リソース用に構築した URL に移動し、リソースが正常に見つかったことを確認します。 

1.  このタスクで作成したブラウザー ウィンドウを閉じます。

#### タスク 3: Web アプリの設定を更新する

1.  Azure potal の左側のナビゲーション ペインで、「**リソース グループ**」 を選択します。

1.  「**リソース グループ**」 ブレードで、この課題で先ほど作成した **MarketingContent** リソースグループを選択します。

1.  「**MarketingContent**」 ブレードで、 この課題で先ほど作成した **landingpage*[yourname]*** Web アプリを選択します。

1.  **App Service** ブレードの **設定** カテゴリで **構成** リンクを選択します。

1.  「**構成**」 セクションで、次のアクションを実行します。
    
    1.  「**アプリケーション設定**」 タブを選択します。
    
    1.  既存の **CDN メディア エンドポイント**アプリケーション設定を選択します。

    1.  「**アプリケーション設定の追加/編集**」 ポップアップ ダイアログ ボックスで、ラボの前の手順でコピーした **cdnmedia*[yourname]*** エンドポイントの **エンドポイント ホスト名** URL を 「**値**」 ボックスに入力し、「**OK**」 を選択します。
    
    1.  既存の **CDN ビデオ エンドポイント** アプリケーション設定を選択します。

    1.  「**アプリケーション設定の追加/編集**」 ダイアログ ボックスで、前の手順でコピーした **cdnvideo*[yourname]*** エンドポイントの **エンドポイント ホスト名** URLを、「**値**」 ボックス に入力し、「**OK**」 を選択します。
    
    1.  ブレードの 「**保存**」 を選択して、設定を保存します。  

    > **注**: 演習を進める前に、アプリケーションの設定が保持されるまで待ちます。

1.  **設定** セクションに戻り、**Overview** を選択します。

1.  **Overview** セクションで、**リスタート** を選択します。この操作により、Web アプリが再起動します。

    > **注**: ラボを進める前に、再起動操作が完了するまで待ちます。操作の完了時に通知が届きます。

#### タスク 4: Web コンテンツをテストする

1.  Azure portal のナビゲーション ペインで、「**リソース グループ**」 リンクを選択します。

1.  「**リソース グループ**」 ブレードで、 この実習ラボで前に作成した **MarketingContent** リソース グループを探して選択します。

1.  **MarketingContent** ブレードで、 この実習ラボで前に作成した **contentdeliverynetwork** CDN プロファイル を選択します。

1.  **CDN プロファイル** ブレードで、**cdnweb*[yourname]*** エンドポイントを選択します。

1.  **エンドポイント** ブレードで、「**エンドポイント ホスト名**」 テキスト ボックスの値をコピーします。

1.  タスク バーで、「**Microsoft Edge**」 アイコンを右クリックするか、ショートカットメニューを有効化したら、「**新しいウインドウ**」 を選択します。

1.  新しいブラウザー ウィンドウで、**cdnweb*[yourname]*** エンドポイントの **エンドポイント ホスト名** URL に移動します。

1.  コンテンツ配信ネットワークを使用して提供される Web サイトとマルチメディア コンテンツを確認します。

#### レビュー

この演習では、コンテンツ配信ネットワークを使用してマルチメディア コンテンツを提供し、Web アプリケーション自体にサービスを提供するように Web アプリを更新しました。

### エクササイズ 5: サブスクリプションのクリーンアップ 

#### タスク 1: Azure Cloud Shellを開き、リソース グループを一覧表示する

1.  ポータルで、**Cloud Shell** アイコンを選択して新しいシェル インスタンスを開きます。

1.  Cloud Shellがまだ構成されていない場合は、既定の設定を使用して Bash のシェルを構成します。

1.  ポータルにある **Cloud Shell** コマンド プロンプトで次のコマンドを入力し、Enter キーを押してサブスクリプション内のすべてのリソース グループを一覧表示します。

    ```
    az group list
    ```

1.  次のコマンドを入力し、Enter キーを押して、リソース グループを削除する可能性のあるコマンドの一覧を表示します。

    ```
    az group delete --help
    ```

#### タスク 2: リソース グループの削除

1.  次のコマンドを入力してから、Enter キーを押して **MarketingContent** リソース グループを削除します。

    ```
    az group delete --name MarketingContent --no-wait --yes
    ```
    
1.  ポータルの Cloud Shell ペインを閉じます。

#### タスク 3: アクティブなアプリケーションを閉じる

1.     現在実行中の Microsoft Edge アプリケーションを閉じます。

#### レビュー

この実習では、この演習で使用したリソース グループを削除してサブスクリプションをクリーンアップしました。