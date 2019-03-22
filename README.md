# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|integer|null: false|
|mail|varchar|null: false|

### Association
- has_many :messages
- has_many :groups through: :members
- has_many :members

----------------------------


## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false|
|text|text|null: false|
|image|text|null: false|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user



---------------------------


## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|integer|null: false|


### Association
- has_many :messages
- has_many :users through: :members
- has_many :members


-------------------------------------

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
