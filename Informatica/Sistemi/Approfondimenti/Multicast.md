Il **multicast** è utilizzato per trasmettere informazioni contemporaneamente a più host (relazione one-to-many). A differenza dell'[[Unicast]], il multicast supporta la comunicazione uno-a-molti, consentendo a un insieme di processi di formare un gruppo di multicast.
## Caratteristiche del Multicast:

- **Relazione One-to-Many:** Un messaggio inviato da un processo a un gruppo multicast viene recapitato a tutti gli altri partecipanti appartenenti al gruppo.
- **Applicazioni Tipiche:**
    - **Usenet News:** Pubblicazione e diffusione di nuove notizie in tempo reale.
    - **Videoconferenze:** Ogni host genera un segnale audio-video ricevuto dagli host associati ai partecipanti alla videoconferenza.
    - **Massive Multiplayer Games:** Giochi online in cui un elevato numero di giocatori interagiscono in un mondo virtuale.
    - **DNS (Domain Name System):** Aggiornamenti delle tabelle di naming inviati a gruppi di DNS.
    - **Altre Applicazioni:** Chat, instant messaging, applicazioni P2P, ecc.
- **Protocollo IGMP:** Internet Group Management Protocol, utilizzato per gestire la costituzione dei gruppi multicast.
- **API Multicast:** Le API devono includere primitive per unirsi a un gruppo, lasciare un gruppo, spedire e ricevere messaggi indirizzati a un gruppo del quale l'host fa parte.