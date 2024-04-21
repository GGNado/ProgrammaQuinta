- Framework
- Implementa [[JPA]]
- Gestisce la persistenza degli oggetti Java in database relazionali, offrendo un mapping oggetto-relazionale (ORM).

Scriviamo oggetti POJO, e nella riga prima dello specifico campo scriviamo @(qualcosa) che avrà la specifica di quel campo

- Crea la tabella e l'oggetto
```java:
@Entity  
@Table(name = "People")  
public class User {  
    @Id  
    private Integer id;
```