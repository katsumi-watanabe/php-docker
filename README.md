# php-docker

## 手順
---
```shell:title
composer create-project laravel/laravel (filename)
```

ディレクトリの移動: docker-compose.ymlファイルが存在するディレクトリに移動します。

```shell:title
cd /path/to/directory/with/docker-compose.yml
```
コンテナの起動: docker-compose upコマンドを使用してすべてのサービスを一度に起動します。
```shell:title
docker-compose up -d
```

コンテナの停止: docker-compose downコマンドを使用してすべてのサービスを一度に停止します。
```shell:title
docker-compose down
```