- Capacità di mantenere i dati duraturi nel tempo
Esiste a tre livelli:
- cookie (Lato [[Architettura Client & Server#Client]])
- sessioni (Lato [[Architettura Client & Server#Server]])
- lettura e scrittura su DB (lato [[Database]])

## In python
[[FastApi]] e tutti i framework che usiamo non ha un modo per ricordaci se un utente, ad esempio si è loggato, quindi ci viene in supporto il [[JWT]]
## In Java
Al contrario, in java possiamo sfruttare le sessioni delle nostre servlet che sono in grado di ricordarsi tutti i dati che un utente ha trasferito, manipolato. 