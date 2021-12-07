# アプリケーション名
【作業用】DQX 占い師デッキレシピ集

# アプリケーション概要
※こちらは追記機能を実装するための作業用リポジトリとなります。
アプリケーションの概要に関しては以下をご参照ください。  
https://github.com/murataholic/tarot_deck
# URL
# テスト用アカウント
# 利用方法
# 目指した課題解決
# 洗い出した要件
| 機能  | 目的 | 詳細  | ストーリー |
| ---- | ---- | ---- | -------- |

# 実装した機能
# 工夫した機能
# 実装予定の機能
- 記事編集時（ページ遷移後）にタロット画像をあらかじめ表示させる
- 記事投稿時のタロット選択を簡略化させる
- トップページ（記事一覧ページ）の修正（※記事投稿数増加への対応）
- SNS認証
- コメント機能

# ローカルでの動作方法

# 開発環境
- フロントエンド：HTML/CSS/JavaScript/jQuery
- バックエンド：Ruby on Rails(6.0.0)/Ruby(2.6.5)/JavaScript
- テスト：RSpec
- Linter：Rubocop
- データベース：MySQL(5.6.50)/Sequel Pro
- インフラ：Heroku
- タスク管理：GitHub

# データベース設計
## ER図
[![Image from Gyazo](https://i.gyazo.com/ea143a4fe20086a112a0a1b3bff81716.png)](https://gyazo.com/ea143a4fe20086a112a0a1b3bff81716)

## 画面遷移図
[![Image from Gyazo](https://i.gyazo.com/5ad1eed07f84cfa1fc483f1516376fb9.png)](https://gyazo.com/5ad1eed07f84cfa1fc483f1516376fb9)

## テーブル設計

### users テーブル

| Column              | Type   | Options                   |
| --------------------| ------ | ------------------------- |
| email               | string | null: false, unique: true |
| encrypted_password  | string | null: false               |
| nickname            | string | null: false               |

#### Association

- has_many :articles
- has_many :nices

### articles テーブル

| Column    | Type       | Options                        | 
| --------- | ---------- | -------------------------------|
| user      | references | null: false, foreign_key: true |
| title     | string     | null: false                    |
| genre_id  | integer    | null: false                    |
| text      | text       | null: false                    |
| arc1_id   | integer    | null: false                    |
| arc2_id   | integer    | null: false                    |
| arc3_id   | integer    | null: false                    |
| arc4_id   | integer    | null: false                    |
| arc5_id   | integer    | null: false                    |
| arc6_id   | integer    | null: false                    |
| arc7_id   | integer    | null: false                    |
| arc8_id   | integer    | null: false                    |
| arc9_id   | integer    | null: false                    |
| arc10_id  | integer    | null: false                    |
| arc11_id  | integer    | null: false                    |
| arc12_id  | integer    | null: false                    |
| arc13_id  | integer    | null: false                    |
| arc14_id  | integer    | null: false                    |
| arc15_id  | integer    | null: false                    |
| arc16_id  | integer    | null: false                    |
| arc17_id  | integer    | null: false                    |
| arc18_id  | integer    | null: false                    |
| arc19_id  | integer    | null: false                    |
| arc20_id  | integer    | null: false                    |
| mons1_id  | integer    | null: false                    |
| mons2_id  | integer    | null: false                    |
| mons3_id  | integer    | null: false                    |
| mons4_id  | integer    | null: false                    |
| mons5_id  | integer    | null: false                    |
| mons6_id  | integer    | null: false                    |
| mons7_id  | integer    | null: false                    |
| mons8_id  | integer    | null: false                    |
| mons9_id  | integer    | null: false                    |
| mons10_id | integer    | null: false                    |
| mons11_id | integer    | null: false                    |
| mons12_id | integer    | null: false                    |
| mons13_id | integer    | null: false                    |
| mons14_id | integer    | null: false                    |
| mons15_id | integer    | null: false                    |
| mons16_id | integer    | null: false                    |
| mons17_id | integer    | null: false                    |
| mons18_id | integer    | null: false                    |
| mons19_id | integer    | null: false                    |
| mons20_id | integer    | null: false                    |

#### Association

- belongs_to :user
- has_many :nices

### nices テーブル

| Column    | Type       | Options                        | 
| --------- | ---------- | -------------------------------|
| user      | references | null: false, foreign_key: true |
| article   | references | null: false, foreign_key: true |

#### Association

- belongs_to :user
- belongs_to :article