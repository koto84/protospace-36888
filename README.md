# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| email              | string | null: false |
| encrypted_password | string | null: false |
| name               | string | null: false |
| profile            | string | null: false |
| occupation         | string | null: false |
| position           | string | null: false |

### Association

-has_many : prototypes
-has_many : comments

## prototypes テーブル

| Column       | Type   | Options                        |
| ------------ | ------ | ------------------------------ |
| title        | string | null: false                    |
| catch_copy   | string | null: false                    |
| concept      | string | null: false                    |
| user         | string | null: false, foreign_key: true |

### Association

-belongs_to : user
-has_many : comments


##  commentsテーブル

| Column       | Type       | Options                        |
| ------------ | ---------- | ------------------------------ |
| content      | string     | null: false                    |
| prototype    | references | null: false, foreign_key: true |
| user         | references | null: false, foreign_key: true |

### Association

-belongs_to : user
-belongs_to : prototypes
