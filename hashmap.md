---
title: "HashMap"
tags: ""
---
```java
import java.util.*;
public class HashMapLesson{
  public static void main(String[] args){
    Random rand=new Random();
    HashMap<Integer,Integer> map=new HashMap<>();
    final int count=100;
    final int min=1;
    final int max=100;
    for(int i=0;i<count;i++){
      int num=rand.nextInt(max)+1;
      if(map.containsKey(num)){
        map.put(num,map.get(num)+1);
      }else{
        map.put(num,1);
      }   
    }   
    System.out.printf("%d~%dの乱数を%d回発生させたよ\n",min,max,count);
    System.out.println("***result***");
    System.out.printf("%d種類の数値が出ました\n",map.size());
    for(int i=min;i<=max;i++){
      if(map.containsKey(i)){
        System.out.println(i+"..."+map.get(i));
      }   
    }   
  }
}
~    
```
