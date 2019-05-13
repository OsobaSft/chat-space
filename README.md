# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|nickname|varchar|null: false|
|email|varchar|null: false|
|password|char|null: false| 

### Association
- has_many :groups
- has_many :messages
- has_many :images

## groups テーブル

|Column|Type|Options|
|------|----|-------|
|group_name|varchar|null: false|

### Association
- belongs_to :user

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|body|text|null: false|
|image_id|null: true, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group
- has_many :images


## imagesテーブル

|Column|Type|Options|
|------|----|-------|
|message_id|null: false, foreign_key: true|
|image|image|null: false|


### Association
- belongs_to :message




