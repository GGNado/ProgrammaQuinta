## Introduzione
SMTP è un protocollo di comunicazione utilizzato per la trasmissione di messaggi di posta elettronica su una rete. È parte del livello di applicazione nel [[Modello ISO-OSI]] e svolge un ruolo fondamentale nel facilitare la consegna affidabile di email tra server di posta elettronica.

## Funzionamento di base
SMTP segue un modello di comunicazione client-server. Il client SMTP, noto come "Mail User Agent" (MUA), invia un messaggio di posta elettronica al server SMTP. Il server SMTP, noto come "Mail Transfer Agent" (MTA), è responsabile della ricezione del messaggio e della sua consegna al destinatario.

## Processo di Invio
1. **Connessione:** Il client SMTP si connette al server SMTP sulla porta standard 25.
2. **Saluto:** Il client invia un saluto al server, e il server risponde con un saluto confermando la connessione.
3. **Trasmissione del Messaggio:** Il client trasmette il messaggio di posta elettronica al server. Questo messaggio include informazioni come l'indirizzo del mittente, l'indirizzo del destinatario, e il corpo del messaggio.
4. **Consegna:** Il server SMTP riceve il messaggio e lo inoltra al server di posta del destinatario o al server successivo nella catena di consegna.
## Conclusione
SMTP è uno degli elementi chiave dell'infrastruttura di posta elettronica, facilitando la trasmissione affidabile dei messaggi attraverso la rete. La sua struttura client-server e i comandi chiave lo rendono un protocollo essenziale per la comunicazione elettronica.
