Rails App Startup Script
===

# Overview
Railsアプリの起動スクリプトです。
AppサーバをUnicornで想定したRailsアプリケーションのための起動スクリプトです。

## Usage

### スクリプトの編集
`rails_app`をRailsアプリケーションの名前に置き換えます。

`deploy_user`をデプロイ用のユーザ名に置き換えます。

`/path/to/app_root`をRailsアプリケーションのルートディレクトリに置き換えます。
`ex. /home/deploy_user/current`

`RAILS_ENV=production`Productionモードに設定しているため、ステージングで使う場合は`staging`に変更します。

### スクリプトの設置
スクリプトを編集したらコピペなりscpでサーバに送るなりして`/etc/init.d/`配下に格納します。
``` sh
$ vim /etc/init.d/rails_app
$ chmod 755 /etc/init.d/rails_app
```

### サービスの起動 / 停止 / 再起動
スクリプトによるRailsアプリケーションの起動 / 停止 / 再起動のコマンド
``` sh
$ service rails_app start
$ service rails_app stop
$ service rails_app restart
```

### 自動起動設定
サーバ起動時に起動するよう設定
``` sh
$ chkconfig rails_app on
```

