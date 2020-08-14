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


## usersテーブル
|Column|Type|Option|
|------|----|------|
|user|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :groups

## groupsテーブル
|Column|Type|Option|
|------|----|------|
|group|text|null: false|
|user_id|null: false, foreign_key: true|
### Association
- belong_to :user
- has_many :tweets
- has_many :users, through: :groups_users

## tweetsテーブル
|Column|Type|Option|
|------|----|------|
|tweet|text|null: false|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group

## groups_usersテーブル
|Column|Type|Option|
|------|----|------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belong_to :group
- belong_to :user