# README

Things you may want to cover:
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
|user_id|integer|null:false, foreign_key: true|
### Association
- has_many :users_groups

## messages
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|text||
|datetime|timestamp||
|user_id|integer|null:false, foreign_key: true|
|group_id|integer|null:false, foreign_key: true|
### Association
- has_many :user, through: :users_groups
- has_many :group, through: :users_groups

## users_groups
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true, add_index: true|
|group_id|integer|null: false, foreign_key: true, add_index: true|
### Association
- belongs_to :user
- belongs_to :group
