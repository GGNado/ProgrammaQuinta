Il **protocollo TCP** è orientato alla connessione (connection-oriented) e si distingue per la sua affidabilità. Garantisce il controllo dell'integrità dell'informazione nei pacchetti mediante un sistema di acknowledge che consente il rilevamento degli errori. Tuttavia, la sua affidabilità e il controllo dell'errore rendono il TCP più lento rispetto ad altri protocolli. In contesti di comunicazione [[Unicast]], TCP è ampiamente utilizzato.
### 3-Way Handshake
Il **3-way handshake** è una procedura fondamentale nel protocollo TCP per stabilire una connessione tra mittente e destinatario. Consiste in tre passaggi sequenziali:

1. **SYN (Synchronize):** Il mittente invia un pacchetto SYN al destinatario per indicare l'intenzione di stabilire una connessione.
2. **SYN-ACK (Synchronize-Acknowledge):** Il destinatario risponde con un pacchetto SYN-ACK, indicando la disponibilità a stabilire la connessione. Il server, quando riceve la tua richiesta di connessione, crea un socket remoto associato al tuo indirizzo IP e alla tua porta. Questo socket gestirà la comunicazione da parte del server.
3. **ACK (Acknowledge):** Il mittente invia un pacchetto ACK al destinatario, confermando la ricezione del SYN-ACK e finalizzando la connessione.

Il 3-way handshake assicura che entrambe le parti siano pronte a iniziare la comunicazione, stabilendo una connessione affidabile e bidirezionale.