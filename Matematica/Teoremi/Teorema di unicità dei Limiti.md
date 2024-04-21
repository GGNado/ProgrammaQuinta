Se Il limite che tende a X di C è uguale a L (quindi a un numero) $$lim_{x \to c} f(x) = l$$
La nostra **l** sarà unica 
- Questo teorema si dimostra per assurdo, ovvero si nega la tesi ottenendo una affermazione non vera.

# Come si dimostra
Supponiamo che la funziona F(X) ammette due limiti
1)  limite di X che tende a C uguale a L $$lim_{x \to c} f(x) = l$$
2) e  limite di X che tende a C uguale a M $$lim_{x \to c} f(x) = m$$
e possiamo dire che m e l sono numeri diversi con m > l (o l > m, non cambia nulla, uno dei due è perforza più grande dell'altro)
## Per definizione
avremo:
- primo limite: Per ogni E maggiore di 0 esiste un intorno di C tale che per ogni X appartenente all'introno di C escludendo C tale che il valore assoluto di F(x)-l < E
- secondo limite: Per ogni E maggiore di 0 esiste un intorno di C tale che per ogni X appartenente all'introno di C escludendo C tale che il valore assoluto di F(x)-m < E
e quindi E = (m-l)/2
da cui segue:
- primo limite: l-E < f(x) < l+E e questo è il primo intorno
- secondo limite:  m-E < f(x) < m+E e questo è il primo intorno
Ora indico con H intersezione tra il primo e il secondo intorno: H = Intorno1 Intersecato Intorno2
Considero l'intorno H tale che: m-E < F(x) < l+E
allora facendo tutti i calcoli, si arriva alla conclusione che (m-l)/2 < E ma siamo arrivati ad un assurdo perchè io in precedenza avevo dichiarato che E era UGUALE ad (m-l)/2
