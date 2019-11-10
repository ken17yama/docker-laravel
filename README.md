# docker-laravel

## 現在起動中のDocker環境の破棄

コンテナ停止・イメージ削除  
`docker-compose down --volumes --rmi all`

## Docker環境の再構築

作業ディレクトリの作成  
`mkdir [作業ディレクトリ]`

作業ディレクトリへの移動  
`cd [作業ディレクトリ]`

GitHubからクローン  
`git clone git@github.com:ken17yama/docker-laravel.git`

移動  
`cd docker-laravel`

dockerの起動  
`docker-compose up -d --build`

コンテナに入るために  
`exec winpty bash`

appコンテナに入る  
`docker-compose exec app ash`

vendorディレクトリのライブラリをインストール  
`composer install`

環境変数ファイルの作成  
`cp .env.example .env`

アプリケーションキーの生成  
`php artisan key:generate`

マイグレーションを実行  
`php artisan migrate`

アクセスしてみる  
http://127.0.0.1:10080

## 作業完了したら

コンテナから出る  
`exit`

dockerを停止  
`docker-compose down`
