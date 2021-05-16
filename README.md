# テーブル設計

## usersテーブル

| Column      | Type    | Options     |
| ----------  | ------  | ----------  |
| email       | string  | NOT NULL    |
| password    | string  | NOT NULL    |
| name        | string  | NOT NULL    |
| profile     | string  | NOT NULL    |
| occupation  | string  | NOT NULL    |
| position    | string  | NOT NULL    |

### Association

- has_many  :prototypes
- has_many  :comments 

## prototypes

| Column      | Type          | Options           |
| ------      | ------        | ----------        |
| title       | string        | NOT NULL          |
| catch_copy  | text          | NOT NULL          |
| concept     | text          | NOT NULL          |
| image       | ActiveStorage |                   |
| user        | references    | foreign_key: true |

### Association

- belongs_to :users
- has_many  :comments

## comments
  
| Column      | Type          | Options           |
| ------      | ------        | ----------        |
| text        | text          | NOT NULL          |
| user        | references    | foreign_key: true |
| prototype   | references    | foreign_key: true |

### Association

- belongs_to :users
- belongs_to :prototypes