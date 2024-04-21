#1-capitolo
# Introduzione
Il [[Modello ISO-OSI]] e [[Modello TCP]] implementano diversi protocolli applicativi come:
- [[FTP]]: protocollo di trasmissione dati
- [[Protocollo HTTP]]: protocollo di invio/ricezione risorse web
- [[DNS]]: domain name system
- [[SMTP]]: protocollo di invio email
- [[POP]]: protocollo di ricezione email
Naturalmente tutte le applicazioni che usano questi protocolli si appoggiano sul livello di trasporto
## Architettura
Le architetture che il livello delle applicazioni ammette sono principalmente 3:
- [[Architettura Client & Server]]
- [[Peer to Peer]]
- ibride (peer to peer + Client/Server)
## Servizi offerti dal Livello di Trasporto
Ogni applicazione, dopo aver scelto il tipo di architettura, deve scegliere tra i protocolli di trasporto quale adottare in base alle proprie esigenze:
- trasferimento dati affidabile: in questo caso si sceglieranno i protocolli [[UDP]] e [[TCP]].
- ampiezza di banda: alcune applicazioni richiedono grande larghezza di banda;
- temporizzazione: alcune applicazioni richiedono ritardi bassissimi di latenza (giochi online); 
- sicurezza: alcune applicazioni possono anche richiedere determinate condizioni di [[Crittografia]];
