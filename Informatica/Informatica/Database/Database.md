# Introduzione
Le applicazioni con i database vedono i dati a seconda di come sono organizzati logicamente (modello logico) e li elaborano utilizzando strumenti e linguaggi messi a disposizione, come nel caso di SQL, usiamo un modello relazionale. L'app non si occupa della parte fisica, ovvero di salvare i dati, ma si occupa il DBMS.
# Modello logico
Il modello logico dei dati è l'insieme di costrutti utilizzati per organizzare i dati di interesse e descriverne la dinamica.
- Ogni DMBS ne ha uno
- Caratterizzato dall'insieme di concetti per strutturare i dati
- Caratterizzato dall'insieme di regole che descrivono eventuali vincoli
Tra i più famosi modelli ricordiamo:
- Gerarchico: viene rappresentato tramite un albero
- Reticolare: viene rappresentato tramite un grafo
- relazionale: rappresentabile mediante tabelle e relazioni tra di esse (Mysql)
- a oggetti: che è un'estensione alla basi di dati dati del paradigma object oriented
- XML punti molto impiegato come strumento per l'esportazione di dati tra diverse applicazioni
- Schema-less: modelli NOSql, utilizzano un insieme di approcci accomunati dal tentativo di superare la rigidità del modello relazionale per esempio gli approcci Key/Value.
## Modello gerarchico
- Rappresentato secondo <U>strutture ad albero</U>, <u>la radice</u> è il record principale del database da cui partono uno o più sotto alberi. 
- Ogni elemento prende il nome di <u>segnemto</u>
- permette di rappresentare i dati sfruttando la relazione tra segmenti padre e segmenti figli, che prende il nome di relazione uno a molti. 
(Nella relazione 1 a N, il padre può avere molti figli, i figli solo un padre)
Un esempio comune di modello gerarchico è il File System
## Modello Reticolare
- rappresentato mediante grafo
- viene considerato come un'estensione del modello gerarchico dove ogni nodo può essere il punto di partenza per raggiungere un determinato campo
- per poter realizzare le connessione tra diversi record vengono utilizzati i record connettori
# Modello relazionale
- il modello relazionale usa come struttura dati la relazione tabella
- ogni tabella è composta da righe e colonne, le colonne sono i diversi campi o proprietà e ogni riga corrisponde a record
 Il modello relazionale viene utilizzato in mySql.
 Le principali caratteristiche dei modelli Relazionale sono:
- utilizzo di tabelle campi per memorizzare i dati
- schema fisso delle tabelle con chiave primaria che identifica univocamente una riga della tabella
- presenza di relazione tra due o più campi di tabelle mediante chiavi esterne
- accesso ai dati garantito con la proprietà proprietà Acid ovvero a atomicità, consistenza, isolamento e durabilità
# Modello a oggetti
Invece di utilizzare le tradizionali tabelle e righe, questo modello organizza i dati come oggetti con attributi e comportamenti.
# Modello XML
- non è propriamente un modello di database
- è un linguaggio simile all'HTML con il quale condivide i tag
- la principale caratteristica è che XML può rappresentare contenuti in un formato compatibile con qualsiasi sistema
# Modello NoSQL (Schema less)
- NoSQL = Not only SQL
- questo modello non si oppone a SQL ma ne preleva alcune funzionalità e si propone di superare i suoi limiti in termini di elasticità e scalabilità.
database no sequel possono avere le caratteristiche più disparate: alcuni usano tabelle e campi ma senza schemi fissi altri non utilizzano il modello relazionali con chiave primarie ed esterne altri ancora non gestiscono le transazioni Acid.
Un esempio di NoSql che sta avendo maggiore successo è MongoDB
# Progetto di un database
La progettazione di un database segue fasi e regole ben precise:
1) analisi del problema
2) progettazione concettuale ovvero modelle ER
3) progettazione logica ovvero schema logico
Queste 3 fasi si possono definire modellazione dei dati dove andiamo a creare le tabelle
4) progettazione fisica
5) realizzazione dell'applicazione
Queste ultime invece si possono definire modellazione funzionale Dove andiamo a implementare le tabelle e andiamo a creare le funzioni che accedono i dati
# SQL
Uno tra i linguaggi più diffusi che si interfacciano ai database relazionali e SQL. non è un vero e proprio linguaggio di programmazione ma è un linguaggio dichiarativo dove:
- è possibile definire gli schemi delle relazioni attraverso il DDL (data defination language)
- è possibile leggere modificare e inserire dati attraverso il DML (data manipulation language)
- DCL (data control language) gestisce le autorizzazioni degli utenti
- è possibile estrarre informazioni attraverso le query
