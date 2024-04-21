## Introduzione
Il DES è un algoritmo di crittografia a chiave simmetrica, il che significa che la stessa chiave viene utilizzata per cifrare e decifrare i dati. 
## Caratteristiche principali:

- **Blocchi di 64 bit:** Il DES opera su blocchi di dati di 64 bit.
- **Chiave di 56 bit:** La chiave di cifratura del DES è di 56 bit, il che significa che esistono 2^56 possibili chiavi diverse.

## Funzionamento dell'algoritmo:

1. **Permutazione iniziale:** Il blocco di dati in chiaro viene sottoposto a una permutazione iniziale che modifica l'ordine dei bit.
2. **Divisione in blocchi da 32 bit:** Il blocco di dati viene diviso in due blocchi da 32 bit, chiamati L e R.
3. **Round:** I 16 round vengono eseguiti uno dopo l'altro. In ogni round:
    - La funzione f viene applicata al blocco R, utilizzando la sottochiave del round corrente.
    - Il risultato della funzione f viene combinato con il blocco L tramite un'operazione XOR.
    - I blocchi L e R vengono scambiati.
4. **Permutazione finale:** Il blocco di dati viene sottoposto a una permutazione finale che inverte l'ordine dei bit della permutazione iniziale.

**Sicurezza del DES:**

Con gli anni è stato violato più volte e una soluzione nel breve periodo è stata trovata con il triple DES, quindi eseguire il DES 3 volte

## Esempio

Supponiamo di voler cifrare il messaggio "CIAO" con la chiave "123456".

1. Il messaggio viene convertito in bit: 01000011 01101000 01101001 01100101.
2. Il blocco di dati viene sottoposto a una permutazione iniziale.
3. Il blocco di dati viene diviso in due blocchi da 32 bit: L = 01000011 01101000 e R = 01101001 01100101.
4. Vengono eseguiti 16 round.
5. Il blocco di dati viene sottoposto a una permutazione finale.

Il messaggio cifrato è: 11001001 10111011 11000100 10011101.