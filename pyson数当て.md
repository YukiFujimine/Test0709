---
title: "Pyson数当て"
tags: ""
---
```python
import random

def check(prediction,answer):
    hit,blow=0,0
    for i in range(len(prediction)):
        for j in range(len(answer)):
            if prediction[i]==answer[j]:
                if i==j:
                    hit+=1
                else:
                    blow+=1  
    return hit,blow
    
print('数当てゲームを始めます。3桁の数を当ててください！カンマ区切りで入力>>')
answer=[]
for i in range(3):
    answer.append(random.randint(0,9))

#print(answer)

while(True):
    prediction=list(input('カンマ区切りで入力>>').split(','))
    for i in range(len(prediction)):
        prediction[i]=int(prediction[i])
    
    if len(prediction)!=len(answer):
        print('正解は{}でした'.format(answer))
        break
    elif prediction==answer:
        print('正解！！')
        break
    else:
        hit,blow=check(prediction,answer)
        print('{}hit,{}blow'.format(hit,blow))
        
```
