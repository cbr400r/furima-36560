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
 - has_many :buyer

## sales テーブル

| Column           | Type       | Options    |
| ---------------- | ---------- | ---------- |
| image            | string     | null:false |
| item_name        | string     | null:false |
| item_contents    | string     | null:false |
| category         | text       | null:false |
| item_status      | text       | null:false |
| delivery_cost    | integer    | null:false |
| send_area        | integer    | null:false |
| send_day         | integer    | null:false |

### Association

 - belongs_to :users

## destinations テーブル

| Column         | Type       | Options    |
| -------------- | ---------- | ---------- |
| post_number    | string     | null:false |
| prefecture     | string     | null:false |
| city           | string     | null:false |
| address        | integer    | null:false |
| building_name  | string     |            |
| phone_number   | integer    | null:false |

### Association

 - belongs_to :users

 ## buyers テーブル

| Column         | Type       | Options    |
| -------------- | ---------- | ---------- |
| seller         | text       | null:false |
| category       | text       | null:false |
| item_status    | text       | null:false |
| delivery_cost  | text       | null:false |
| send_area      | text       | null:false |
| send_day       | text       | null:false |

### Association

 - belongs_to :users
