# アプリ名
RAMEN_REVIEW

# 概要
<br>ログインしていないユーザー:ラーメン店の一覧、レビューを見ることができる<br>
<br>ログインしているユーザー：ラーメン店の一覧、レビューを見る、書くことができる<br>



# 制作背景（意図）
自分自身まだまだjavascriptに対して知識が甘いことを自覚しているためjavascriptを使ったアプリを作り、知識を高めていきたいと思ったため。


# DEMO
#### トップページ
<p align="center">
  <img src="https://user-images.githubusercontent.com/72494683/101971196-eae8dd80-3c72-11eb-8c51-76e91927c681.png" width=70%><br>
</p>

#### 新規登録画面

<p align="center">
<img alt="新規登録画面" src="https://user-images.githubusercontent.com/72494683/102001246-1fbc6980-3d33-11eb-8689-8dbb9e9ead86.jpg" width=70%><br>
</p>

#### ログイン画面

<p align="center">
<img alt="ログイン画面" src="https://user-images.githubusercontent.com/72494683/102001262-6e6a0380-3d33-11eb-8d14-8cf8bc659e34.jpg" width=70%><br>
</p>

#### ラーメン店一覧

<p align="center">
<img alt="ラーメン店一覧" src="https://user-images.githubusercontent.com/72494683/102001749-d1aa6480-3d38-11eb-9a4b-99a0ef3728e1.png" width=70%><br>
</p>

#### レビュー投稿

<p align="center">
<img alt="レビュー投稿" src="https://user-images.githubusercontent.com/72494683/102001317-1ed80780-3d34-11eb-838b-550d304f0cce.jpg" width=70%><br>
</p>

#### レビュー一覧

<p align="center">
<img alt="レビュー一覧" src="https://user-images.githubusercontent.com/72494683/102001328-4dee7900-3d34-11eb-9b9b-fea8ed301716.jpg" width=70%><br>
  </p>

# 工夫したポイント
今までデータを投稿し、保管していましたが今回は元々データを存在させておくやり方を実践してみました。<br>
またレビューの星の部分をjavascriptで実装し、レビューの平均値を出すやり方も実装することができました。
## 使用した技術（開発環境）
HTML・CSS・Ruby・Ruby on Rails・JavaScript・GitHub 

## 課題や今後実装したい機能
レビューするサイトとしては少し味気ない感じなので、写真なども加えてより見やすくする必要があると感じています。<br>
<br>今後実装したい機能としては、google mapのAPIを導入することでより使いやすくなると感じている。<br>

# テーブル設計
## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| name     | string | null: false |
| email    | string | null: false |
| password | string | null: false |
### Association

- has_many :reviews
- has_many :ramen_shops

## reviews テーブル

| Column      | Type    | Options     |
| ------      | ------  | ----------- |
| user_id     |reference| null: false |
|ramen_shop_id|reference| null:false  |
|content      |string   | null:false  |
|score        |integer  | null:false  |


### Association

- belongs_to: user
- belongs_to: ramen_shop

## ramen_shops テーブル

| Column   | Type    | Options     |
| ------   | ------  | ----------- |
| name     | string  | null: false |



### Association

- belongs_to: user
- has_many: reviews


