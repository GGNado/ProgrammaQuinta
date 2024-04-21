
Il protocollo utilizzato a livello applicativo per il trasferimento di file è il **File Transfer Protocol (FTP)**, comunemente chiamato FTP, basato su [[TCP]]. 
## Funzionamento
FTP utilizza due canali TCP separati per trasportare un file in parallelo: una connessione di controllo e una connessione dati.

- **Connessione di Controllo:**
  - Utilizzata per spedire informazioni di controllo tra client e server.
  - Comandi come identificazione dell'utente, password, e comandi per la variazione della directory vengono scambiati.
  - Chiamata "control connection" o "command channel".

- **Connessione di Dati:**
  - Utilizzata per il trasferimento effettivo dei file.
  - Chiamata "data connection" o "data channel".

## Modello Client/Server

Il protocollo FTP segue un modello di tipo [[Architettura Client & Server]], dove la macchina host destinata a svolgere la funzione di server ha in esecuzione uno specifico programma FTP.

### FTP Server

- Software come Filezilla Server mette a disposizione dei client opzioni come download/upload, recupero di trasferimenti interrotti, rimozione e rinomina di file, creazione di directory, e navigazione tra directory.
- L'accesso al FTP server richiede autenticazione, e le credenziali determinano i privilegi dell'utente sul file system.

### FTP Client

- Il client si connette al server utilizzando un software FTP, generalmente gratuito.
- Un FTP client consiste in una parte di comunicazione (implementazione del protocollo FTP) e un'interfaccia utente che agevola le funzioni offerte dal prodotto.
- Filezilla
## Sicurezza e FTPS

In termini di sicurezza, FTP non cifra i dati scambiati, rendendoli vulnerabili. FTPS è una specifica aggiuntiva che introduce un layer di cifratura SSL e una serie di comandi e codici di risposta per proteggere le informazioni scambiate tra client e server.

