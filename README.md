# README

## users table
|Column|Type|Options|
|------|----|-------|
|username|string|null: false|
|email|string|null: false, unique: true|
|password|string|null: false|
### Association
- has_many :users_groups

## groups table
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false, unique: true|
### Association
- has_many :users_groups

## users_groups
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true, add_index: true|
|group_id|integer|null: false, foreign_key: true, add_index: true|
### Association
- belongs_to :user
- belongs_to :group

## messages
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|text||
|datetime|timestamp||
|user_id|integer|null:false, foreign_key: true|
|group_id|integer|null:false, foreign_key: true|
### Association
- has_many :users, through: :users_groups
- has_many :groups, through: :users_groups
