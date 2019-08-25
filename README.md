# README
# chat-space2

#Reason I make this application is for practice.

## Userテーブル
|column   |type   |index|null  |unique|
|---------|-------|-----|------|------|
|name     |string |true |false |true  |
|password |string |false|false |false |
### Association
--has_many :groups ,through: :group_users
--has_many :group_users
--has_many :comments

## Group_userテーブル(中間テーブル)
|column     |type   |index|null  |unique|foreign_key|
|-----------|-------|-----|------|------|-----------|
|group_id   |references|true |false |false |true       |
|user_id    |references|false|false |false |true       |
### Association
-belongs_to :user
-belongs_to :group


## Groupテーブル
|column|type   |index|null  |unique|
|------|-------|-----|------|------|
|name  |string |false|false |true  |
### Association
-has_many :users,through: :group_users
-has_many :group_users
-has_many :comments


### Commentテーブル
|column     |type   |index|null  |unique|foreign_key|
|-----------|-------|-----|------|------|-----------|
|user_id    |references|true |false |false |true       |
|group_id   |references|true |false |false |true       |
|comment    |text   |false|true  |false |false      |
|image      |string |false|true  |false |false      |
### Association
-belongs_to :user
-belongs_to :group



