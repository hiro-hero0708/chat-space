DB design

users table

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|

### Association
- has_many: :messages
- has_many: groups, through: :groups_users

messages table

|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

groups table

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|


### Association
- has_many :messages
- has_many :members
- has_many :groups_users
- has_many :users, through: :groups_users

groups_users table

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
