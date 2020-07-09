---
title: "setAttribute("属性名",インスタンス)リクエストスコープに保存"
tags: ""
---
```java
	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		// TODO Auto-generated method stub
		@SuppressWarnings("deprecation")
		String[] fortunes= {"大吉","中吉","凶"};
		String fortune=fortunes[new java.util.Random().nextInt(3)];
		request.setAttribute("unsei", fortune);

		RequestDispatcher dispatcher=request.getRequestDispatcher("/WEB-INF/jsp/forwardSample.jsp");
		dispatcher.forward(request, response);
	}
```

```html
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
    <%
    String str=(String)request.getAttribute("unsei");
    %>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>きょうの運勢</title>
</head>
<body>
<p>あなたの運勢は<%=str%>です</p>
</body>
</html>
```
