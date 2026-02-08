## JOIN句
・・・指定したテーブルのカラムに登録された値が一致するデータをもとに、各テーブルのレコードを結合できる

JOIN句はFROM句のあとに記述し、結合の対象となるテーブルを指定。
そして結合する元となるカラムを、ONの後に=で指定。

FROM <テーブル名1>
JOIN <テーブル名2> ON <テーブル名1.カラム名1> = <テーブル名2.カラム名2>

FROM shifts
JOIN users ON shifts.user_id = users.id
→shiftsテーブルのuser_idと、usersテーブルのidが一致する行を結合させる
例えばshiftsテーブルのuser_idが1の行と、usersテーブルのidが1の行を結合させる


FROM shifts s
JOIN users u ON s.user_id = u.id

## CONCAT観数
・・・複数の文字列を連結できる関数

CONCAT(文字列1, 文字列2, ...)

## GROUP BY句
・・・ある特定のデータをグループ化するために用いる句です。
グループ化をしたデータは他の関数などと組み合わせて、グループごとの平均値や総量などを集計できる

GROUP BY カラム名

## COUNT関数
・・・データの総量をカウントするための関数。カラムを指定することでそのカラムのデータ行数を指定できる。
また、GROUP BY句でグループ化されたデータに対して使用可能

SELECT COUNT(カラム名)

/* 5行あるデータのうち、2行分のnameカラムの値がNULLだった場合 */
SELECT COUNT(*) FROM users
/* → 実行結果は5が返る */

SELECT COUNT(name) FROM users
/* → 実行結果は3が返る */

## サブクエリ
・・・ある検索結果を使用して、別のSQL文を実行する仕組みのこと