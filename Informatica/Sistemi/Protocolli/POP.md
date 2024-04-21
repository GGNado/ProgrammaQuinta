## Introduzione
Il Protocollo Post Office (POP) è un protocollo di comunicazione utilizzato per il recupero di messaggi di posta elettronica da un server di posta a un client di posta elettronica. Esistono diverse versioni di POP, con POP3 che è la più ampiamente utilizzata.

## Funzionamento di base
POP consente ai client di posta elettronica di recuperare i messaggi dalla casella di posta sul server. La procedura di base comprende i seguenti passaggi:

1. **Connessione:** Il client POP si connette al server POP sulla porta standard 110 (o sulla porta 995 per POP3 sicuro con SSL/TLS).
2. **Autenticazione:** Il client si autentica con il server, generalmente utilizzando nome utente e password.
3. **Accesso alla Casella di Posta:** Il client accede alla casella di posta sul server e recupera i messaggi.
4. **Opzioni di Gestione:** A seconda della configurazione, i messaggi possono essere lasciati sul server o eliminati dopo il recupero.
5. **Chiusura della Connessione:** Il client termina la connessione POP quando ha finito di recuperare i messaggi.
## Modalità di Funzionamento
- **Modalità Download e Eliminazione (Default):** I messaggi vengono scaricati sul client e cancellati dal server (a meno che non siano contrassegnati per la conservazione).
- **Modalità Download e Conservazione:** I messaggi vengono scaricati sul client, ma rimangono sul server anche dopo il download.
## Conclusione
Il protocollo POP è ampiamente utilizzato per il recupero di messaggi di posta elettronica da un server a un client, fornendo un'interfaccia efficiente e standardizzata per la gestione della posta elettronica.
