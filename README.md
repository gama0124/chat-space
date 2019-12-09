# chat-space DB設計
## usersテーブル
|Column |Type |Option|
|-------|-----|------|
|email|string|null: false|
|password|integer|null: false|
|name|string|null: false ,index:true|
### Association
- has_many :groups ,through: :groups_users
- has_many :groups_users
- has_many :comments

## chatテーブル
|Column |Type|Option|
|-------|----|------|
|user_id|references|null: false ,foreign_key:true|
|group_id|references|null: false ,foreign_key:true|
|text|text||
|image|text||
### Association
- belongs_to :groups
- belongs_to :user

## groupテーブル
|Column |Type|Option|
|-------|----|------|
|name|string|null: false|
### Association
- has_many :users ,through: :groups_users
- has_many :groups_users
- has_many :chats



## groups_usersテーブル
|Colum |Type|Option|
|------|----|------|
|user_id|references|null: false ,foreign_key:true|
|group_id|references|null: false ,foreign_key:true|
### Association
- belongs_to :user
- belongs_to :group


