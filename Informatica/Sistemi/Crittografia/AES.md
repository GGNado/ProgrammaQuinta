## AES (Advanced Encryption Standard)

## Introduzione:

- Nasce come soluzione al [[DES]]
- L'AES è un algoritmo simmetrico che processa blocchi a 128 bit.
- Opera con chiavi a 128, 192 e 256 bit.
- Si stima che un calcolatore può individuare una chiave DES a 56 bit in 1 sec.; invece per violare una chiave AES a 128 bit ci impiegherebbe 149 miliardi di anni.

## Caratteristiche:

- AES è basato sull'algoritmo di Rijndael.
- Tre caratteristiche fondamentali:
    - Resistenza contro tutti gli attacchi
    - Velocità e compattezza del codice su un'ampia gamma di piattaforme
    - Semplicità progettuale
- Utilizza blocchi a 128 bit.
- Chiavi a 128, 192 e 256 bit.

## Trasformazioni:
AES usa quattro trasformazioni per ogni round:
- Sostituzione bytes: Sostituisce ciascun elemento della matrice tramite una tabella S-box
- Permutazione: detta ShiftRows, la prima riga rimane invariata, mentre le altre righe subiscono uno scorrimento circolare a sinistra di uno
- Mixing Columns: Trasforma ciascuna colonna della matrice ad una nuova colonna.
- KeyAdding: Ogni byte viene combinato in XOR con la chiave da 128 bit (16 byte). Ad ogni round la chiave aggiunta è diversa e ricavata dalla precedenti ricorsivamente.

## Vantaggi:

- AES è il primo standard approvato da NSA per comunicazioni top-secret.
- Ad oggi, non sono conosciuti attacchi in grado di violarlo.
- Più sicuro del DES grazie alla chiave di lunghezza maggiore.
- Gli algoritmi usati sono semplici da implementare.
- Funzionano su processori poco costosi e con poca memoria.