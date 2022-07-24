# rails-env

Docker 環境　 Rails + MySQL

- Ruby 2.5
- Rails 5
- MySQL 5.7

## M1 Mac の場合

docker-compose.yml に追記

```bash
db:
  platform: linux/x86_64
```

## 初期設定

プロジェクト作成

```bash
$ docker-compose run app rails new . --force --api --database=mysql -T
```

database.yml の設定変更(config/database.yml)

```bash
password: password
host: db
```

ビルドして起動

```bash
$ sudo docker-compose up -d --build
```

db 作成

```bash
$ docker-compose exec app rails db:create
```
