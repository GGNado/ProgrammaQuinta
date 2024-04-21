- Json web Token
- Client manda informazioni (username e psw), una volta identificato si genera il token
- Ha una scadenza
- Tecnica di autenticazione chiamata AUTH

# Struttura
- Header: troviamo il tipo di algoritmo usato
- Payload: troviamo i dati 
- Signature: la firma serve per verificare l'integrità del token

## Token
- Bearer token: utilizzato nelle richieste HTTP per autenticare l'identità di un utente.
- JWT: utilizzato in tecnologie web specifiche