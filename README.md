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
<img alt="新規登録画面" src="" width=70%><br>
</p>

#### ログイン画面

<p align="center">
<img alt="roguinn" src="" width=70%><br>
</p>

#### レシピ投稿画面

<p align="center">
<img alt="レシピ投稿画面" src="https://user-images.githubusercontent.com/72494683/100247459-b6400b00-2f7d-11eb-992a-27d323cd544a.png" width=70%><br>
</p>

#### レシピ編集

<p align="center">
<img alt="レシピ編集" src="https://user-images.githubusercontent.com/72494683/100244916-d15d4b80-2f7a-11eb-851e-5ad1c53cfef5.png" width=70%><br>
</p>

#### コメント、返信機能

<p align="center">
<img alt="コメント、返信機能" src="https://user-images.githubusercontent.com/72494683/100247176-64978080-2f7d-11eb-9439-6a08d0ea9565.png" width=70%><br>
  </p>
  
#### レシピ詳細ページ

<p align="center">
  
![レシピ詳細ページ](https://user-images.githubusercontent.com/72494683/100253014-f0141000-2f83-11eb-9fc8-2c8a59b3942e.gif)
  
 </p> 
 
#### いいね機能

![いいね機能](https://user-images.githubusercontent.com/72494683/100253157-1c2f9100-2f84-11eb-9433-ccaa656ccbbc.gif)<br>

# 工夫したポイント
気に入ったレシピに対してのいいね機能を、コメントに対しての返信機能は付けたてレシピを投稿した人、そのレシピを参考に作ってみた方との間をなるべく近くして、シェアということがしやすいようにしたいと思い実装したことが工夫した点になります。<br>
<br>また、背景色が単色であったりすると味気がない上に、少しでもアクセスしたときに好感を持ってもらい、またアクセスしてもらえるようにトップページのレイアウトには力を入れ、工夫をしました。<br>
## 使用した技術（開発環境）
HTML・CSS・Ruby・Ruby on Rails・JavaScript・GitHub 

## 課題や今後実装したい機能
課題は、返信機能がついてはいるのですが見にくかったり、実用的ではないため改良が必要だと感じています。<br>
<br>今後実装したい機能としては、検索機能やSNSとの連携ができるようにしてレシピの検索がしやすくなるように改良したり、新規登録時にSNSのアカウントで簡単に登録ができるようにして、より使いやすいように改良が必要だと思っています。<br>

# テーブル設計
## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| name     | string | null: false |
| email    | string | null: false |
| password | string | null: false |
### Association

- has_many :recipes
- has_many :comments
- has_many :goods

## recipe テーブル

| Column   | Type    | Options     |
| ------   | ------  | ----------- |
| title    | string  | null: false |
|user_id   |reference| null:false  |
|body      |text     | null:false  |


### Association

- belongs_to: user
- has_many :comments
- has_many :goods

## comments テーブル

| Column   | Type    | Options     |
| ------   | ------  | ----------- |
| text     | text    | null: false |
|recipe_id |reference|             |
|user_id   |reference|             |


### Association

- belongs_to: user
- belongs_to: recipe


## goods テーブル

| Column   | Type    | Options     |
| ------   | ------  | ----------- |
| user_id  |reference|             |
|recipe_id |reference|             |         

### Association
- belongs_to: user
