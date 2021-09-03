# テーブル設計

## users テーブル

| Column                 | Type   | Options                  |
| ---------------------- | ------ | ------------------------ |
| nickname               | string | null:false               |
| email                  | string | null:false, unique: true |
| encrypted_password     | string | null:false               |
| last_name              | string | null:false               |
| first_name             | string | null:false               |
| last_name_kana         | string | null:false               |
| first_name_kana        | string | null:false               |
| birthday               | date   | null:false               |


### Association

 - has_many :sales
 - has_many :destinations
 - has_many :items
 - has_many :buyers

## sales テーブル

| Column           | Type       | Options    |
| ---------------- | ---------- | ---------- |
| image            | string     | null:false |
| item_name        | string     | null:false |
| item_contents    | string     | null:false |
| category         | integer    | null:false |
| item_status      | integer    | null:false |
| delivery_cost    | integer    | null:false |
| send_area        | integer    | null:false |
| send_day         | integer    | null:false |
| price            | integer    | null:false |
| commission       | integer    | null:false |
| profit           | integer    | null:false |
| user_id          | integer    | null:false, foreign_key: true |

### Association

 - belongs_to :user

## destinations テーブル

| Column         | Type         | Options    |
| -------------- | ------------ | ---------- |
| post_number    | string       | null:false |
| prefecture     | string       | null:false |
| city           | string       | null:false |
| address        | string       | null:false |
| building_name  | string       |            |
| phone_number   | string       | null:false |
| user_id        | references   | null:false, foreign_key: true |

### Association

 - belongs_to :user

 ## buyers テーブル

| Column         | Type       | Options                       |
| -------------- | ---------- | ----------------------------- |
| user_id        | references | null:false, foreign_key: true |
| sale_id        | references | null:false, foreign_key: true |
### Association

 - belongs_to :user
