- Java database Connector
- ha bisogno di un driver chiamato connettore
- Interfaccia Java per la connessione e la gestione di database relazionali.

```java:
Class.forName("com.mysql.cj.jdbc.Driver");  
connection = DriverManager.getConnection("jdbc:mysql://localhost:3306/<NomeDatabase>", "root", "");

```