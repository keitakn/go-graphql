# go-graphql
GoLang製のGraphQLサンプルプロジェクト

## ローカル環境で動作させる

### 初回起動時

`docker-compose up --build -d`

### 2回目以降の起動時

`docker-compose up`

`curl -g 'http://localhost:9998?query={user(id:"1"){name}}'` で動作している事を確認出来る。

### 停止

`docker-compose down`

### 停止とDockerイメージの削除を同時に行う

`docker-compose down --rmi all`

## 本番環境で動作させる

以下のコマンドを実行しコンテナを立ち上げる。

```
docker build -t go-graphql .
docker run -p 8080:8080 -d --name go-graphql go-graphql
```

`curl -g 'http://localhost:8080?query={user(id:"1"){name}}'` で動作確認を行い問題なければDocker HubやECR等に反映させる。

## コードの整形
`go fmt`
