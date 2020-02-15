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

* ...# chat-space


## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
### Association
has_mamy messages
has_many groups


## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|message|text|null: false|
|imgae|string|
|user_id|integer|null: false, foreign_key: true|
### Association
belongs_to group
belongs_to user


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string||null: false|
|msessage_id|integer|null: false, foreign_key: true|
|users_id|integer|null: false, foreign_key: true|
### Association
has_many users
has_many messages


## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|messages_id|integer|null: false, foreign_key: true|
|groups_id|integer|null: false, foreign_key: true|
### Association
belongs_to group
belongs_to user