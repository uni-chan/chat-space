# README

## users table
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true, unique: true|
|email|string|null: false, unique: true|
|password|string|null: false|
### Association
- has_many :groups, through: :users_groups
- has_many :messages
- has_many :users_groups

## groups table
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :users, through: :users_groups
- has_many :messages
- has_many :users_groups

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
- belongs_to :user
- belongs_to :group