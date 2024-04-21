Il **protocollo UDP** opera senza connessione (connectionless), il che significa che non è garantita l'affidabilità della consegna dei pacchetti. In altre parole, per strada, alcuni pacchetti potrebbero perdersi, ma spesso questa perdita non è percepibile agli utenti umani. Tuttavia, UDP offre vantaggi in termini di velocità, essendo più rapido rispetto al TCP, in quanto non richiede la gestione complessa della connessione.
### Caratteristiche di UDP:

- **Senza Connessione:** Non viene stabilita una connessione prima della trasmissione dei dati, il che rende UDP più veloce ma meno affidabile rispetto a TCP.
- **Velocità:** L'assenza di procedura di handshake e di controllo dell'errore rende UDP più veloce, ideale per applicazioni che richiedono tempi di risposta rapidi.
### Utilizzo Principale nel Multicast:
- **Connessione [[Multicast]]:** UDP è ampiamente utilizzato nelle comunicazioni di tipo multicast, dove un singolo messaggio può essere inviato a un gruppo di destinatari contemporaneamente.