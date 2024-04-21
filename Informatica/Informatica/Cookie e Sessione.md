#Prota #Greco #Informatica #Java #JSP
- Servono per far ricordare al server cosa si è detto con il client
- I cookie ci permettono di avere sessioni

Per avere id della sessione
```html:
<%= session.getId() %>
```

Conta sessione:
```jsp:
<%@ page import="java.util.Random" %>  
<%@ page contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>  
<!DOCTYPE html>  
<html>  
<head>  
    <title>JSP - Hello World</title>  
</head>  
<body>  
<%  
        //SE NON è STATO SCELTO IL NUMERO, GENERIAMOLO  
        if (session.getAttribute("num") == null){  
            session.setAttribute("num", new Random().nextInt(101));  
        }  
        if(session.getAttribute("conta") != null ){  
            session.setAttribute("conta", (Integer) session.getAttribute("conta") + 1);  
        } else {  
            session.setAttribute("conta", 1);  
        }  
%>  
  
<h1>Numero di sessioni: <%= session.getAttribute("conta")%></h1>  
<h1>Numero random: <%= session.getAttribute("num")%></h1>  
</body>  
</html>

```
