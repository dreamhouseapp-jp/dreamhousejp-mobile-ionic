# DreamHouse モバイルアプリケーション

このリポジトリはDreamhouseモバイルアプリケーケーションの手順書とソースコードをホストしています。DreamHouseはSalesforceを使ったend-to-endのデモンストレーション用のサンプルアプリケーションです。 詳しくは[DreamHouseのサイト](http://dreamhouseappjp.io/) をご覧ください。


## Salesforceバックエンドのインストール

[こちらの手順](http://dreamhouseappjp.io/installation/) に従ってSalesforceバックエンドをインストールして下さい。

## アプリケーションのインストール

1. 最新バージョンのCordova 及び Ionic 2 ベータをインストールします:
    ```
    npm install -g cordova ionic@beta
    ```

    (Macの場合):
    ```
    sudo npm install -g cordova ionic@beta
    ```

1. このリポジトリをCloneします:
    ```
    git clone https://github.com/dreamhouseapp-jp/dreamhouse-mobile-ionic
    ```

1. `dreamhousejp-mobile-ionic` ディレクトリへ移動します:
    ```
    cd dreamhousejp-mobile-ionic
    ```

1. 依存ライブラリをインストールします:
    ```
    npm install
    ```

## ビルド及びブラウザでの動作

1. もしgulpがシステムにインストールされていない場合はインストールします:
    ```
    npm install -g gulp
    ```

    (Macの場合):
    ```
    sudo npm install -g gulp
    ```

1. force-serverをインストールします:
    ```
    npm install -g force-server
    ```

    (Macの場合):
    ```
    sudo npm install -g force-server
    ```

1. Ionicのビルドスクリプトを使ってJavascriptをビルドします:
    ```
    gulp build
    ```

1. アプリをブラウザで動作させます:
    ```
    force-server --root www
    ```

    - もしOAuthのウィンドウが見えない場合、ポップアップを有効にして再実行します。
    - Dreamhouseパッケージをインストールした組織にログインできることを確認します。


## ビルド及びデバイス上で動作

1. package.json `cordovaPlugins` 及び `cordovaPlatforms` を利用して内にあるアプリケーションの状態をリストアします:
    ```
    ionic state restore
    ```

1. Mobile SDK プラグインをインストールします:
    ```
    cordova plugin add https://github.com/forcedotcom/SalesforceMobileSDK-CordovaPlugin
    ```

1. iOS向けのアプリケーションをビルドします:
    ```
    ionic build ios
    ```

1.  ```dreamhouse-mobile-app/platforms/ios``` ディレクトリにある ```DreamHouse.xcodeproj``` を開きます。

1. Xcode上でアプリケーションをビルドするか、メニュー上の **Product** > **Archive** からApp Store もしくは Enterprise 配布ようにビルドします。もしXcode上でビルドがエラーになる場合は、 **DreamHouse** ターゲットから **Build Settings** タブを開き、 **bitcode** を検索して **Enable Bitcode** に **No** を選択し、再度実行します。
