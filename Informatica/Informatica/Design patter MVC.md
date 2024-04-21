- Formato da 3 parti
## Model (Modello)
- **Descrizione:** Rappresenta i dati e la logica di business dell'applicazione. Il Modello gestisce l'accesso e la manipolazione dei dati, nonché la logica dell'applicazione.
- **Responsabilità:**
  - Archivia lo stato dell'applicazione.
  - Definisce le regole di business e la logica di manipolazione dei dati.
  - Notifica le viste in caso di modifiche allo stato.

## View (Vista)
- **Descrizione:** Rappresenta l'interfaccia utente dell'applicazione. La Vista si occupa di visualizzare i dati al cliente e di interpretare l'input dell'utente.
- **Responsabilità:**
  - Presenta i dati forniti dal Modello.
  - Inoltra l'input dell'utente al Controller.
  - Può avere la capacità di osservare il Modello per rilevare cambiamenti e aggiornare automaticamente la presentazione.

## Controller (Controllore)
- **Descrizione:** Gestisce gli input dell'utente e modifica lo stato del Modello e della Vista di conseguenza. Il Controllore funge da intermediario tra Modello e Vista.
- **Responsabilità:**
  - Riceve l'input dell'utente dalla Vista.
  - Interagisce con il Modello per effettuare le modifiche necessarie.
  - Aggiorna la Vista per riflettere le modifiche nel Modello.

**Flusso di lavoro tipico di MVC:**
1. L'utente interagisce con l'interfaccia utente (View).
2. La View invia l'input dell'utente al Controller.
3. Il Controller processa l'input, interagisce con il Modello per apportare le modifiche necessarie.
4. Il Modello aggiorna il proprio stato e notifica la View di eventuali cambiamenti.
5. La View ottiene i dati aggiornati dal Modello e si aggiorna di conseguenza.
### Altri pattern Opzionali
#### Singleton Pattern
- **Descrizione:** Assicura che una classe abbia una sola istanza e fornisce un punto di accesso globale a quella istanza.
- **Utilizzo Tipico:** Limitare l'istanza di una classe a una sola.

#### Factory Method Pattern
- **Descrizione:** Definisce un'interfaccia per la creazione di un oggetto, lasciando alle sottoclassi la decisione su quale classe istanziare.
- **Utilizzo Tipico:** Creare oggetti senza specificare la classe esatta.

#### Observer Pattern
- **Descrizione:** Definisce una dipendenza uno-a-molti tra oggetti, in modo che quando uno cambia stato, tutti i suoi dipendenti vengano notificati e aggiornati.
- **Utilizzo Tipico:** Notificare oggetti di cambiamenti di stato in altri oggetti.

#### Strategy Pattern
- **Descrizione:** Definisce una famiglia di algoritmi, incapsula ciascuno di essi e li rende intercambiabili.
- **Utilizzo Tipico:** Variare l'algoritmo indipendentemente dal cliente.

#### Decorator Pattern
- **Descrizione:** Attacca dinamicamente responsabilità aggiuntive a un oggetto, fornendo un'alternativa flessibile alla subclassificazione.
- **Utilizzo Tipico:** Estendere le funzionalità di una classe in modo flessibile.

#### Command Pattern
- **Descrizione:** Incapsula una richiesta come un oggetto, consentendo di parametrizzare client con richieste diverse, accodare richieste e supportare operazioni annullabili.
- **Utilizzo Tipico:** Parametrizzare oggetti con operazioni, accodare richieste o supportare operazioni annullabili.

#### Adapter Pattern
- **Descrizione:** Converte l'interfaccia di una classe in un'altra interfaccia che un cliente si aspetta.
- **Utilizzo Tipico:** Far collaborare classi con interfacce incompatibili.

#### Composite Pattern
- **Descrizione:** Compone oggetti in strutture ad albero per rappresentare parti/interi del sistema, consentendo ai client di trattare oggetti singoli e composizioni in modo uniforme.
- **Utilizzo Tipico:** Trattare oggetti singoli e composizioni in modo uniforme.
