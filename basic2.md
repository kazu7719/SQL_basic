### SQLによるテーブル操作

## USE文
・・・どのデータベースを使用するのか指定するSQLの文
USE <database名>

## テーブルとカラムの作成
CREATE TABLE テーブル名　(カラム名1 カラム名1の型, カラム名2 カラム名2の型, ...);

rails db:migrateの実行の裏側では、このCREATE TABLEのSQLの文が動いていた

MySQLでの数値型、文字型名

INT・・・数字
VARCHAR(M)・・・最大M文字の文字列


## FROM句
・・・対象テーブルを指定する際に使用するSQL句

FROM <テーブル名>

SHOW columns FROM goods;


## ALTER文
・・・データベースやテーブルを編集できるSQL文。
カラム情報など更新できる。
ALTER TABLE文を実行すると、テーブルに対してカラムの追加や削除ができる

# ALTERでカラム情報の更新
ALTER TABLE <テーブル名>　操作

# カラムを一つだけ追加する場合
ALTER TABLE テーブル名　ADD カラム名　カラムの型;

# カラムを複数追加する場合
ALTER TABLE テーブル名　ADD (カラム名　カラムの型, ...);


## カラムの変更
ALTER TABLE テーブル名　CHANGE 古いカラム名　新しいカラム名　新しいカラムの型;


## カラムの削除
ALTER TABLE テーブル名　DROP カラム名;
