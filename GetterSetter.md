---
title: "getter,setter"
tags: ""
---
```java
public class DogApp{
    public static void main(String[] args){
        Dog d1=new Dog("John");
        //d1.weight=2500;
        d1.setWeight(2500);
        d1.setType("Akita");
        System.out.printf("name:%s type:%s weight:%dg%n",d1.getName(),d1.getType(),d1.getWeight());
        Dog d2=new Dog("Paul",100);
        System.out.printf("name:%s type:%s weight:%dg%n",d2.getName(),d2.getType(),d2.getWeight());
    }
}

class Dog{
    private String name;
    private String type;
    private int weight;
    public Dog(String name){
        this.setName(name);
    }

public Dog(String name){
        this.setName(name);
    }
    public Dog(String name,int weight){
        this(name);
        this.setWeight(weight);
    }
    public Dog(String name,String type,int weight){
        this(name,weight);
        this.setWeight(weight);
    }
    public void setName(String name){
        this.name=name;
    }
    public String getName(){
        return this.name;
    }
    public void setType(String type){
        this.type=type;
    }
    public String getType(){
        return this.type;
    }
    public void setWeight(int weight){
        if(weight<0 || weight>30000){
            throw new IllegalArgumentException("値が不正です");
        }
        this.weight=weight;
    }
    public int getWeight(){
        return this.weight;
    }
}

```
