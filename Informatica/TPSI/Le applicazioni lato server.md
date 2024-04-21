# Programmazione Server-Side
Con il termine programmazione Server-side si intende tutta la logica che il server deve fare per generare una risposta dinamica al client, in genere nel formato HTML, questa elaborazione che avviene sul server prende il nome di elaborazione server-side.
Oggi sono disponibili diverse tecniche di programmazione server-side che si differenziano per:
- i linguaggi di programmazione supportati;
- i Web server supportati;
- il particolare ambito applicativo per il quale sono concepite.
Queste tecniche di programmazione sono classificate in:
- Codice separato: Common Gateway Interface, servlet, server api
- Codice embedded in HTML: [[Pagina JSP]], PHP 
Il client può inviare questi dati in un form html dove con un tasto submit in base a due diversi metodi, get e post è possibile inviare i dati al server che poi eseguirà delle operazioni. Naturalmente la scelta del metodo cambia fa variare il comportamento dell'invio. 

## Codice Separato
come accennato prima, possiamo avere:
### Common gateway Interface
in particolare usato con i linguaggi C e Python.
Le operazioni si svolgono in un ordine preciso, ovvero:
1) Il client invia da un form i dati al server
2) Il server chiama il programma CGI passandogli i parametri del form
3) Il programma CGI esegue tutte le varie operazioni e restituisce il risultato in HTML al server
4) Il server invia la risposta al client
### Servlet
Un'alternativa sono le [[Servlet]] che vengono usate in Java. 
##### Prime differenze
- Le servlet, essendo eseguite su una JVM sono portabili su tutte le macchine.
- Le servlet vengono caricate in memoria solo una volta e poi viene creato un thread per ogni richiesta, mentre le CGI vengono eseguiti e caricati ogni volta che c'è una richiesta.
- Servlet solo java, CGI supporta più linguaggi
##### **Funzionamento delle Servlet:**
- Ogni istanza di una servlet è un oggetto Java caricato ed eseguito dal Web server nel contesto del ciclo di richiesta/risposta dei servizi.
- Il controllo della servlet è gestito da un'applicazione Java chiamata container, la più famosa tomcat, che regola il suo ciclo di vita. Grazie al conteiner il programmatore si deve occupare solamente della parte logica dell'applicazione perchè il conteiner gestice i client, il multithreading ecc ecc.
##### Svolgimento
Naturalmente anche qui abbiamo un ordine:
1) un client invia una richiesta (request) per una servlet a un Web application server;
2) se si tratta di una prima richiesta allora il server istanzia e carica la servlet;
3) si attiva un thread che gestisce la comunicazione tra il client e la servlet stessa;
4) il server invia al thread-servlet la richiesta pervenutagli dal client;
5) il thread-servlet costruisce e imposta la risposta (response) e la inoltra al server
6) il server invia la risposta al client.
##### Come si creano
Le servlet sono delle classi java che estendono la classe HTTPServlet che invoca una serie di metodi, in particolare i metodi HTTP:
- doGet
- doPost
- doPut
- doDelete
- doHead
- doOptions
- doTrace
In particolare nel doGet e nel doPost vengono passati oggetti chiamati request e response che appartengono anche loro a determinate classi java: HTTPServletRequest e HTTPServletResponse
###### HTTPservletRequest
- Contiene la richiesta del client
- Permette di ottenere i dati che l'utente ha inviato
###### HTTPservletResponse
- Contiene la risposta del client
- Permette di inviare i dati all'utente in formato HTML, flusso binario, messaggi di errore e molto altro
#### Ciclo di vita

Prima di procedere con il codice della servlet è necessario analizzare il suo ciclo di vita, che può essere riassunto in tre fasi: init()  service()  destroy()
Durante l'init(),che prevede un oggetto di tipo ServletConfig, il container inizializza la servlet e tutte le sue risorse. Successivamente si passa al service() una volta che il client fa richiesta, e si risponde con ServletRequest o response. Poi si passa al destroy una volta che il webserver si interrompe. 

##### Struttura
È molto importante organizzare il nostro progetto con tomcat e servlet secondo un Desgin pattern appropriato, ovvero il [[Design patter MVC]] che comprende le cartelle model, controll e view. Unica variazione è il nome della cartella view in webapp dove inseriamo le jsp

### Vantaggi Servlet
- Portabilità: essendo scritte in java abbiamo un supporto infinito su tutti i dispositivi
- Efficienza: vegono caricate solo una volta e poi le richieste vengono gestite con i thread
- Persistente: rimangono caricate fino alla chiusura del web server
- Gestione delle sessione: visto che il protocollo HTTP non è in grado di ricordare i dettagli delle precedenti sessioni, con le servlet siamo in grado di ricordare cosa si sono scambiati ecc ecc
### Svantaggi
Non hanno senso quelli sui libri



