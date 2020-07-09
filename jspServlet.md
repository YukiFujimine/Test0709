---
title: "jspServlet"
tags: ""
---
```java
package servlet;
import java.io.IOException;
import javax.servlet.RequestDispatcher;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
/**
 * Servlet implementation class Main
 */
@WebServlet("/main")
public class Main extends HttpServlet {
	/**
	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		String xStr=request.getParameter("x");
		int x=xStr==null? 0:Integer.parseInt(xStr);
		String yStr=request.getParameter("y");
		int y=yStr==null? 0:Integer.parseInt(yStr);
		int sum=x+y;
		 /*"x"というラベルでxをセット、xはintだがオートボクシングが効くので引数に入れられる*/
		request.setAttribute("x", x);
		request.setAttribute("y", y);
		request.setAttribute("sum",sum);
		RequestDispatcher rd=request.getRequestDispatcher("/WEB-INF/jsp/main.jsp");
		rd.forward(request, response);
	}
}
09:23
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<%
int x=(Integer)request.getAttribute("x");
int y=(Integer)request.getAttribute("y");
int sum=(Integer)request.getAttribute("sum");
%>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
<p><%=x %>+<%=y %>=<%=sum %></p>
</body>
</html>
```

```html
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<%
int x=(Integer)request.getAttribute("x");
int y=(Integer)request.getAttribute("y");
int sum=(Integer)request.getAttribute("sum");
%>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
<p><%=x %>+<%=y %>=<%=sum %></p>
</body>
</html>
```
