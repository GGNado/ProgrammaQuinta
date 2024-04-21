Il **Domain Name System (DNS)** è un servizio essenziale su Internet per la risoluzione dei nomi degli host in indirizzi IP. Esso comprende un database distribuito e un protocollo a livello applicazione che regola la comunicazione tra host e name server.

## Concetto di Domain Name System

- **Database Distribuito:**
  - Memorizza coppie (nome simbolico - indirizzo IP) su un insieme di nodi della rete, noti come name server.
  
- **Protocollo a Livello Applicazione:**
  - Regola la comunicazione tra host e name server ed è utilizzato da altri protocolli per la risoluzione dei nomi simbolici.

## Processo di Risoluzione DNS

1. Quando un server locale non riesce a tradurre il nome simbolico di un sito web in un indirizzo IP, contatta un **server DNS radice**.
2. Se il server DNS radice non conosce la mappatura, contatta un **server DNS autorizzato** per ottenere la mappatura richiesta.
3. Il server DNS autorizzato restituisce la mappatura al server DNS locale, che può ora effettuare la traduzione e rispondere alla richiesta iniziale.

## Server DNS Radice e Top-Level Domain (TLD)

- Attualmente, ci sono **13 server radice** sparsi per il mondo, etichettati da A a M, organizzati come un cluster di server replicati.
- Sono noti anche come **server di nomi radice** e corrispondono ai domini di più alto livello (top-level domain).
- I server TLD, collegati agli altri server nella rete, formano una struttura "ad albero".
- I domini di alto livello includono com, org, net, edu, ecc., e domini locali di alto livello come uk, fr, ca, jp.

## Sicurezza e DNS

- **DNSSEC (DNS Security Extensions):**
  - Estensioni di sicurezza per il DNS che aggiungono autenticazione e integrità, prevenendo attacchi come il dirottamento di DNS.

