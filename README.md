# README

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|username|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :chat
- has_many :users_group
- has_many :group,  through:  :users_grope

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|gropename|string|null: false|
|text|text||
### Association
- has_many :chat
- has_many :users_group
- has_many :users,  through:  :users_grope

## users_gropeテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|grope_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

## chatテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :users
- belongs_to :group