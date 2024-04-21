**DOCUMENTAZIONE DEL PROGETTO DI RETE  "NAT/PAT OVERLOAD"**

**Informazioni Generali:**
- **Nome del Progetto:** NAT_PAT_OVERLOAD
- **Data:** 10/10/2023
- **Autore:** Massa Luigi

**Descrizione del Progetto:**
Fare una configurazione con il NAT e PAT così da permettere ai vari dispositivi della rete privata istituti di poter comunicare fra loro. 

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



1) apri il CLI del router della rete privata
2) scrivi en
3) conf t
4) interface Fastethernet 0/0 (Rete privata)
5) ip nat inside
6) exit e entra nella seriale con Interface Serial 2/0
7) ip nat outside
8) exit
9) ip nat inside source list 1 interface Serial 2/0 overload
10) ip nat inside source static tcp "indirizzo privato es. 192.168.1.1" 80 "non so per cosa stia" 12.0.0.1 "Sta per l'indirzzo ip della seriale 2/0" 8080 "numero di porta"
11) fai stessa cosa per tutti gli indirizzi ip privati ma cambia il numero porta
12) ip classless (solo che a me non lo prende)
13) ip route 0.0.0.0 0.0.0.0 12.0.0.2 "ques'ultimo è la seriale dell'altro router"
14) access-list 1 permit 192.168.1.0 0.0.0.255
15) 1 indirizzo pubblico + porta = pat