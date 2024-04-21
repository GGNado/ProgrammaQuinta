# Introduzione
Il [[Database#Modello relazionale]] rappresenta i dati nella forma di tabelle bidimensionali, dove ogni tabella descrive qualcosa di esistente nel mondo reale. L'organizzazione dei dati nelle tabelle relazionali è conosciuta come **vista logica**, mentre il modo in cui il software del database salva fisicamente i dati sul disco fisso di un computer è noto come **vista interna**.

 Una tabella relazionale può essere immaginata come un file in cui i dati sono salvati sotto forma di colonne, chiamate **Attributi**, e righe, chiamate **Tuple**.
![[Screenshot 2024-01-11 alle 11.05.55.png]]
E la tabella è caratterizzata da elementi come:
- dominio ovvero l'insieme dei valori che possono essere presenti in una colonna.
- grado ovvero il numero delle colonne.
- cardinalità ovvero il numero delle righe.
# Attributi
Per ogni attributo è importante definire:
- il tipo di dato: quindi se è un valore decimale, intero, carattere, stringa ecc ecc
- la lunghezza: ad esempio un dato di 5 cifre o una parola di 20 lettere
- l'intervallo: ad esempio dei controlli di inserimento in fase di input dove controlliamo che un determinato valore che si sta inserendo rispecchi un intervallo di valori corretti (basta pensare all'età che non può essere negativa)
## Proprietà della Tabella relazionale
Una tabella rappresenta una relazione se ogni riga o tupla è univoca.
Per rendere queste tuple diverse fra loro, abbiamo bisogno delle [[#Chiavi]].
## Chiavi
Per essere sicuri di avere tuple tutte differenti si stabilisce di inserire in una tabella un attributo che prende il nome di chiave. Se non è presente un singolo attributo si possono prendere più attributi che formano una chiave composta.
Esistono diverse tipologie di chiavi:
- **Chiave artificiale**: il famoso ID che è un attributo che l'oggetto in questione non ha realmente ma viene dato per facilitare la distinzione tra le varie tuple. È un valore intero, che si autoincrementa ogni volta che viene aggiunto una tupla.
- **Chiave primaria e candidata**: sarebbero quegli attributi di una tupla che identificano l'elemento in maniera univoca come ad esempio ISBN oppure la matricola.
- **Chiave esterna**: una chiave particolare che ci permette di mettere in relazione diverse tabelle chiamata FK o Foreign Key
# Valori null e di default
Molti casi è possibile che è in una tupla ci siano dei valori non definiti, ed essendo che tutta la struttura deve avere dei valori omogenei si inseriscono dei valori speciali come ad esempio il valore **NULL** che indica l'assenza di un dato oppure in alcuni casi si preferisce usare il valore di default come ad esempio nell'attributo totale fattura che non sarà inizializzato a Null ma a zero. 
Per lavorare con i NULL si usa l'operatore di confronto IS:
- Per vedere se un attributo è NULL:  attributo IS NULL
- Per vedere se un attributo non è NULL: attributo IS NOT NULL
# Classificazione degli attributi
Gli attributi possono avere diverse classificazione. Possono essere:
- descrittori: descrivono una caratteristica non unica di un'entità
- identificatori: chiamate più comunemente chiavi, identificano in maniera univoca una tupla
Quindi in breve i descrittori descrivono la caratteristica della istanza che può essere ripetuta mentre gli identificatori la individuano in maniera univoca e distinta. 

Un'altra classificazione può essere: 
- scalari che possono avere un solo valore: come ad esempio nome, cognome
- multipli che possono avere più valori: come ad esempio linguaParlata

Un'ultima classificazione può esistere in base alla tipo dell'attributo:

| Tipo              | Descrizione                                      | Esempi                          |
| ----------------- | ------------------------------------------------ | ------------------------------- |
| Univoco           | Tutte le tuple hanno valore diverso              | Targa, codice Fiscale           |
| Generico          | Opposto di Univoco                               | colore, libri Letti             |
| Atomico           | Non scomponibile                                 | Cap, strada                     |
| Composto          | Costituito da più elementi, contrario di atomico | indirizzo di casa,              |
| Opzionale         | Che può non esistere                             | Numero di telefono.             |
| Obbligatorio      | Il contrario di opzionale, deve sempre esistere  | Partita iva, nome               |
| Statico o Costate | Valori che non subiranno cambiamenti             | Codice Fiscale, Data di nascita |
| Modificabile      | I suoi valori possono cambiare                   | età, peso, altezza              |
| Calcolato         | Valore che esce in base a un algoritmo           | scontrino, IMC, PrezzoScontato                          |
| Esplicito                  | Opposto di calcolato                                                 | Prezzo                                 |

