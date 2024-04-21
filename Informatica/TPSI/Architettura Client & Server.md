## Client
- **Ruolo:** Il client è la parte dell'applicazione che interagisce direttamente con l'utente. Rappresenta l'interfaccia utente e gestisce l'input dell'utente.
- **Responsabilità:** Invia richieste al server e riceve le risposte. L'elaborazione dei dati e la presentazione all'utente avvengono sul lato del client.
- **Esempi di client:** Browser web, applicazioni desktop, app mobili.

## Server
- **Ruolo:** Il server è responsabile di gestire e fornire i servizi richiesti dai client. Riceve le richieste dai client, elabora le informazioni e invia le risposte.
- **Responsabilità:** Archivia e gestisce i dati, elabora le richieste del client, esegue la logica dell'applicazione.
- **Esempi di server:** Server web, database server, server di posta elettronica.

## Architetture

### Architettura a due livelli (Two-Tier)
- Semplice e diretta.
- Il client si occupa dell'interfaccia utente e della logica dell'applicazione, mentre il server si occupa dell'elaborazione dei dati e della gestione dei database.
- Spesso utilizzata in applicazioni desktop.

### Architettura a tre livelli (Three-Tier)
- Suddivide l'applicazione in tre componenti: interfaccia utente, logica dell'applicazione e gestione dei dati.
- Il client si occupa dell'interfaccia utente, un server intermedio (application server) gestisce la logica dell'applicazione e un server di database gestisce i dati.
- Fornisce una maggiore scalabilità e flessibilità rispetto all'architettura a due livelli.

### Architettura a microservizi
- Suddivide l'applicazione in servizi indipendenti, ognuno dei quali è responsabile di una funzionalità specifica.
- Ogni microservizio può essere sviluppato, distribuito e scalato indipendentemente.
- Promuove la modularità e la manutenibilità.

### Architettura a serverless
- La logica dell'applicazione è eseguita in risposta a eventi senza la necessità di gestire direttamente i server.
- L'infrastruttura sottostante è gestita automaticamente dal provider di servizi cloud.
- Riduce la complessità operativa e consente di pagare solo per le risorse effettivamente utilizzate.

