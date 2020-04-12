
## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true|
|email|string|null: false|
|password|string|null: false|

### Association
- has_many :groups, through: :groups_users
- has_many :group_users
- has_many :messages


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :users, through: :groups_users
- has_many :group_users
- has_many :messages

## messageテーブル

|Column|Type|Options|
|------|----|-------|
|body|string||
|image|text||
|group|references|null: false, foregin_key: true|
|user|references|null: false, foregin_key: true|

### Association
- belongs_to :group
- belongs_to :user
