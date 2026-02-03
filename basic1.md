## ActiveRecordメソッド
・・・モデルがテーブル操作に関して使用できるメソッドの総称
all
find
new 
save
create
destroy


## SQL
・・・SQLとはRDBの操作を行うための言語。
ActiveRecordなどのORMのメソッドは、SQLに変換するためテーブルの操作が可能

## SQLの命令について
・データを定義するDDL(テーブルの作成・削除)
・データを操作するDML(データを探す・登録・更新)
・データを制御するDCL(変更の確定・取消)

## DDLのできること
・CREATE(データベース・テーブル作成)
・ALTER(データベース・テーブル更新)
・DROP(データベース・テーブル削除)

##　DMLのできること
・INSERT(データの登録)
・UPDATE(データの更新)
・DELETE(データの削除)
・SELECT(データの検索)

## DCLのできること
・COMMIT(DB変更の確定)
・ROLLBACK(DBの変更の取り消し)
・GRANT(ユーザーに操作権限付与)
・REVOKE(ユーザーに操作権限無効化)

## SELECT文
・・・SQLの文法で、データベースからデータを取得する場合に使用

SELECT <取得したいデータ> FROM <テーブル名>;

## CREATE文

CREATE DATABASE <データベース名> ;

## SHOW文
・・・データベースやテーブルを一覧表示できるSQLの文

SHOW DATABASES;

## DROP文
・・・データベースやテーブルを削除できるSQLの文

DROP DATABASE 《データベース名》;