## usersテーブル

|Cloumn|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|

### Association
- has_many :messages
- has_many :groups_users
- has_many :groups, through: :groups_users

## messagesテーブル

|Cloumn|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|null: false|
|users_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## group_usersテーブル

|Cloumn|Type|Options|
|------|----|-------|
|groups_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## groupsテーブル
|Cloumn|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :messages
- has_many :group_users
- has_many :users through::group_users
