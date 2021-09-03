# テーブル設計

## users テーブル

| Column                 | Type   | Options                  |
| ---------------------- | ------ | ------------------------ |
| nickname               | string | null:false               |
| email                  | string | null:false, unique: true |
| password               | string | null:false               |
| encrypted_password     | string | null:false               |
| last_name              | string | null:false               |
| first_name             | string | null:false               |
| last_name_kana         | string | null:false               |
| first_name_kana        | string | null:false               |
| birthday               | string | null:false               |


### Association

 - has_many :sales
 - has_many :destinations
 - has_many :items
 - has_one :cards


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

 ## items テーブル

| Column        | Type       | Options    |
| ------------- | ---------- | ---------- |
| product_name  | text       | null:false |
| price         | integer    | null:false |
| category      | string     | null:false |
| seller        | integer    | null:false |

### Association

 - belongs_to :users

 ## cards テーブル

| Column         | Type       | Options    |
| -------------- | ---------- | ---------- |
| card_number    | integer    | null:false |
| card_period    | integer    | null:false |
| security_card  | integer    | null:false |

### Association

 - belongs_to :users
