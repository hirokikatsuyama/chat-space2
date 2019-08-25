# README
# chat-space2

#Reason I make this application is for practice.

### Userテーブル
-has_many :groups ,through: :group_users
-has_many :group_users
-has_many :comments

|column   |type   |index|null  |unique|
|---------|-------|-----|------|------|
|name     |string |true |false |true  |
|password |string |false|false |false |

### Group_userテーブル(中間テーブル)
-belongs_to :user
-belongs_to :group

|column     |type   |index|null  |unique|foreign_key|
|-----------|-------|-----|------|------|-----------|
|group_id   |references|true |false |false |true       |
|user_id    |references|false|false |false |true       |

### Groupテーブル
-has_many :users,through: :group_users
-has_many :group_users
-has_many :comments

|column|type   |index|null  |unique|
|------|-------|-----|------|------|
|name  |string |false|false |true  |

### Commentテーブル
-belongs_to :user
-belongs_to :group

|column     |type   |index|null  |unique|foreign_key|
|-----------|-------|-----|------|------|-----------|
|user_id    |references|true |false |false |true       |
|group_id   |references|true |false |false |true       |
|comment    |text   |false|true  |false |false      |
|image      |string |false|true  |false |false      |

