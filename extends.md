---
title: "extends"
tags: ""
---
```java
public class SuperHero extends Hero{
    boolean flying;

    public void fly(){
        this.flying=true;
        System.out.println("飛び上がった!");
    }
    public void land(){
        this.flying=false;
        System.out.println("着地した!");
    }
}

class クラス名 extends 元となるクラス名{
	}
    親クラスとの差分だけを記述して新たなクラスを宣言

```
