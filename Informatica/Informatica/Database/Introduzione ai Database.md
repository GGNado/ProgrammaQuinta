#Prota #Informatica 
- Prima si usavano i file di record
- DBMS: (Database managment system) software della gestione di questa quantità di dati, database è la raccolta di dati
- Si possono eseguire diverse operazioni: ricerca, aggiunta, modifica, cancella, selezione (CRUD)
- Le informazioni vengono gestite dal [[Sistemi informativi]] 

## Introduzione
In ogni applicazione informatica vengono trattate informazioni ed è necessario che queste informazioni vengano memorizzate in modo permanente per essere poi utilizzate in successive elaborazioni. Questi dati vengono gestiti dai [[Sistemi informativi]] e dai [[Sistemi informativi#Sistemi informatici]]. 
### Archivi e applicazioni informatiche (da sapere)
- Archivio è l'insieme dei dati che vengono salvati su un supporto di memorizzazione
- Applicazioni informatiche utilizza dati in esso immagazzinati per svolgere una funzione specifica

### Problema di non usare i Database
Se prendiamo in considerazione un'azienda che non utilizza i database per gestire i file, dati e applicazioni saranno strutturati in maniera autonoma e disgiunta anche se fanno parte dello stesso sistema. Questo comporta dei problemi quando è necessaria la condivisione e la modifica in contemporanea di tutte quelle applicazioni che lavorano su uno stesso file. Una soluzione estrema sarebbe quella di duplicare per ogni applicazione i dati, però abbiamo come conseguenza lo spreco di memoria.

#### Soluzione
È necessario quindi disporre di un sistema in grado di contenere tutti i dati per le diverse applicazioni in modo da avere una sola copia, sempre aggiornata, disponibile per tutti i programmi che consenta l'accesso simultaneo a più utenti. Questo sistema deve offrire inoltre 
- Un'interfaccia che permetta di interagire con i dati
- Uno specifico linguaggio per rendere possibili le operazioni di archiviazione, modifica e recupero dei dati.
- di poter modificare i dati senza danneggiare le applicazioni già funzionanti
Tale soluzione è proprio il [[Introduzione ai Database]]

## Il DBMS
Con l'utilizzo di un database, la definizione la struttura dei dati è indipendente dall'applicazione e necessitiamo di un software chiamato DBMS che si occupa di gestire i dati. 
In sintesi i DBSM:
- Deve gestire grandi quantità di dati
- Deve garantire la condivisione dei dati
- Deve garantire la persistenza, ovvero i dati devono durare nel tempo
- Deve garantire l'affidabilità delle transazioni, ovvero non devono generare situazioni inconsistenti
- Offrire interfacce grafiche per l'amministrazione come: MariaDB, MySQL

Le sue principali caratteristiche che deve avere sono:
- [[#Gestione efficiente]]
- [[#Persistenza e affidabilità]]
- [[#Sicurezza]]
- [[#Condivisione e gestione della concorrenza]]
##### Gestione efficiente
Essere in grado non solo di gestire i dati, ma di farlo nel modo più efficiente possibile. Il DBMS non deve rappresentare un collo di bottiglia, ovvero uno strumento che rallenti l'elaborazione dei dati della nostra applicazione. I DMBS sono organizzati in strutture dati ad albero, tabelle di hash. 
##### Persistenza e affidabilità
Deve operare sui dati rispettando alcune proprietà, note con la sigla ACID acronimo di:
- Atomicity: le operazioni devono essere interrompibili
- Consistency preservation: al termine di una operazione, il DBMS deve ritornare allo stato da cui è partito
- Isolation: deve isolare quelle operazioni intermedie
- Durability: i dati e risultati devono essere permanenti
##### Sicurezza
Gestire l'accesso ai dati solo ad utenti in possesso di diritti di accesso
##### Condivisione e gestione della concorrenza
Deve garantire la sincronizzazione per l'accesso condiviso dei dati.
### Architettura del DBMS

La struttura del Database Management System (DBMS) si articola su tre livelli:
#### 1. Schema Esterno (o vista utente)
- Rappresenta la parte del database visibile agli utenti.
- Ogni utente può avere una vista personalizzata dei dati.
- Le viste mostrano solo le informazioni rilevanti per un particolare utente o applicazione.
#### 2. Schema Logico
- Descrive la struttura dei dati compresa dal DBMS.
- Rappresenta l'organizzazione e le relazioni tra i dati in modo astratto.
- Include tabelle, relazioni e vincoli senza dettagli sulla memorizzazione fisica.
#### 3. Schema Interno (o fisico)
- Rappresenta la struttura fisica effettiva del database.
- Descrive come i dati sono memorizzati e organizzati nel sistema di archiviazione.
- Include dettagli come i file di dati, gli indici e la struttura di memorizzazione su disco.


