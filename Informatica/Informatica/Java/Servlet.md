- Classi che estendono la classe HTTPServlet che permettono di creare delle rotte nuove. 
- Con queste classi facciamo @Override di metodi che stanno nella classe che stiamo ereditando 
- Risponde a un particolare URL (indirizzi) del progetto che sono indicati nella notazione
- Troviamo i metodi doGet, doPost, doDelete = metodi che accediamo a quelli indirzzi
- Ci rende più sicuro il nostro sito web
- Di default risponde con un formato HTML
- Le pagine JSP sono pagine web che vengono prima trasformate in servlet e poi eseguite

# Come si crea
- Una volta aver creato una classe che estende HTTPServlet, bisogna mettere questo tag

```java:
@WebServlet(name = "ServletV0", value = "/ServletV0")  
public class ServletV0 extends HttpServlet {  
    @Override  
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {  
        resp.getWriter().println("Ciao hacker");  
    }  
}
```

Puoi usare anche:
```java:
@WebServlet(urlPatterns = {"/see.html"})
```
dispatch