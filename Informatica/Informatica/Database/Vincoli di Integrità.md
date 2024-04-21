# Introduzione
All'interno dei [[Introduzione ai Database#Il DBMS]] viene messo in atto un insieme di regole che cercano di evitare l'inserimento errato di dati, sia per quanto riguarda la prima popolazione del database, ma anche quando si vanno ad apportare aggiornamenti o eliminazioni di tuple bisogna prevenire situazioni di inconsistenza (Esempio marco in una tabella è nato a Milano, ma in un'altra tabella è nato a Roma)
## Classificazione
È possibile classificare i vincoli di integrità in
- [[#Intrarelazionale]]: vincoli su singoli attributi della tabella, ad esempio i check
- [[#Interrelazionale]]: vincoli che coinvolgono più relazione, ad esempio le primary key
### Intrarelazionale
Possono essere di due tipi:
- Vincoli su attributi di una tupla che possono essere [[#Vincoli Statici]] o [[#Vincoli Dinamici]]
- Vincoli di chiave
#### Vincoli Statici
Ll controllo avviene solo al momento dell'inserimento o dell'aggiornamento (ad esempio la check) e sono:
- Vincolo di correttezza: nel caso il dato sia un codice verificabile tramite algoritmi (codice fiscale)
- Presenza di valore che prende il nome di dizionario
- Vincolo sul valore che è dipendente da altri attributi in altre relazioni
##### Esempi
Si potrebbe impostare un controllo sull'attributo Nome/Cognome che non deve contenere numeri, oppure età deve essere maggiore di 0. Oppure un vincolo sul valore che sarà Vero, solo se il primo valore è uguale a qualcosa.
#### Vincoli Dinamici
Il controllo è periodico perchè il valore subisce variazioni in base al tempo (stipendio precedente/successivo)


### Interrelazionale
Essendo che i dati delle tabelle sono in relazione fra loro, queste relazioni subiscono dei vincoli sia quando si inserisce un elemento, che quando lo si aggiorna o elimina.
In particolare, con l'utilizzo delle chiavi esterne, è necessario che queste chiavi siano chiavi primari nella loro tabella di appartenenza. (il libro fa l'esempio che non può esistere un'esame del sangue se non si ha il paziente)
#### Regole di inserzione e modifica
È possibile nei DBMS impostare delle regole che impongano o meno il rispetto di queste regole, abbiamo:
- Inserzione dipendente: esegue l'inserzione di un'istanza nell'entità figlio solo se la chiave padre esiste già
- Inserzione automatica: esegue l'inserzione nel figlio, e se il padre non esiste, viene creato
- Inserzione nulla: esegue l'inserzione nel figlio, e se la chiave padre non esiste, viene messa a NULL
- Inserzione di default: esegue l'inserzione e se la chiave padre non esiste, si applica un valore di default
- Nessun effetto: non ci sono vincoli
#### Regole di Cancellazione
- Cancellazione con restrizione: consente l'eliminazione del padre solo se non ci sono riferimento nel figlio
- Cancellazione a cascata: permette sempre la cancellazione del padre ed elimina tutte le tuple nel figlio 
- Cancellazione nulla: permette la cancellazione del padre e nel figlio le chiavi esterne vengono impostate a null
- Cancellazione di default: stesso ragionamento ma con un valore di default







