# README
# chat-space2

#Reason I make this application is for practice.

## Userテーブル
|column   |type   |option|
|---------|-------|-----|
|name     |string |index: true, null: false, unique: true|
|password |string |index: false,null: false,unique: false|
### Association
- has_many :groups ,through: :group_users
- has_many :group_users
- has_many :comments

## Group_userテーブル(中間テーブル)
|column     |type   |option|
|-----------|-------|------|
|group_id   |references|index: true,null: false,unique: false,forigen_key: true|
|user_id    |references|index: false,null: false,unique: false,forigen_key: true|
### Association
- belongs_to :user
- belongs_to :group


## Groupテーブル
|column|type   |option|
|------|-------|------|
|name  |string |index: false,null: false,unique: true|
### Association
- has_many :users,through: :group_users
- has_many :group_users
- has_many :comments


### Commentテーブル
|column     |type   |option|
|-----------|-------|------|
|user_id    |references|index: true,null: false,unique: false,forigen_key: true|
|group_id   |references|index: true,null: false,unique: false,forigen_key: true|
|comment    |text   |index: false,null: true,unique: false,forigen_key: false|
|image      |string |index: false,null: true,unique: false,forigen_key: false|
### Association
- belongs_to :user
- belongs_to :group



