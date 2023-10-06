# php-docker

## 手順
---
```shell:title
composer create-project laravel/laravel (filename)
```
※/docker/srcの中で実行。git cloneなどを実行することになる<br>
```shell:title
docker build -t (filename) .
```
※Dockerfileと同じ階層で実行する。<br>


docker-compose up -d 


docker run -p 8080:80 -d -v "$(pwd)"/src:/var/www/html --name php-container docker-test

ディレクトリの移動: docker-compose.ymlファイルが存在するディレクトリに移動します。

```shell:title
cd /path/to/directory/with/docker-compose.yml
```
コンテナの起動: docker-compose upコマンドを使用してすべてのサービスを一度に起動します。
```shell:title
docker-compose up -d
```
