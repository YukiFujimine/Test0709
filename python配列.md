---
title: "Python配列"
tags: ""
---
```python
def is_leapyear(year:int)->(bool):
    if year%400==0:
        return True
    elif year%4 == 0 and year%100 != 0:
        return True
    else:
        return False

def leapyears(year:int)->(list):
    years=[]
    while len(years)<10:
        if is_leapyear(year):
            years.append(year)
        year+=1
    return years
    
year=int(input('西暦を入力してください'))
if is_leapyear(year):
    print('西暦{}年は、うるう年です'.format(year))
    print(leapyears(year))
else:
    print('西暦{}年は、うるう年ではありません'.format(year))
        
西暦を入力してください 2020
西暦2020年は、うるう年です
[2020, 2024, 2028, 2032, 2036, 2040, 2044, 2048, 2052, 2056]
```
