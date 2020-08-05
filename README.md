# README
# furima_27889 DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|
|email|string|null: false|
|password|string|null: false|
|first_name|string|null: false|
|family_name|string|null: false|
|first_name_kana|string|null: false|
|family_name_kana|string|null: false|
|birthday|date|null: false|
### Association
- has_many :purchase_conditions
- has_many :items
- has_many :comments

## itemsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|price|integer|null: false|
|introduction|text|null: false|
|exhibitor|string|null: false|
|category|string|null: false|
|item_condition|string|null: false|
|postage_type|string|null: false|
|prefecture_code|string|null: false|
|preparation_day|string|null: false|
|item_img|string|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to_active_hash :item_condition
- belongs_to_active_hash :postage_type
- belongs_to_active_hash :prefecture_code
- belongs_to_active_hash :preparation_day
- belong_to :user 
- has_one :purchase_conditions
- has_many :comments

## destinationsテーブル
|Column|Type|Options|
|------|----|-------|
|post_code|string|null: false|
|prefecture_code|string|null: false|
|city|string|null: false|
|house_number|string|null: false|
|building_name|string|
|phone_number|string|null: false|
|item_id|integer|null: false, foreign_key: true|
### Association
- belongs_to_active_hash :prefecture_code
- belong_to :item

## purchase_conditionsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|item_id|integer|null: false, foreign_key: true|
### Association
- belong_to :user 
- belong_to :item

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|comment|string|null: false|
|user_id|integer|null: false, foreign_key: true|
|item_id|integer|null: false, foreign_key: true|
### Association
- belong_to :user 
- belong_to :item

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
