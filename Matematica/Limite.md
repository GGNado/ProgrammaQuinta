## Info Generale 
- Ci aspettiamo una criticità da una funzione, un valore può creare problemi
- Descrivono cosa accade a una funzione quando si avvicina a un certo valore.
- Capire cosa succede intorno a quel numero 

$$lim_{x \to 2} f(x) = l$$
- La funzione f(x) ha per limite il numero reale detto L

# Interrogazione
### Che cos'è il limite? 
- l **limite di una funzione è** **un** operatore, che permette **di** studiare il comportamento **di una funzione** nell'[[Intervalli#Intorno di un numero]] (X tende a ->), e grazie al quale possiamo stabilire a quale valore tende la **funzione** man mano che i valori della variabile indipendente **si** approssimano a quel punto. 
- per ogni E > 0 esiste un intorno di X0 tale che per ogni X che appartiene all'intorno di X0 escluso X0 si ha valore assoluto di F(x) - l
### Come si disegna?
1) Prima di tutto ci serve una funzione F(X) e cerchiamo di semplificarla (quindi se tipo è y = 2x + 2x + 2 - 1 -> y = 4x + 1) e vogliamo studiare il comportamento di X -> 2
2) Ora creiamo la tabella x e y:

| X   | Y   |
| --- | --- |
| -1  | -3  |
| 0   | 1   |
| 1   | 5   |
| 2   | 9   |

3) Fai grafico e unisci con una linea ma <u>se il valore X non è compreso nel dominio interrompi la linea</u> altrimenti falla continua.

### Come studiarla? Metodo 1
Faccia finta di avere y = 2x e con Dominio tutto R - {2}
1) quindi abbiamo una tabella del genere: 

| X   | Y   |
| --- | --- |
| 1   | 2   |
| 2   | ??  |
| 3   | 6   |

2) **Cosa succede tra 1 - 2 & 2 -3?**
Diamo alla variabile X dei valori che si avvicinano sempre di più:

| X   | 1,9 | 1,99 | 2   | 2,01 | 2,1 |
| --- | --- | ---- | --- | ---- | --- |
| Y   | 3,8 | 3,89 | ??? | 4,02 | 4,02    |

Notiamo che man mano che ci avviciniamo a 2, la y si avvicina al 4.
Più in generale, <u>se prendiamo un qualunque valore di x in un intorno di 2 sempre più piccolo, allora f(x) si trova sempre più vicino a 4</u> 

### Come studiarla? Metodo 2
#### 1 caso
Possiamo esprimere lo stesso concetto anche in un altro modo: considerato un qualunque [[Intervalli#Intorno circolare]] di 4 di ampiezza E esisterà sempre un intorno di 2 i cui punti x (con x != 2) hanno immagine contenuta nell'intorno.

I punti di tale intorno sono quei valori di x che soddisfano la disequazione:
$$| f(x)-4 | <E$$
ipotizzando che il modulo sia: 
$$| x+2 | <E $$
ricorda che ci sarà un sistema del tipo:
$$\begin{cases} x<E-2\\ x > -E -2 \end{cases}$$
ora puoi scrivere sotto forma di intervallo tutto cio:
$$-E-2<x<E-2$$


#
### Spiegazione della prof

Considero la funzione

![[Screenshot 2023-10-06 alle 11.12.17.png]]
Quindi y = 2x

| x   | y   |
| --- | --- |
| 1   | 2   |
| 2   | 4   |
| 3   | ?   |
| 4   | 8   |
| 5   | 10    |

- In 3 la funzione non esiste, possiamo definirlo anche punto di accumolo
Vogliamo studiare la funzione vicino a questo valore quindi cerchiamo dei valori prossimi al 3:

![[Screenshot 2023-10-06 alle 11.22.18.png]]

Eseguiamo la verifica:
1) prendiamo numero reale positivo arbitrario, e la indichiamo con E
2) considero un [intorno circolare] di 6 (in questo caso) )6-E, 6+E(
3) quindi possiamo dire che la mia funzione sarà sempre compresa tra 6+-E quindi   6-E < F(x) < 6+E
4) Questo non è altro che la lettura del valore assoluto di |Fx-6|< E
5) Chi era F(x)? 2x quindi: |2x-6| < E
6) essendo il 2 positivo lo porto fuori: 2|x-3|< E
7) faccio fratto 2 e levo il 2: |x-3| < E
8) tolgo il valore assoluto mettendo a sistema: {x-3 < E} e {x-3 > -E}
9) quindi -E < x-3 < E
10) portiamo la X a sinistra e destra: 3-E < X < 3+E
11) HO PROVATO **CHE ESISTE UN INTORNO CIRCOLARE DEL PUNTO 3** 

Conclusione
- Qualunche sia il numero E, mi considero un intorno circolare di 6 in corrispondenza del quale scopro che esiste un intorno circolare del punto 3 tale che qualsiasi E che prendo dell'introno di x, ma diverso da 3, si ha che il valore assoluto di Fx - 6 è minore di E. 
- Quando x si avvicina a 3, F(x) si avvicina a 6 == detto in matematica: quando x tende a 3, F(x) tende a 6
- Il limite della mia funzione F(x) avviene quando X <u>tende</u> a 3: lim f(x) = 6


ESEMPI:
- [Esempio 1]