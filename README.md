# README

## userテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :chats
- has_many :users_groups
- has_many :groups,  through:  :users_groups

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :chats
- has_many :users_groups
- has_many :users,  through:  :users_groups

## users_gropesテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

## chatテーブル
|Column|Type|Options|
|------|----|-------|
|text|text||
|image|text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group