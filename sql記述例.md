---
title: "SQL記述例"
tags: ""
---
MySQL(RPG 1-40)

Level1

1.  SELECT \* FROM `パーティー`
2.  SELECT 名称 AS なまえ,hp AS 現在のHP,mp AS 現在のMP FROM パーティー
3.  SELECT \* FROM `イベント`
4.  SELECT イベント番号 AS 番号,イベント名称 AS 場面 FROM イベント
5.  INSERT INTO パーティー(id,名称,職業コード,hp,mp) VALUES('A01','スガワラ','21',131,232), ('A02','オーエ','10',156,84), ('A03','イズミ','20',84,190)

Level2

6.  SELECT \* FROM パーティー WHERE id='C02'
7.  UPDATE パーティー SET hp=120 WHERE id='A01'
8.  SELECT id,名称,hp FROM パーティー WHERE hp&lt;100
9.  SELECT id,名称,mp FROM パーティー WHERE mp>=100
10. SELECT イベント番号,イベント名称,タイプ FROM イベント WHERE タイプ&lt;>'3'
11. SELECT イベント番号,イベント名称 FROM イベント WHERE イベント番号&lt;=5
12. SELECT イベント番号,イベント名称 FROM イベント WHERE イベント番号>20
13. SELECT イベント番号,イベント名称 FROM イベント WHERE 前提イベント番号 IS null
14. SELECT イベント番号,イベント名称,後続イベント番号 FROM イベント WHERE 後続イベント番号 IS NOT null
15. UPDATE パーティー SET 状態コード='眠り' WHERE 名称 LIKE '%ミ%'
16. SELECT id,名称,hp FROM パーティー WHERE hp BETWEEN 120 AND 160
17. SELECT 名称,職業コード FROM パーティー WHERE 職業コード IN('01','10','11')
18. SELECT 名称,状態コード FROM パーティー WHERE 状態コード IS null || 状態コード NOT IN('異常なし','気絶')
19. SELECT \* FROM パーティー WHERE hp>100 AND mp>100
20. SELECT \* FROM パーティー WHERE substring(id,1,1)='A' AND substring(職業コード,1,1)='2'
21. SELECT \* FROM イベント WHERE タイプ='1' AND 前提イベント番号 IS NOT null AND 後続イベント番号 IS NOT null
22. Id,イベント番号

Level3

23. SELECT 状態コード FROM パーティー GROUP BY 状態コード
24. SELECT id,名称 FROM パーティー ORDER BY id ASC
25. SELECT 名称,職業コード FROM パーティー ORDER BY 名称 DESC
26. SELECT 名称,hp,状態コード FROM パーティー ORDER BY 状態コード ASC,id DESC
27. SELECT タイプ,イベント番号,イベント名称,前提イベント番号,後続イベント番号 FROM イベント ORDER BY 1 ASC,2 ASC
28. SELECT \* FROM パーティー ORDER BY hp DESC LIMIT 3
29. SELECT \* FROM パーティー ORDER BY mp DESC LIMIT 1 OFFSET 2
30. SELECT CASE substring(職業コード,1,1)WHEN '1' THEN '[S]' WHEN '2' THEN '[M]' ELSE '[A]' END AS 職業区分,職業コード,id,名称 FROM パーティー ORDER BY 職業コード ASC
31. SELECT イベント番号 FROM イベント
    WHERE イベント番号 NOT IN(SELECT イベント番号 FROM 経験イベント WHERE イベント.イベント番号=経験イベント.イベント番号)
    ORDER BY イベント番号 ASC
32. SELECT イベント番号 FROM イベント WHERE イベント番号 IN(SELECT イベント番号 FROM 経験イベント WHERE クリア区分='1') AND タイプ = '2'

Level4

33. SELECT 名称 AS なまえ,hp AS 現在のHP, CASE WHEN 職業コード IN('11','21') THEN (hp+50) ELSE hp END AS 装備後のHP FROM パーティー
34. UPDATE パーティー SET mp=mp+20 WHERE id IN('A01' ,'A03')
35. SELECT 名称 AS なまえ,hp AS 現在のHP,hp\*2 AS 予想されるダメージ FROM パーティー WHERE 職業コード='11'
36. SELECT 名称 AS なまえ,concat(hp,'/',mp) AS HPとMP,コード名称 AS ステータス FROM パーティー AS p LEFT JOIN (SELECT \* FROM コード WHERE コード種別=2) AS c ON p.状態コード = c.コード値 WHERE c.コード名称&lt;>'異常なし' OR p.状態コード IS null
37. SELECT イベント番号,イベント名称,
    CASE WHEN タイプ='1' THEN '強制'
    WHEN タイプ='2' THEN 'フリー'
    WHEN タイプ='3' THEN '特殊' END AS タイプ,
    CASE WHEN イベント番号 BETWEEN 1 AND 10 THEN '序盤'
    WHEN イベント番号 BETWEEN 11 AND 17 THEN '中盤'
    ELSE '終盤' END AS 発生時期 FROM イベント
38. SELECT 名称 AS なまえ,hp AS 現在のHP,char_length(名称)\*10 AS 予想ダメージ FROM パーティー
39. UPDATE パーティー SET 状態コード='04'
    WHERE hp%4=0 OR mp%4=0
40. SELECT floor(777-(777\*0.3)) AS 支払った金額
