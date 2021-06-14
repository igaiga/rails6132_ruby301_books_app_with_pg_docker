神速さんのこのページをもとにつくったRailsアプリ

- Railsアプリの開発環境向けDockerfile + docker-compose.yml
- https://sinsoku.hatenablog.com/entry/2021/03/24/100000

### 初回の環境構築
- $ docker-compose build
- $ docker-compose run --rm web bin/setup
  - bundle install, yarn install, db作成など

### Webサーバの起動
- $ docker-compose run --rm --service-ports web
  - http://localhost:3000 からアクセスできる

### Rails コマンドの実行
- $ docker-compose run --rm web bin/rails -T

### コンテナ内 shell
- $ docker-compose run --rm web bash

### テストの実行
- $ docker-compose run --rm -e RAILS_ENV=test web bin/rails db:test:prepare
- $ docker-compose run --rm -e RAILS_ENV=test web bin/rails test

### 全てのvolumeを削除する

- $ docker-compose down --volumes
  - 開発環境を一新する
