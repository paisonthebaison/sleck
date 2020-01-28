# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

## users table
| Column | Type | Options |
| ------ | ---- | --------|
|username|string|null: false|
|email|string|null: false|
|password|string|null: false|

### Association
- has_many :groups through groups_users
- has_many :chats

## groups table
| Column | Type | Options |
| ------ | ---- | --------|
|user_id|integer|null: false, foreign_key: true|
|group_name|string|null: false|

### Association
- has_many :users through groups_users
- has_many :chats

## groups_users table
| Column | Type | Options |
| ------ | ---- | --------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Asociation
- has_many :users
- has_many :groups

## Chats table
| Column | Type | Options |
| ------ | ---- | --------|
|image|text| |
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
