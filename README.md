# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...




##usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|Email|string|null: false|

###association
- has_many :groups, through: :groups_users
- has_many :messages




##groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

###association
- has_many :users, through: :groups_users
- has_many :messages




##messagesテーブル

|Column|Type|Options|
|-----|----|--------|
|body|text|null: false|
|image|string|null: false|
|group|references|----|
|user|references|-----|

###association
- belongs_to :users
- belongs_to :groups




##groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

###association
- belongs_to :group
- belongs_to :user