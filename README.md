# README
### usersテーブル
| Column    | Type   | Options     |
| --------- | ------ | ----------- |
| nickname  | string | null: false |
| email     | string | null: false |
| password  | string | null: false |
| lastname  | string | null: false |
| firstname | string | null: false |

### Association
- has_many :users_rooms
- has_many :rooms, through: :users_rooms
- has_many :messages

### roomsテーブル
| Column | Type   | Options     |
| ------ | ------ | ----------- |
| name   | string | null: false |

### Association
- has_many :users_rooms
- has_many :users, through: :users_rooms
- has_many :messages

### user_roomsテーブル
| Column | Type       | Option                         |
| ------ | ---------- | ------------------------------ |
| user   | references | null: false, foreign_key: true |
| room   | references | null: false, foreign_key: true |

### Association
- has_many :users
- has_many :rooms

### messagesテーブル
| Column  | Type       | Option                         |
| ------- | ---------- | ------------------------------ |
| content | text       |                                | 
| user    | references | null: false, foreign_key: true |
| room    | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- belongs_to :room