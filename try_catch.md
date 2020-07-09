---
title: "try~catch"
tags: ""
---
```java
static int getInputRange(String msg, int min, int max) {
		int n;
		while (true) {
			// scannerは例外を発生した際値を保持し続けるのでループの頭でnewする。
			s = new Scanner(System.in);
			System.out.print(msg);
			try {
				n = s.nextInt();// nextIntは整数以外だとInputMismatchExceptionを投げる
				if (n < min || n > max) {
					// この場合も例外を投げる
					throw new InputMismatchException();
				}
				// 適正な値が入ったらループを抜ける
				break;
			} catch (InputMismatchException e) {
				System.out.printf("err:[%d~%dの整数を入力してください]\n", min, max);
			}
		}
		return n;
	}
```
