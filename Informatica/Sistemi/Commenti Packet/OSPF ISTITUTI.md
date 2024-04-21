**DOCUMENTAZIONE DEL PROGETTO DI RETE  "OSPF_ISTITUTI"**

**Informazioni Generali:**
- **Nome del Progetto:** OSPF_ISTITUTI
- **Data:** 03/10/2023
- **Autore:** Massa Luigi

**Descrizione del Progetto:**
Fare una configurazione con il protocollo OSPF così da permettere ai vari dispositivi degli istituti di poter comunicare fra loro. 

**Configurazione di Rete:**
- **Dispositivi Utilizzati:** 3 Switch, 3 Router, dispositivi vari
- **Indirizzi IP:** 

| Dispositivo         | IP             | Subnetmask    | Eventuale gateway |
| ------------------- | -------------- | ------------- | ----------------- |
| Router Alessandrini | 192.168.20.254 | 255.255.255.0 |                   |
| Router Liceo        | 10.0.0.254     | 255.0.0.0     |                   |
| Router Marino       | 176.16.1.254   | 255.255.0.0   |                   |
| Laptop 0            | 10.0.0.8       | 255.0.0.0     | 10.0.0.254        |
| PC 0                | 192.168.20.8   | 255.255.255.0 | 192.168.20.254    |
| PC 1                | 172.16.1.8     | 255.255.0.0   | 172.16.1.254      |


- **Protocolli Utilizzati:** [OSPF]
Il protocollo OSPF viene utilizzato all'interno degli [Autonomus System]. Il Protocollo OSPF (Open Shortest Path First) è un protocollo di routing utilizzato per determinare le rotte più efficienti all'interno di una rete. OSPF fa parte della famiglia di protocolli di routing link-state, il che significa che i router scambiano informazioni sullo stato dei collegamenti di rete tra di loro per calcolare il percorso migliore verso una destinazione.

Quindi nel nostro caso se la scuola Marino dovesse mandare un messaggio al liceo, il protocollo OSPF eseguirà una somma in base ai "costi", ovvero viene assegnato un numero detto costo a tutti i collegamenti del router, e deciderà il percorso migliore e più efficiente.

**Interfacce dei router:**

***Router 1:***
- **Nome:** Liceo
- **Interfacce e Indirizzi IP:**
  - Seriale 0/0: 2.2.2.3
  - Seriale 1/0: 3.3.3.3 
  - FastEthernet 2/0: 10.0.0.254

***Router 2:***
- **Nome:** ITT Alessandrini
- **Interfacce e Indirizzi IP:**
  - Seriale 0/0: 1.1.1.1
  - Seriale 1/0: 2.2.2.2
  - FastEthernet 2/0: 192.168.20.254

***Router 3:***
- **Nome:** IP Marino
- **Interfacce e Indirizzi IP:**
  - Seriale 0/0: 1.1.1.2
  - Seriale 1/0: 3.3.3.4
  - FastEthernet 2/0: 172.16.1.254

**Configurazione del Protocollo:**

Abbiamo aperto i CLI di ogni router e abbiamo eseguito i seguenti codici:
1) Ci siamo assicurati di entrare come amministratori
2) Iniziamo ad entrare nella configurazione del protocollo con il comando: router OSPF "id processo". Id processo possiamo dare un qualsiasi numero che identificherà il processo
3) Ora abilitiamo il protocollo su tutte le interfacce con: network 192.168.1.0 0.0.0.255 area 0 dove <u>network</u> è la parola chiave, <u>192.168.1.0</u> è l'interfaccia dove vogliamo attivare il protocollo, <u>0.0.0.255</u> è la wildcard, <u>area 0</u>: questa è la specifica dell'area OSPF a cui appartiene questa rete. Eseguiamo questo comando su tutte le interfacce ethernet e seriali e su ogni router.

**Diagramma della Rete:**

![[OSPF_Istituti.pkt]]

![[OSPF.png]]