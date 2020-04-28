# README

## usersテーブル
| Type   | Column             | Options                               |
| ------ | ------------------ | ------------------------------------- |
| string | name               | null: false                           |
| string | email              | null: false, unique:true, default: "" |
| string | encrypted_password | null: false,              default: "" |
|        |                    |                                       |

### Association
- has_many: notes
- has_many: comments

---

## notesテーブル
| Type   | Column       | Options     |
| ------ | ------------ | ----------- |
| string | Name         | null: false |
| string | title        | null: false |
| string | text1        | null: false |
| string | text2        |             |
| string | text3        |             |
| string | text4        |             |
| string | text5        |             |
| string | text6        |             |
| text   | introduction | null: false |
|        |              |             |

### Association
- belongs_to: user
- has_many :note_tags
- has_many :tags, through: :note_tags
- has_many: comments

---

## tagsテーブル
| Type       | Column          | Options     |
| ---------- | --------------- | ----------- |
| references | name            | null: false |
|            |                 |             |

### Association
- has_many :note_tags
- has_many :notes, through: :note_tags

---

## note_tagsテーブル
| Type       | Column          | Options     |
| ---------- | --------------- | ----------- |
| references | note            | null: false |
| references | tag             | null: false |
|            |                 |             |

### Association
- belongs_to :note
- belongs_to :tag

---

## commentsテーブル
| Type       | Column  | Options     |
| ---------- | ------- | ----------- |
| references | user    | null: false |
| references | note    | null: false |
| text       | comment | null: false |
|            |         |             |

### Association

- belongs_to: user
- belongs_to: item

---
