- Stateless: ovvero non ha memoria. Si usano i [[Cookie e Sessione]]
### Introduzione
Il protocollo HTTP, che fa parte del livello Applicativo del modello ISO/OSI, viene usato per trasmettere risorse come un file o anche Query e queste risorse vegono identificate attraverso un URI o URL
### Protocollo HTTP nel dettaglio
HTTP consente di inviare e ricevere le risorse Web, rappresentate da documenti, pagine o elementi di una singola pagina Web, da un host chiamato server a un altro chiamato client.
#### Come fa a comunicare?
Per comunicare utilizza le sessioni dove ciascuna di sessione stabilisce una connessione al server ed esegue una richiesta contenete l'URL. Il server risponderà con la restituzione/produzione della pagina/risorsa richiesta e infine chiude la connessione (questo nel caso più semplice)
#### Tipi di Connessioni
Come protocollo di trasporto utilizza il TCP e questa connessione nel caso più semplice viene chiusa immediatamente dopo.
Nel HTTP 1.1 di tipo permanente il server lascia aperta la connessione TCP dopo aver spedito la risposta. Le successive richieste e risposte fra client e server utilizzano sempre la stessa connessione. 
Esistono due tipi di connessioni permanenti:
- incanalata: le richieste del client vengono aggiunte in una coda detta pipline
- non incalanata: il client può inviare le successive richieste solo dopo aver ricevuto la risposta della precedente.
L’HTTP 1.1 utilizza di default la connessione incanalata

#### Messaggi HTTP
I messaggi che Client e Server si scambiano sono formati da:
- una riga iniziale: contiene la versione del protocollo HTTP
- un header non sempre obbligatorio: dove troviamo informazioni come tipo di browser
- una riga vuota
- un body non sempre obbligatorio

e possono essere ad esempio:
- [[#HTTP Request]]
- [[#HTTP Response]]

##### HTTP Request
Una HTTP request è un messaggio testuale inviato dal client al server ed è formato da tre elementi:
- [[#Riga di richiesta]]
- [[#Intestazione HTTP]] (header),
- [[#Corpo del Messaggio]] (messagebody),

###### Riga di richiesta
Contiene:
- il Metodo: CONNECT, DELETE, GET, HEAD, POST, PUT, OPTIONS, TRACE
- URI o URL: è l’identificativo di risorsa richiesta al server;
- La versione: HTTP 1.0 HTTP 1.1 ecc

###### Intestazione HTTP
Contiene tutte le informazioni necessarie per l’identificazione del messaggio. Classificate in
- intestazioni generali; 
- intestazioni della richiesta;
- intestazioni del corpo dell’entità

###### Corpo del Messaggio
Contiene i dati trasportati (nel caso anche del post)

##### HTTP Response
Dopo che il server HTTP ha ricevuto una richiesta da un client, può effettuare l’esecuzione di uno script in tecnologia server-side . Fatto ciò, il server Web risponde al client con una risposta HTTP.

Questa risposta è organizzata come una richiesta [[#HTTP Request]]. L’unica differenza è che le risposte iniziano con una [[#Riga di stato]] al posto della [[#Riga di richiesta]]. Quindi è formata da:
- Riga di stato: esempio Stato 200 che sarebbe OK
- [[#Intestazione HTTP]]
- [[#Corpo del Messaggio]]: che conterrà in genere la pagina HTML
#### Metodi HTTP
Come detto in precedenza, la prima riga del [[#HTTP Request]] conterrà il metodo. I metodi possono essere: 

| Metodo  | Versione HTTP | Descrizione                                                                                                                                                       |
| ------- | ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| GET     | 1.0 e 1.1     | Il metodo GET viene utilizzato per richiedere dati da una risorsa specifica                                                                                       |
| HEAD    | 1.0 e 1.1     | Il metodo HEAD è simile a GET, ma restituisce solo gli header della risorsa richiesta senza il corpo del messaggio                                                |
| POST    | 1.0 e 1.1     | Il metodo POST viene utilizzato per inviare dati al server per essere elaborati                                                                                   |
| PUT     | 1.1           | Il metodo PUT è utilizzato per caricare o aggiornare una risorsa specifica nel server. Se la risorsa esiste già, verrà sovrascritta; se non esiste, verrà creata. |
| DELETE  | 1.1           | Il metodo DELETE è utilizzato per rimuovere una risorsa specifica dal server                                                                                      |
| OPTIONS | 1.1           | Il metodo OPTIONS viene utilizzato per ottenere informazioni sulle opzioni e le caratteristiche supportate da una risorsa                                         |
| TRACE   | 1.1           | Il metodo TRACE viene utilizzato per eseguire un test di loopback diagnostico.                                                                                                                                                                  |

###  URL
Un **URL** (*Uniform Resource Locator*) è un indirizzo utilizzato per identificare e accedere alle risorse su Internet. Gli URL sono formati da diverse parti:

1. **Schema:** Specifica il protocollo utilizzato (es. "http://" o "https://").

2. **Host:** Il nome di dominio o l'indirizzo IP del server che ospita la risorsa.

3. **Porta (opzionale):** Specifica il canale di comunicazione sul server.

4. **Percorso:** Indica la posizione specifica della risorsa sul server.

5. **Query:** Trasmette parametri al server (es. criteri di ricerca).

6. **Frammento:** Identifica una sezione specifica all'interno della risorsa.

Gli URL sono fondamentali per accedere a siti web e risorse online e vengono utilizzati in browser, email, condivisione di file e altri contesti online. La loro corretta formattazione è essenziale per garantire l'accesso alle risorse desiderate
