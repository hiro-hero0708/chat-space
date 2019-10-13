    usersテーブル

|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|user_name|string|null:false |

### Association
- has_many :messages
- has_many :groups_user

messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string||
|group_id|integer|null: false ,foreign_key: true |
|user_id|integer|null: false,foreign_key: ture|

### Association
- belongs_to :user
- belongs_to :group

groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false|
|member|string||
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :groups_user
- has_many :messages

groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
