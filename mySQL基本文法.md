---
title: "基本文法"
tags: ""
---
○ データベース

fruitsApp
を作成せよ。文字コードはutf8とすること。

    CREATE DATABASE fruitsApp DEFAULT CHARACTER SET utf8

○ fruitsAppにfruitsテーブルを以下の仕様で作成せよ

###### id 整数　主キー　自動連番

###### name 可変長文字列(30) NOTNULL制約

###### price int

###### updated 日付

    CREATE TABLE fruits(
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(30) NOT NULL,
    price INT,
    updated DATE
    )

○ fruitsテーブルに以下の商品を登録せよ

###### みかん,100円,2020-02-12

###### ばなな,50円,2020-02-12

###### りんご,150円,2020-02-13

###### ナシ,80円,2020-02-15

###### パイン,200円,2020-02-15

###### いちご,300円,2020-02-15

    INSERT INTO fruits(name,price,updated)
    VALUES('みかん',100,'2020-02-12'),
    ('ばなな',50,'2020-02-12'),
    ('りんご',150,'2020-02-13'),
    ('ナシ',80,'2020-02-15'),
    ('パイン',200,'2020-02-15'),
    ('いちご',300,'2020-02-15')

○ fruitsテーブルから、名前、値段の一覧を取得する。

    SELECT name,price FROM fruits

○ fruitsテーブルに以下のデータを追加する
	洋ナシ,220円

    INSERT INTO fruits(name,price) VALUES('洋ナシ',220)

○ fruitsテーブルから、IDが「3]のデータを抽出する。

    SELECT * FROM fruits WHERE id=3

○ fruitsテーブルから、登録日が2020-02-13以前のデータについて
 商品名の一覧を抽出する。

    SELECT name,updated FROM fruits WHERE updated<='2020-02-13'

○ fruitsテーブルから、価格が100円以上200円以下の商品を、名前、価格、の一覧で抽出する。

    SELECT name,price FROM fruits WHERE price>=100 AND price<=200

○ fruitsテーブルから、日付が2020-02-15でない商品を、名前、価格、の一覧で抽出する。

    SELECT name,price FROM fruits WHERE updated<>'20200215'

○ すべての商品を10円値上げせよ。

    UPDATE fruits SET price=price+10

○ 名前にナシが含まれる商品を名前、価格、の一覧で抽出する。

    SELECT name,price FROM fruits WHERE name LIKE '%ナシ%'

○ 日付データがnullの項目を商品名の一覧で抽出する。

    SELECT name FROM fruits WHERE updated IS NULL

○	一番高い商品の名前、価格を出力する。

    SELECT name,price FROM fruits ORDER BY price DESC LIMIT 1

○ パインのデータを削除する。

    DELETE FROM fruits WHERE name='パイン'

○ すべてのデータを\*を使って一覧表示せよ

    SELECT * FROM fruits
