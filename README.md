# php-docker

## 手順
---
srcファイル配下に移動してlaravelファイルを作成する
※git　cloneなども想定
```shell:title
composer create-project laravel/laravel (filename)
```

000-default.confのDocumentRootとDirectoryのprojectnameを変更する
```shell:title
/var/www/html/projectname/public
```

ディレクトリの移動: docker-compose.ymlファイルが存在するディレクトリに移動しファイル内容を調整する

コンテナの起動: docker-compose upコマンドを使用してすべてのサービスを一度に起動します。
```shell:title
docker-compose up -d
```

コンテナの停止: docker-compose downコマンドを使用してすべてのサービスを一度に停止します
```shell:title
docker-compose down
```

全て停止:　Portが被って起動できない時に使用する
```shell:title
docker stop a9800d8d51b5
```

## ４０４エラー
---
### Apache原因
```shell:title
docker-compose exec app apache2ctl -M | grep rewrite
```

```shell:title
AH00112: Warning: DocumentRoot [/var/www/html/projectname/public] does not exist
AH00558: apache2: Could not reliably determine the server's fully qualified domain name, using 172.26.0.2. Set the 'ServerName' directive globally to suppress this message
 rewrite_module (shared)
```

上のようなエラーが出る場合は再ビルドする
※--no-cache オプションを使用すると、Dockerはキャッシュを使用せずにイメージをビルドします。これは、以前のビルドからのレイヤーを再利用せず、すべての手順を最初から実行することを意味します。
```shell:title
docker-compose down
docker-compose build --no-cache
docker-compose up -d
```
