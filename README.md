# README

# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| nickname           | string | null: false |
| email              | string | null: false |
| family_name        | string | null: false |
| first_name         | string | null: false |
| family_name_kana   | string | null: false |
| first_name_kana    | string | null: false |
| birth_year         | string | null: false |
| birth_month        | string | null: false |
| birth_day          | string | null: false |
| password           | string | null: false |

### Association

- has_many :items
- has_many :orders

## items テーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| name      | string     | null: false                    |
| category  | string     | null: false                    |
| price     | integer    | null: false                    |
| text      | text       | null: false                    |
| condition | integer    | null: false                    |
| status    | integer    | null: false                    |
| user_id   | references | null: false, foreign_key: true |
| order_id  | references | null: false, foreign_key: true |


### Association
- belongs_to :users
- has_one :orders

## orders テーブル
| Column   | Type       | Options                        |
| -------- | ---------- | ------------------------------ |
| user_id  | references | null: false, foreign_key: true |
| item_id  | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- belongs_to :item

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
