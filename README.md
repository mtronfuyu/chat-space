## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false,
|email|string|null: false, unique: true|
|message_id|integer|foreign_key: true|
foreign_key: true|
|group_id|integer|foreign_key: true|

### Association
- has_many :groups_users
- has_many :groups, through: :groups_users
- has_many :messages

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|       |
|message_id|integer|foreign_key: true|
foreign_key: true|
|user_id|integer|foreign_key: true|

### Association
- has_many :groups_users
- has_many :users, through: :groups_users
- has_many :messages

## groups_usersテーブル
|Column|Ttpe|Options|
|------|----|-------|
|user_id|integer|foreign_key: true|
|group_id|integer|foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## messageテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|       |
|user_id|integer|foreign_key: true|
|group_id|integer|foreign_key: true|
|image|string|foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group
