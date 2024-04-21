### Introduzione
Con gli anni i [[Sistemi informativi]] si sono evoluti e oggi giorno è possibile realizzarli in diverse architetture: in [[#Sistemi centralizzati]] e in [[#Sistemi distribuiti]].

### Sistemi centralizzati
Nei sistemi centralizzati le applicazioni girano in un <u>unico processore o host</u> il quale è diviso tra i vari dispositivi del sistema. Inoltre tutte le risorse del host centrale sono accessibili da tutti. 

Se possiamo dare dei vantaggi per l'utilizzo di questo sistema è che è semplice da creare, gestire e fargli manutenzione. Inoltre è anche più sicuro dei [[#Sistemi distribuiti]]

![[Screenshot 2023-10-08 alle 15.35.58.png]]

### Sistemi distribuiti 
Nei sistemi distribuiti abbiamo <u>più processori cooperanti</u>, le applicazioni risiedono su più host e i dati sono distribuiti tra più nodi. 

![[Screenshot 2023-10-08 alle 16.08.54.png]]
##### Vantaggi
Hanno molteplici vantaggi come:
- Affidabilità: in caso di guasti di un nodo, il sistema continuerà a funzionare, ridondanza.
- Integrazione: qualsiasi dispositivo è in grado di accedervi, qualunque sia il suo sistema operativo e tipologia di hardware,
- Trasparenza: nascondere la complessività del sistema agli utenti facendoli credere di star lavorando su una macchina potente,
- Scalabilità: possibilità di aggiungere/rimuovere componenti
- Efficienza: possono distribuire l'afflusso di utenti su più zone, quindi velocizzare i lavori ed esecuzioni

##### Svantaggi 
Ma anche svantaggi come:
- Complessità: infatti la sua realizzazione e manutenzione richiede competenze specifiche
- Sicurezza: come accennato in precedenza, i sistemi distribuiti avendo più copie di dati sparsi nei nodi, saranno più vulnerabili ad eventuali attacchi.

### Classificazione sistemi distribuiti
- **Sistemi di calcolo distribuiti:** Questi sistemi sono progettati per eseguire calcoli. Prendono due nomi: <u>cluster</u> se vengono usate macchine dello stesso tipo, <u>grid</u> se eterogenee 
- **Sistemi pervasivi distribuiti:** Questi sistemi sono orientati a fornire servizi e funzionalità su dispositivi come smartphone, tablet e dispositivi IoT, domotica o le PAN.
- **Sistemi informativi distribuiti:** Questi sistemi si concentrano sulla condivisione e la gestione di informazioni distribuite su reti. Un esempio comune è il web, dove i dati sono distribuiti su server in tutto il mondo e accessibili tramite browser web.

##### Client, Server, Actor
Inoltre su ogni dispositivo di un sistema distribuito viene eseguito un programma, che può prendere uno dei seguenti nomi:
- Client: quando richiede un servizio (browser: edge, firefox, safari, chrome)
- Server: quando è fornitore di servizi (esempio Tomcat, offre servizio WEB)
- Actor: Server + Client


# Evoluzione dei sistemi distribuiti e dei modelli architetturali

### Introduzione
Il sistema distribuito è ottenuto dalla connessione di più personal computer che negli anni hanno avuto una crescita tecnologica legata alla <u>legge Moore.</u>.

>«La complessità di un [microcircuito](https://it.wikipedia.org/wiki/Microelettronica "Microelettronica"), misurata ad esempio tramite il numero di [transistor](https://it.wikipedia.org/wiki/Transistor "Transistor") per [chip](https://it.wikipedia.org/wiki/Circuito_integrato "Circuito integrato"), raddoppia ogni 18 mesi (e quadruplica quindi ogni 3 anni).»

\- Legge di Moore

Siamo però arrivati a limiti fisici in quanto è impossibile rimpicciolire ancor di più i transistor, quindi dobbiamo muoverci in nuove direzioni per migliorare la potenza di calcolo.

### Cosa fare dunque? (Soluzione lato Hardware)
Si è passati quindi a combinare, nel caso di Flynn, flusso di dati e flusso delle istruzioni cosi da avere 4 principali tipologie di architetture:
- **[[#SISD]]** (Single Instruction Single Data): flusso di istruzioni unico e flusso di dati unico;
- **[[#SIMD]]** (Single Instruction Multiple Data): flusso di istruzioni unico e flusso di dati multiplo;
- [[#MISD]] (Multiple Instruction Single Data): flusso istruzioni multiplo e flusso dati unico;
- **[[#MIMD]]** (Multiple Instruction Multiple Data): flusso istruzioni multiplo e flusso dati multiplo.

##### SISD
Il flusso di istruzioni è unico e quindi viene eseguito un solo programma alla volta:
Fanno parte:
- la macchina di Von Neumann
- personal computer
- mainframe
- **In genere tutti quei dispositivi con 1 CPU**

##### SIMD
L’elaborazione avviene su più flussi dati in contemporanea ma con un singolo flusso di istruzioni: generalmente sono presenti più processori
Utilizzati per calcoli vettoriali (array)

##### MISD
Esistono quindi più processori, ognuno con una propria memoria, la quale a sua volta avrà un proprio flusso di istruzioni che verranno eseguite sullo stesso flusso di dati.
Da ricordare quindi:
- Più processori
- Ogni processore con propria memoria

##### MIMD
L’architettura MIMD comprende tutte le tipologie di elaboratori composti da più unità centrali di elaborazione indipendenti che possono lavorare su stream di dati anch’essi indipendenti. 
Vengono classificati in: 
- macchine MIMD a memoria fisica condivisa, Multi processore
- macchine MIMD a memoria privata. Multi computer

### Cosa fare dunque? (Soluzione lato Software)
Per alleggerire il carico elaborativo dei serventi sono state introdotte le applicazioni multilivello, nelle quali avviene la separazione delle funzionalità logiche del software in più livelli. 
Questo software prende il nome di Middleware:
- si pone tra il sistema operativo e le applicazioni. 
- Svolge un ruolo cruciale nel facilitare la comunicazione e la cooperazione tra i vari componenti di un sistema distribuito

### (Da sapere se lo chiede)
##### Wearable computing
- usati quasi principalmente per scopi sanitari
- Smartwatch, sensori di movimento: tutti quei sensori indossabili





