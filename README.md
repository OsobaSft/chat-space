# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|

### Association
- has_many :groups
- has_many :messages
- has_many :images

## groups テーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- belongs_to :user
- has_many :messages

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- has_many :users

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|
|body|text|null: true|
|image|image|null: true|

### Association
- belongs_to :user
- belongs_to :group
- has_many :images




