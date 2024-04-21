## Applicazioni di rete
In generale un’applicazione di rete è costituita da un insieme di programmi che vengono eseguiti su due o più computer contemporaneamente: questi operano interagendo tra loro utilizzando delle risorse comuni, accedendo cioè concorrentemente ai database. Quindi ci saranno dei processi che devono scambiare messaggi e per fare ciò, si usano i protocolli che vengono offerti dal [[Modello ISO-OSI]] e dal [[Modello TCP]]. In particolare utilizzeranno il protocollo di trasporto TCP/UDP
## TCP & UDP
TCP e UDP svolgono funzioni diverse: ogni applicazione o processo in esecuzione, prima di poter trasmettere messaggi sulla rete, sceglie il protocollo da usare per poter realizzare la comunicazione. Vedi [[TCP]] e [[UDP]]
## Porte di comunicazione
Essendo che quasi tutti i pc hanno solo una porta fisica per il network, ci serviamo delle porte logiche composte da 2 Byte, quindi comprendono le porte che vanno dallo 0 a 65535
Di queste porte esiste una classificazione:
- Well-know: sono le porte "ben conosciute" che vanno dallo 0 alle 1024, sono porte che il nostro computer già utilizza per servizi fondamentali come [[Protocollo HTTP]], FTP, DNS, [[POP]], [[SMTP]] ecc
- 1025 in poi, sono tutte porte registrate e private che gli utenti possono usare per le proprie applicazioni. 

![[Screenshot 2024-01-23 alle 22.43.47.png]]
Quindi l'identificazione di un servizio si ha dal indirizzo + numero di porta (esempio 127.0.0.1:3000)

## Come si realizzano i socket
Ogni sistema operativo mette a disposizione delle API per realizzare i socket, tra queste le più famose sono:
- socket(): per creare l'oggetto socket
- close(): per terminare l'utilizzo
- connect(): per connettersi
- bind(): per collegare un IP a un socket
- listen(): per ascoltare eventuali richieste 
- send()/recive(): per inviare/ricevere messaggi
## Classificazione dei Socket
Esistono varie famiglie di socket e ricordiamo: 
- Internet socket (AF_INET): permette il trasferimento di dati tra processi posti su macchine remote connesse tramite una LAN o Internet;
- Unix Domain socket (AF_UNIX): permette il trasferimento di dati tra processi sulla stessa macchina Unix
Inoltre i socket possono essere di tre tipi:
- Stream socket (TCP): scambia i messaggi in maniera affidabile, in quanto entrambe le macchine decidono come inviare i messaggi
- Datagram socket (UDP): permette di scambiare messaggi senza connessione, o meglio, senza che entrambi i dispostivi siano online nello stesso momento.
- raw Socket
