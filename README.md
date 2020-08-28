# README

## users table
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false, unique: true|
|password|string|null: false|
### Association
- has_many :users_groups
- has_many :messages, through: users_groups

## groups table
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|
### Association
- has_many :users_groups
- has_many :messages, through: users_groups

## users_groups
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

## messages
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|text||
|datetime|timestamp||
|user_id|integer|null:false, foreign_key: true|
|group_id|integer|null:false, foreign_key: true|
### Association
- has_many :user, through: :users_groups
- has_many :group, through: :users_groups
