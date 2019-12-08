# chat-space DB設計
## usersテーブル
|Column |Type |Option|
|-------|-----|------|
|email|string|null: false|
|password|integer|null: false|
|username|string|null: false|
### Association
- has_many :groups
- has_many :comments

## chatテーブル
|Column |Type|Option|
|-------|----|------|
|user_id|integer|null: false|
|group_id|integer|null: false|
|text|text|null: false|
|image|text||
### Association
- has_many :users
- has_many :groups
- belongs_to :user

## groupテーブル
|Column |Type|Option|
|-------|----|------|
|groupname|string|null: false|
|text|text|null: false|
### Association
- has_many :chats
- has_many :users

## group_userテーブル
|Colum |Type|Option|
|------|----|------|
|user_id|integer|null: false|
|group_id|integer|null: false|
### Association
- belongs_to :user
- belongs_to :group

## commentテーブル
|Colum |Type|Option|
|------|----|------|
|text|text|null: false|
|user_id|integer|null: false|
|group_id|integer|null: false|
### Association
- belongs_to :user
- belongs_to :group

