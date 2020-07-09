---
title: "Map"
tags: ""
---
````java
import java.util.ArrayList;
import java.util.LinkedHashMap;
import java.util.List;
import java.util.Map;

public class Main2{
	public static void main(String[] args){
		// TODO 自動生成されたメソッド・スタ
		Map<String,List<String>> data=new LinkedHashMap<>();
		List<String> tList=new ArrayList<>(); 
				tList.add("切子");
				tList.add("佃煮");
				tList.add("寿司");
				tList.add("のり");
				data.put("東京", tList);
				List<String> kList=new ArrayList<>();
				kList.add("織物");
				kList.add("人形");
				kList.add("漬物");
				kList.add("陶器");
				data.put("京都府", kList);
				System.out.println(data.get("京都府").get(1));
				for(String key:data.keySet()) {
					System.out.print(key+":");
					for(String obj:data.get(key)) {
					System.out.print(obj+",");
					}
				System.out.println();
				}
	}
}```
````
