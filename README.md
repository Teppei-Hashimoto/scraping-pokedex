
# 環境構築
## ツール
+ Anaconda
+ JupyterLab
+ MongoDB
## パッケージ・ライブラリ
+ requests
+ BeautifulSoup
+ pandas
+ pickle
+ pymongo
# ファイルの説明
## 実行用ファイル
### attackdex.ipynb
技一覧のスクレイピングおよびCSV出力に使用
### pokedex.ipynb
ポケモン一覧のスクレイピングおよびMongoDBへの格納に使用
### create_text.ipynb
ポケモンと技データから本文の生成に使用
## 参照用ファイル（主要なもの）
### type.csv
タイプに関するデータ
### attackdex.csv
全世代の技一覧データ
### holditemdex.csv
野生のポケモンが持っているアイテムに関するデータ
※ 一部取得できていないアイテムもあるようです
### all_gen_pokemon_urls.pkl
ポケモンごとに取得元ページのURL一覧をまとめているデータ
### egg_groups_name.pkl
たまごグループに関するデータ
### pokedex_name_list.pkl
ポケモン英語名の一覧データ
# MongoDB関連
スクレイピングで取得したポケモンデータを一度ローカルのMongoDBに格納する形を取っています。
## 使い方
MongoDBをインストール済みの環境を用意してください。
### MongoDBの起動と停止
MacOSの場合
```
起動
$ brew services start mongo-community

停止
$ brew services stop mongo-community
```
### mongoシェルの起動と停止
```
起動
$ mongo

停止
> exit
```
### データベースの作成
```
データベースの作成 または 選択 < pokemon >
> use pokemon

選択しているデータベースの表示
> db

データベースの一覧取得
> show dbs
```
### コレクションの作成
```
コレクションの作成 < all_gen_pokedex >
> use pokemon
> db.createCollection('all_gen_pokedex');

コレクションの作成 < pokedex >
> db.createCollection('pokedex');

コレクションの一覧取得
> show collections
```
### ドキュメントの取得と削除
```
ドキュメントの全件取得
> db.all_gen_pokedex.find();

ドキュメントの全件削除
> db.all_gen_pokedex.remove();
```
