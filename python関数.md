---
title: "Python関数"
tags: ""
---
```python
def analyze_score(sansu,kokugo,rika,syakai,eigo=None,*others):
    scores=[sansu,kokugo,rika,syakai,eigo]+list(others)
    for s in range(len(scores)):
        if s==None:
            scores.remove(s)
    print(scores)       
    max_score=max(scores)
    min_score=min(scores)
    avg_score=sum(scores)/len(scores)
    return[max_score,min_score,avg_score]

print(analyze_score(60,70,90,60,88,77,66))
[x,y,z]=analyze_score(60,70,90,60,88,77,66)
print('最大値{}、最小値{}、平均{}'.format(x,y,z))


[60, 70, 90, 60, 88, 77, 66]
[90, 60, 73.0]
[60, 70, 90, 60, 88, 77, 66]
最大値90、最小値60、平均73.0
```
