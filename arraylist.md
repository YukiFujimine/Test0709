---
title: "ArrayList"
tags: ""
---
```java
import java.util.*;
public class ListLesson{
    public static void main(String args[]){
        List<String> names=new ArrayList<>();　//ArrayListをnewする(Listはインターフェイス)
        names.add="たなか";	//リストに要素を追加する
        names.add="すずき";
        names.add="さいとう";
        System.out.println(names.get(1));	//index1のデータを取得する
    }
}

	
*ArrayListに格納できるのは参照型(インスタンス)のみ

	基本データをArrayListに格納するとき　例)int型
	      ArrayList<Integer> points=new ArrayList<>();
        points.add(10);
        points.add(80);
        points.add(75);
        for(int i:points){
            System.out.println(i);
        }
      
				int removedNum=points.remove(2);	//index2をリムーブして入っていた値を変数に入れる
        System.out.println(points.get(0));	//index 0を取り出し

	      
				if(points.isEmpty()){
            System.out.println("要素数は0です");
        }else{
            System.out.println("要素数は0ではありません");
        }

        if(points.contains(10)){
            System.out.println("リストに10は含まれていいます");
        }else{
            System.out.println("リストに10は含まれていません");
        }
```
