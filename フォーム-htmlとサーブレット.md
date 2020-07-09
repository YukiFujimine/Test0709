---
title: "フォーム htmlとサーブレット"
tags: ""
---
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>				↓フォームの送信先
	　　　　　　	formLessonアプリのFormSampleServlet
							 サーブレット側の@webServletの()内と名前を揃える	
								この場合@WebServlet("/FormSampleServlet")
<form action="/formLesson/FormSampleServlet" method="post">
名前:<input type="text" name="name"><br>
性別:
男<input type="radio" name="gender" value="0">
女<input type="radio" name="gender" value="1"><br>
<input type="submit" value="送信">
</form>
</body>
</html>
```

```java
import java.io.IOException;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

/**
 * Servlet implementation class FormSampleServlet
 */
@WebServlet("/FormSampleServlet")
public class FormSampleServlet extends HttpServlet {

	protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		request.setCharacterEncoding("UTF-8");
		String name=request.getParameter("name");
		String gender=request.getParameter("gender");
		System.out.printf("送信データname:%s,gender:%s",name,gender);
	}

}
```
