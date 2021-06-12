#　テーブル設計

## users　テーブル

| Column       | Type   | Options     |
|--------------|--------|-------------|
| email        | string | null: false |
| password     | string | null: false |
| name         | text   | null: false |
| profile      | text   | null: false |
| occupation   | text   | null: false |
| position     | text   | null: false |

## Association

- has_many :prototypes
- has_many :comments

## comments テーブル

| Column    | Type       | Options     |
|-----------|------------|-------------|
| text      | text       | null: false |
| user      | references |             |
| prototype | references |             |

## Association

- belongs_to :users
- belongs_to :prototypes

## prototypes テーブル

| Column     | Type          | Options     |
|------------|---------------|-------------|
| title      | string        | null: false |
| catch_copy | text          | null: false |
| concept    | text          | null: false |
| user       | references    |             |

## Association

- has_many :comments
- belongs_tp :users