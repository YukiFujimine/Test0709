---
title: "document.querySelector"
tags: ""
---
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>計算プログラム</title>
  </head>
  <body>
    <h1>計算プログラム</h1>
  
    <input type="number" id="num1"></input><br>
    <input type="number" id="num2"></input>
    <button>calc</button>
   <p></p>
  
    <script>
      let num1=document.querySelector('#num1');	/*()内の部品がある住所を変数に代入*/
      let num2=document.querySelector('#num2');
      let btn=document.querySelector('button');
      let result=document.querySelector('p');
      btn.addEventListener('click',()=>{
        result.innerText=`${num1.value}+${num2.value}=${parseInt(num1.value)+parseInt(num2.value)}`;
      });
    </script>
  </body>
</html>

```
