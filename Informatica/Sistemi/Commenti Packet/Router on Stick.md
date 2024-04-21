**DOCUMENTAZIONE DEL PROGETTO DI RETE  "VLAN_STICK"**

**Informazioni Generali:**
- **Nome del Progetto:** VLAN_STICK
- **Data:** 24/11/2023
- **Autore:** Massa Luigi

**Descrizione del Progetto:**
Configurare diverse VLAN come (Docente, Presidenza, Studente) oppure (Vendita, Magazzino, Amministrazione) e configura un "Router on a Stick" per permettere la comunicazione fra le diverse VLAN

**Configurazione di Rete:**
- **Dispositivi Utilizzati:** 2 Switch, 1 Router, dispositivi vari
- **Indirizzi IP:** 

| Dispositivo              | IP            | Subnetmask    | Eventuale gateway |
| ------------------------ | ------------- | ------------- | ----------------- |
| PC0 (VLAN 40 Docenti)    | 192.168.40.10 | 255.255.255.0 | 192.168.40.254    |
| PC1 (VLAN 10 Presidenza) | 192.168.10.10 | 255.255.255.0 | 192.168.10.254    |
| PC2 (VLAN 40 Docenti)    | 192.168.40.11 | 255.255.255.0 | 192.168.40.254    |
| PC3 (VLAN 10 Presidenza) | 192.168.10.12 | 255.255.255.0 | 192.168.10.254    |
| PC4 (VLAN 30 Studenti)   | 192.168.30.14 | 255.255.255.0 | 192.168.30.254    |
| PC5 (VLAN 30 Studenti)   | 192.168.30.24 | 255.255.255.0 | 192.168.30.254    |


- **Protocolli Utilizzati:** <u>VTP e Router on a Stick</u>
Il protocollo VTP consente di configurare le VLAN su un solo switch, che si occupa poi di distribuire le VLAN a tutti gli switch della stessa rete avendo stesso dominio. Quindi mi ha evitato di riconfigurare le stesse VLAN anche sul secondo Switch, inoltre in ottica futura, sarà possibile modificare solo una volta le VLAN e in automatico si aggiornerà tutta la rete riducendo drasticamente il lavoro manuale. Il VTP permette di impostare lo switch in 3 modalità: Server, Client e Transparent

Il Router on a stick ci permette di mettere in comunicazioni dispositivi di VLAN diverse attraverso un unico cavo, altrimenti avremmo dovuto collegare al router tanti cavi quante erano le VLAN

**Interfacce dei switch:**
***Switch 1:***
- **Nome:** Switch server
- **Interfacce e Indirizzi IP:**
  - FastEthernet 0/1: Impostato su VLAN 40 Docenti, impostato su Access
  - FastEthernet 0/2: Impostato su VLAN 10 Presidenza, impostato su Access
  - Gig 0/1: Impostato su Trunk

***Switch 2:***
- **Nome:** Switch client
- **Interfacce e Indirizzi IP:**
  - FastEthernet 0/1: Impostato su VLAN 40 Docenti, impostato su Access
  - FastEthernet 0/2: Impostato su VLAN 10 Presidenza, impostato su Access
  - FastEthernet 0/3: Impostato su VLAN 30 Studenti, impostato su Access
  - FastEthernet 0/4: Impostato su VLAN 30 Studenti, impostato su Access
  - Gig 0/1: Impostato su Trunk

**Procedure/Configurazione della rete:**
Dopo aver disposto i vari dispositivi su packet tracer ho iniziato a creare le VLAN sullo switch server con i seguenti comandi:
```
enable
configure Terminal
vlan 10 (il 10 cambia in base al ID della VLAN)
name Presidenza (Presidenza è il nome della VLAN)
end
Show Vlan (Vediamo le VLAN configurate)
```
Questi comandi eseguiti per tutte le VLAN cambiando ID e Nome. Successivamente ho attivato il protocollo VTP, spiegato in precedenza, con i seguenti comandi:
```
enable
configure terminal
show vtp status (Cosi da vedere i vari campi)
vpt mode Server (Impostiamo server nel caso dello switch server, Client altrimenti)
vtp domain Scuola (Appartengono al dominio scuola)
```

Eseguiamo per verificare il corretto funzionamento del VTP il comando <u>show vtp status</u>
![[Screenshot 2023-11-24 alle 12.49.28.png]]
Come notiamo questo switch ha modalità server e appartiene al dominio Scuola

Successivamente mi sono spostato sul router e ho iniziato ad applicare il concetto di Router on a Stick con i seguenti comandi:
```
enable
configure terminal
interface FastEthernet 0/0.10 (il .10 cambia in base alla VLAN che stiamo configurando)
encapsulation dot1q 10 (il 10 cambia in base alla VLAN)
ip address 192.168.10.254 255.255.255.0 (impostiamo il gateway della VLAN 10)
```
Dopo aver eseguito questi comandi per tutte le VLAN eseguiamo il comando show <u>running-config</u> e assicuriamo che tutto sia andato a buon fine:
![[Screenshot 2023-11-24 alle 12.58.16.png]]

**Verifiche**![[Screenshot 2023-11-24 alle 13.01.18.png]]

**Diagramma della Rete:**
![[Vlan_stick.pkt]]
![[Screenshot 2023-11-24 alle 13.02.07.png]]