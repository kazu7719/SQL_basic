## ALTER文
・・・データベースやテーブルを編集

# ALTERでカラム情報の更新
ALTER TABLE <テーブル名> 操作

# カラムを一つだけ追加する場合
ALTER TABLE テーブル名　ADD カラム名　カラムの型;

# カラムを複数追加する場合
ALTER TABLE テーブル名　ADD (カラム名　カラムの型, ...);

ALTER TABLE goods ADD (price int, zaiko int);

# ALTERでカラムを変更
ALTER TABLE テーブル名　CHANGE 古いカラム名　新しいカラム名 新しいカラムの型;

ALTER TABLE goods CHANGE zaiko stock int;

# ALTERでカラムを削除
ALTER TABLE テーブル名　DROP カラム名;

ALTER TABLE goods DROP stock;

### DML
・・・データ操作のSQL。登録、更新、削除、検索が該当

## データの登録

# SELECT文
・・・データの取得で使用

SELECT <カラム名>　FROM <テーブル名>

全てのカラムデータを取得する場合
SELECT * FROM <テーブル名>

# INSERT文
・・・テーブルにデータを登録する

全てのカラムに値を入れる場合
INSERT INTO <テーブル名> VALUES(値1,値2, 値3);

特定のカラムのみに値を入れる場合
INSERT INTO テーブル名(カラム名1, カラム名2) VALUES(値1, 値2);


## データの更新

# UPDATE文
・・・データを更新

UPDATE <テーブル名> SET <変更内容>　WHERE <条件> ;

UPDATE goods SET price = 100 WHERE id = 2;

## データの削除

# DELETE文
・・・データを削除

DELETE FROM <テーブル名>　WHERE <条件>　;

DELETE FROM goods WHERE id = 2;
