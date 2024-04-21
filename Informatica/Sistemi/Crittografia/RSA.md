## Algoritmo RSA a chiave asimmetrica:

**Introduzione:**

L'algoritmo RSA (Rivest-Shamir-Adleman) è un algoritmo di crittografia a chiave asimmetrica, noto anche come crittografia a chiave pubblica.

**Caratteristiche:**

- Utilizza due chiavi distinte: una chiave pubblica e una chiave privata.
- La chiave pubblica è distribuita liberamente.
- La chiave privata è segreta e conosciuta solo dal proprietario.
- La chiave pubblica serve per cifrare i messaggi.
- La chiave privata serve per decifrare i messaggi.

**Funzionamento:**

1. **Generazione delle chiavi:**
    - Si scelgono due numeri primi grandi, p e q.
    - Si calcola il modulo n = p * q.
    - Si sceglie un numero e tale che 1 < e < φ(n) e gcd(e, φ(n)) = 1.
    - La chiave pubblica è (n, e).
    - La chiave privata è (n, d), dove d è l'inverso modulare di e rispetto a φ(n).
2. **Cifratura:**
    - Il messaggio in chiaro M viene convertito in un numero m, 0 < m < n.
    - Il messaggio cifrato C viene calcolato come C = m^e mod n.
3. **Decifratura:**
    - Il messaggio cifrato C viene decifrato come m = C^d mod n.
    - Il messaggio in chiaro M viene ottenuto convertendo m da un numero a un testo.

**Sicurezza:**

- La sicurezza dell'algoritmo RSA si basa sulla difficoltà di fattorizzare numeri grandi.
- Se un attaccante riesce a fattorizzare n, può ricavare la chiave privata dalla chiave pubblica.
- La lunghezza di n determina la sicurezza dell'algoritmo.

**Esempio:**

Supponiamo di voler cifrare il messaggio "CIAO" con la chiave pubblica (n, e) = (101, 7).

1. Convertiamo il messaggio in chiaro in un numero: M = 3 * 26^2 + 9 * 26 + 1 + 15 = 2019.
2. Calcoliamo il messaggio cifrato: C = 2019^7 mod 101 = 86.
3. Per decifrare il messaggio, il destinatario utilizza la chiave privata (n, d) = (101, 23).
4. Calcola il messaggio in chiaro: m = 86^23 mod 101 = 2019.
5. Converte il numero in messaggio in chiaro: M = "CIAO".

**Vantaggi:**

- Elevata sicurezza.
- Semplicità di utilizzo.
- Ampia diffusione.

**Svantaggi:**

- Calcolo computazionalmente costoso.
- Non adatto per la crittografia di grandi quantità di dati.

**Applicazioni:**

- Firma digitale.
- Crittografia di email.
- VPN.
- e-commerce.
