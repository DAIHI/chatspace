# DB設計
## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :users, through: :groups_users
- has_many :messages

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|username|string|null: false|
|email|string|null: false|
|password|string|null: false|

### Association
- has_many :groups, through: :groups_users
- has_many :massages

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|text|text||
|image|string||
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
