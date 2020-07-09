---
title: "Python入力と出力例"
tags: ""
---
```python
num=list(input('カンマ区切りで数値を入力>>').split(','))
max(num)

数値を入力>> 5,3,9
'9'

from math import pi

for i in range(5):
    print(int(round(pi)) if i==0 else round(pi,i))
    
3
3.1
3.14
3.142
3.1416
```
