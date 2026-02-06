## SQLの命令

・データを定義するDDL
・データを操作するDML
・データを制御するDCL


## DDL
CREATE・・・データベースやテーブルの作成
ALTER・・・データベースやテーブルの更新
DROP・・・データベースやテーブルの削除

# CREATE

CREATE DATABASE <データベース名>;

# SHOW
・・・データベースやテーブルを一覧表示

SHOW DATABASES

# DROP

DROP DATABASE <データベース名>;

# USE
・・・どのデータベースを使用するのか指定

USE <データベース名>;

# テーブルとカラムの作成

CREATE TABLE テーブル名 (カラム名1 カラム名の型, カラム名2 カラム名2の型,..);

カラムの型
・INT・・・数字
・VARCHAR(M)・・・最大M文字の文字列


CREATE TABLE goods (id INT, name VARCHAR(255));

# FROM句
・・・対象となるテーブルを指定する際に使用

SHOW columns FROM <テーブル名>;
