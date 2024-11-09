Generalmente l’obiettivo di un modello di sistema è di essere **corretto**, **completo**, **consistente** e **non ambiguo**.

Gli sviluppatori devono

- formalizzare la specifica delle richieste prodotta durante la fase di **raccolta dei requisiti**
- validazione, correzione e chiarimento questa specifica
- ulteriore considerazione dettagliata di **condizioni limite e casi eccezionali**

  

**Clienti e utenti sono ulteriormente coinvolti solo se cambiano le richieste o c’è bisogno di maggiori informazioni.**

  

### Passaggi

1. Viene costruito un **modello che descrive il dominio di applicazione**
    1. _Il modello di analisi relativo all’orogologio descrive come l’orologio rappresenta il tempo_
2. Viene ampliato il modello di analisi **includendo una descrizione di come gli utenti interagiscono per manipolare il modello del dominio.**
    1. _Come una persona resetta l’ora dell’orologio? O il giorno della settimana?_
3. Il modello di analisi + richieste non funzionali = **definizione architettura del sistema**

  

# Prima parte

## Ambiguità

Le specifiche contengono ambiguità di vario genere, e la loro **formalizzazione** serve ad individuare esse, oltre che **incosistenze** oppure **omissioni.**

Una volta che si trovano gli errori, occorre risolverli **ottenendo ulteriori informazioni** da cliente e utenti.

**Analisi delle richieste** e **identificazione delle richieste** sono attività iterative  
e incrementali che avvengono in concorrenza.  

## Analisi dei requisiti

Ha il compito di tradurre **specifiche dei requisiti** in un modello formale (o semi-formale).

Con questo processo si scoprono errori e si conosce di più dell’obiettivo.

Il **modello di analisi** è composto da:

- **Modello funzionale**
    - Use Cases
    - Scenari
- **Modello degli oggetti di analisi**
    - Diagramma delle Classi
    - Diagramma degli Oggetti
- **Modello dinamico**
    - Statechart
    - Sequence Diagram

![[image 68.png]]

![[image 69.png]]

![[image 70.png]]

  

## Concetti di Analisi

### Il modello degli oggetti di analisi

Fa uso dell’**UML** per rappresentare il sistema dal punto di vista dell’utente, focalizzandosi principalmente sui concetti **manipolabili dal sistema**.

Inoltre è una forma visuale.

### Il modello dinamico

Si focalizza sul comportamento del sistema, specificatamente descrive le interazioni fra i vari componenti dello stesso (con il **Sequence Diagram**) e il comportamento in solitaria di ognuno o di oggetti comunque strettamente accoppiati (con **StateChart**).

### Oggetti Entity, Boundary e Control

Tutti i sistemi hanno al loro interno questi oggetti.

**\Entity:**

informazione persistente (oggetti del dominio di applicazione)

\**Boundary:**

interazioni tra attori e il sistema (oggetti interfaccia utente, oggetti interfaccia dispositivi, oggetti interfaccia di sistema)

\**Control:**

realizzano gli use case (controllo task fatte dal sistema, logica e determinano l’ordine dell’interazione con gli oggetti)

_Esempio: Orologio_

- Year, Month e Day sono oggetti Entity
- Button e LCDDisplay sono oggetti Boundary
- ChangeDateControl è un oggetto Control, che rappresenta l’attività di cambiare la data  
    premendo combinazioni di bottoni  
    

E’ opportuno usare convenzioni sui nomi:

- Gli oggetti control possono avere il suffisso Control
- Gli oggetti boundary dovrebbero avere nomi che ricordano aspetti  
    dell’interfaccia (es. suffisso Form, Button, ecc)  
    

![[image 71.png]]

### Use Cases

Formati come segue:

- Nome
- Attori Partecipanti
- Eccezioni
- Entry Condition
- Flow of Events
- Exit Condition
- Vincoli

  

Esempio:

![[image 72.png]]

  

### Identificare oggetti ENTITY

In aiuto a quest’attività, si usa _**L’euristica di Abbott**_, che si basa sul linguaggio naturale per identificare oggetti, attributi, associazioni dalla specifica dei requisiti, mappando il linguaggio parlato alle componenti.

Sfortunatamente, proprio per questa semplicità, esso risulta essere anche **molto inaccurato**, quindi ci serve solo come idea iniziale.

_Euristica di Abbott_

![[image 73.png]]

  

### Euristica per identificare gli oggetti ENTITY

Aggiungere termini per capire la dinamica degli use case, è decisamente di aiuto, così come trovare termini ricorrenti, entità ed attività del mondo reale che il sistema considera.

Importanti anche le sorgenti e destinazioni di dati.

Per ogni oggetto identificato:

- Nome unico
    - Stesso nome fra utenti e specialisti
- Breve descrizione
- Si individuano attributi e responsabilità (si predilige quelli non ovvi)
- Processo iterativo e revisioni

  

Esempi:

![[image 74.png]]

  

Nel dominio dello use case ReportEmergency si riconoscono i seguenti oggetti

- Dispatcher
    - “Ufficio di polizia che gestisce Incidenti. Un Dispatcher apre,  
        documenta e chiude Incident in risposta a Report di Emergenza  
        e altra comunicazione con FieldOfficers. I Dispatcher sono  
        identificati dal numero del badge.”  
        
- FieldOfficer
    - “Un funzionario di un ufficio di polizia o dei vigili del fuoco in  
        servizio. Un FieldOfficer può essere allocato al più ad un Incident  
        alla volta. I FieldOfficer sono identificati da badge.”  
        
- Incident
    - Situazione che richiede l’attenzione di un FieldOfficer. Un  
        Incident può essere riportato nel sistema da un FieldOfficer o da  
        qualcuno anche esterno al sistema. Un Incident è composto da  
        una descrizione, una risposta, uno status (aperto, chiuso,  
        documentato), una locazione, e un numero di FieldOfficer.  
        
- EmergencyReport
    - Che non è denominato esplicitamente nello use case
    - Se ne deduce l’esistenza dal colloquio col cliente, per esempio
    - “Report iniziale su un Incident da un FieldOfficer a un Disptacher.  
        Un EmergencyReport solitamente determina la creazione di un  
        Incident da parte di un Dispatcher. Un EmergencyReport è  
        composto da un livello di emergenza, un tipo (fuoco, stradale, ..),  
        un luogo e una descrizione.”  
        

  

### Identificare gli oggetti BOUNDARY

Rappresentano l’interfaccia del sistema con gli attori. La modellano senza descriverne gli aspetti visuali. (Le grafiche vengono create con sistema prototipale e iterativo)

- In ogni use case ogni attore interagisce almeno con un oggetto Boundary
- L’oggetto Boundary colleziona informazioni dall’attore e la traduce in qualcosa interpretabile da Control e Entity

![[image 75.png]]

  

### Euristiche per identificare gli oggetti BOUNDARY

- Identificare l’UI tramite cui l’utente inizia l’use case
    - ReportEmergencyButton
- Identificare form di inserimento per contattare il sistema
    - ReportEmergencyForm
- Identificare avvisi e messaggi che il sistema usa per rispondere all’utente
    - AcknolewdgmentNotice
- Quando più attori sono presenti nello stesso use case, identificare attori che sono terminali in modo specifico così da far riferimento all’UI
    - DispatcherStation
- NON MODELLARE ASPETTI VISUALI UI (meglio usare mock-ups)
- Usare termini dell’utente finale per descrivere l’interfaccia

  

### Identificare gli oggetti CONTROL

Responsabili della coordinazione fra Boundary e Entity collezionando informazioni dal primo per mandarle al secondo.

Di solito non hanno una controparte nel mondo reale.

- Creato all’inizio dello use case e distrutto alla fine di esso

![[image 76.png]]

  

### Euristiche per identificare gli oggetti CONTROL

- Un oggetto Control per ogni use case
- Un oggetto Control per ogni attore in uno use case
- La vita di un oggetto Control dovrebbe corrispondere alla durata di uno use case o di una sessione utente.
    - Se risulta difficile identificarne inizio e fine, il corrispondente use case non ha entry e exit conditions ben definite.

  

Per il dominio di esempio ReportEmergency

- Lo use case ha un oggetto control per ogni attore
    - ReportEmergencyControl per il _FieldOfficer_
    - ManageEmergencyControl per _Dispatcher_
    - Decisione di due control diversi basata su due sottoinsiemi diversi
        - FieldOfficerStation
        - DispatcherStation
- Mettendo oggetti di Boundary, Entity e Control si è passato da un flusso di eventi ad una struttura vera e propria

  

  

## Mappare use case ad oggetti con Sequence Diagram

Un sequence diagram mostra come il comportamento di uno use case è distribuito tra gli oggetti che ne fanno parte, ogni oggetto ha infatti una propria responsabilità (in termini di insieme di operazioni).

Inoltre spiega la sequenza di interazioni tra gli oggetti dello use case.

Pero’ non è adatto alla comunicazione col cliente ed è quindi usabile solo per gli esperti, essendo per essi più preciso degli use case stessi e **individua oggetti mancanti**.

  

### Sequence Diagram

Diviso in colonne, ogni colonna rappresenta un oggetto dello use case

- Prima colonna a sinistra
    - Attore che inizia lo sue case
- Seconda colonna
    - Oggetto Boundary con cui l’attore interagisce per iniziare lo use case
- Terza colonna
    - Oggetto Control che gestisce il resto dello use case

Gli oggetti Control, inoltre, creano altri Boundary e possono interagire con altri Control.

- Frecce orizzontali
    - Trovate tra colonne, sono messaggi o stimoli tra oggetti
        - Un messaggio attiva un’operazione, rappresentata con rettangolo la cui lunghezza temporale in cui essa è attiva.

  

La vita di tutti gli oggetti del diagramma inizia da sopra e continua andando verso giù.

- Sopra a tutto si trovano gli oggetti che esistono prima del primo messaggio
- Oggetti creati durante interazione sono riconosciuti con <<create>>
- Oggetti distrutti avranno una croce sopra di essi
- La linea tratteggiata indica il tempo in cui l’oggetto puo’ ricevere messaggi

  

Esempio per ReportEmergency

![[image 77.png]]

Possiamo determinare già che lo use case è incompleto, infatti

- Menziona l’esistenza di un messaggio di notifica, che esiste solo per astratto e non ha informazioni
    - Con l’oggetto _Acknowledgment_ (determinato col cliente) aggiunto al modello di analisi, il problema viene risolto
        
        - Creato prima del Boundary “AcknowledgmentNotice”
        
        ![[image 78.png]]
        

  

Lo use case ora raffinato sarà:

![[image 79.png]]

![[image 80.png]]

![[image 81.png]]

  

### Euristiche per il Sequence Diagram

- 1° colonna = attore che inizia use case
- 2° colonna = oggetto Boundary (usato per iniziare lo use case)
- 3° colonna = oggetto Control che gestisce lo use case
- I Control sono creati dai Boundary che iniziano l’use case
    - Entrambi accedono alle Entity
    - Boundary successivi sono creati dai Control creati
    - Entity non accede mai a Control e Boundary, così non si creano dipendenze e le Entity possono essere condivisi fra più use cases

  

### Oggetto Responsabilità

Il sequence diagram richiede la spartizione delle responsabilità dello use case fra i vari oggetti che ne fanno parte.

Queste responsabilità prendono la forma di operazioni, e vengono assegnate agli oggetti stessi.

- Possono essere condivise fra use cases per eliminare ridondanza e migliore consistenza
- Durante l’analisi, i sequence diagrams si incentrano su un comportamento di alto livello e l’implementazione va quindi considerata esternamente ad esso

  

Tipi di Responsabilità:

- **Pre-condizione**
    - Condizioni che le operazioni devono rispettare per ottenere il corretto risultato
- **Post-condizione**
    - Condizione che devono essere garantite vere dopo l’operazione
- **Class invariant (?)**
    - Condizione che deve rimanere sempre vera senza nessuna eccezione per tutte le istanze delle classi

Tutte quelle di sopra raggruppate creano il **Contract.**

  

### Ulteriori considerazioni

Disegnare un Sequence Diagram è difficile, quindi dovrebbe essere usato solo per problematiche il cui funzionamento non è ben specificato.

  

### Cross-checking

Come già citato, il Sequence Diagram è molto utile a specificare comportamenti e a trovare parti mancanti. Molte informazioni che possiamo ricavare sono:

- _Quali use cases creano questo use case e quali attori accedono alle sue informazioni?_
- _Quali use cases modificano e eliminano oggetti? Quali attori iniziano questi use cases?_
- _Questo oggetto è necessario?_

  

  

## Class Diagram

Il sequence diagram illustra le interazioni tra oggetti

Il class diagram mostra le relazioni tramite Associazioni, Ereditarietà e Aggregazione

Con le associazioni possiamo ulteriormente evidenziare casi limite, tipo che l’EmergencyReport è scritto da un solo FieldOfficer.

Nel caso in cui però possano più di uno oppure da anonimi, bisogna formulare altri casi, parlandone con il cliente in fase di analisi.

  

![[image 82.png]]

  

Rappresenta la struttura del sistema ed è usato

- Durante l’analisi dei requisiti per modellare il dominio del problema
- Durante il system design per modellare sottosistemi e interfacce
- Durante il design di oggetti per modellare le classi

  

### Classi

![[image 83.png]]

  

Rappresenta un concetto che incapsula stato (**attributi**) e comportamento (**operazioni**).

- Ogni attributo ha un tipo
- Ogni operazione ha un segno distintivo

L’unica informazione obbligatoria è il nome della classe.

  

### Istanze

![[image 84.png]]

  

Rappresenta un fenomeno, il cui nome è sottolineato e contenente il nome della classe.

Gli attributi sono i valori.

  

### Attori vs Istanze vs Oggetti

Differenze fra attori, classi e oggetti:

- Attore
    - Entità fuori al sistema con cui interagisce
- Classe
    - Un modello di astrazione per le entità del dominio del problema
        - Modellazione dentro al sistema
- Oggetto
    - Istanza specifica della classe

  

### Associazioni

![[image 85.png]]

Relazioni fra classi.

- Link
    - Connessione tra istanze, come una tupla (definita anche come istanza di associazione)
- Associazione
    - Mapping bidirezionale che definisce un insieme di link (come una classe descrive un insieme di oggetti)
    - Esistono anche associazioni direzionali

  

Proprietà:

- Nome unico e identificabile
- Ruolo che identifica la funzione di ogni classe
- Molteplicità
    - 1-to-1
    - Many-to-1
    - 1-to-many
    - Many-to-many

  

![[image 86.png]]

  

### Euristiche per identificare le associazioni

- Esaminare i verbi nelle frasi
- Precisare i nomi delle associazioni e i ruoli
- Eliminare associazioni che sono ridondanti e ricavabili da altre
- Preoccuparsi della molteplicità delle associazioni solo quando l’insieme non è stabile
- Troppe associazioni = modello illegibile

  

Esempio:

![[image 87.png]]

  

Per un aiuto, queste sono le possibili molteplicità:

![[1_bdhU4W2R3LcnVi1fqAubUw.png]]

  

### Aggregazioni

“E’ parte di”.

Assegnata all’entità padre tramite un rombo vuoto.

![[image 88.png]]

  

Se non è sicuri che l’associazione che si sta descrivendo sia un’aggregazione (un concetto  
intero-parti) è meglio modellarla come associazione 1-Many e poi rivederla quando si ha maggiore conoscenza del dominio.  

**Aggregati e componenti:**

  

![[image 89.png]]

  

Composizione invece è quando i componenti non possono esistere senza aggregato.

![[image 90.png]]

  

### Eredità

![[image 91.png]]

  

Le classi figlie ereditano attributi e operazioni delle classi parente.

Elimina ridondanza.

  

### Generalizzazione e specializzazione

Generalizzazione

- Modellazione che identifica concetti astratti da quelli di più basso livello

Specializzazione

- Attività che identifica concetti più specifici da quelli di più alto livello

Assieme abbiamo la specifica di ereditarietà dei concetti.

  

### Gerarchia

![[image 92.png]]

  

Le classi condividono similarità preservando le loro differenze.

  

### Identificare attributi

Proprietà individuali degli oggetti, generalmente solo quelli essenziali come:

- Nome
- Breve descrizione
- Tipo per esprimere che valori può assumere

E non essendo direttamente legati alla funzionalità del sistema, possono essere aggiunti anche dopo la conclusione dell’analisi.

  

Esempio per EmergencyReport:

![[image 93.png]]

  

Si scelgono frasi possessive o aggettivi, e si usa anche memorizzare uno stato tramite un attributo dedicato.

  

### Pratica identificazione classe

  

![[image 94.png]]

  

![[image 95.png]]

  

1. Trovare nuovi oggetti
2. Iterare punto 1 per nomi, attributi e metodi

  

![[image 96.png]]

  

1. Trovare associazioni fra gli oggetti
2. Dare una label alle associazioni
3. Determinare la molteplicità

  

![[image 97.png]]

  

### Ulteriori considerazioni

![[image 98.png]]

  

Notazioni possibili:

![[image 99.png]]

  

  

# Statechart

Se i sequence diagram distribuiscono il comportamento tra i diversi oggetti del sistema rappresentando il punto di vista dell’utente, lo **statechart** rappresenta il comportamento di un singolo oggetto.

Pero’ è utile fare lo statechart di un oggetto solo se esso ha un ciclo di vita significativo.

Si usa maggiormente dunque per gli oggetti CONTROL, meno per gli ENTITY, e per niente per i BOUNDARY.

  

Esempio di statechart per Incident:

![[image 100.png]]

  

![[image 101.png]]

  

![[image 102.png]]

  

  

# Rivedere il modello di analisi

Essendo costruito incrementalmente e iterativamente, esso cambierà ad ogni iterazione in una versione più stabile di se stesso, per correttezza, completezza, consistenza e chiarezza.

- Domande per la **correttezza**
    - _Il glossario è comprensibile per gli utenti?_
    - _Le classi astratte corrispondono a concetti di alto livello?_
    - _Tutte le descrizioni concordano con le definizioni degli utenti?_
    - _Oggetti Entity e Boundary hanno nomi significativi?_
    - _Oggetti Control e use cases sono nominati con verbi significativi?_
    - _Tutti gli errori sono descritti e trattati?_
- Domande per la **completezza**
    - Per ogni oggetto
        - _E’ necessario per uno use case?_
        - _In quale use case è creato? Modificato? Distrutto?_
    - Per ogni attributo
        - _Quando è settato?_
        - _Quale è il tipo?_
    - Per ogni associazione
        - _Quando è attraversata?_
        - _Perchè ha una data molteplicità?_
    - Per ogni oggetto CONTROL
        - _Ha le associazioni necessarie per accedere agli oggetti che partecipano nel corrispondente use case?_
- Domande per **consistenza**
    - _Ci sono classi o use case con lo stesso nome?_
    - _Ci sono entità con nomi simili e che denotano concetti simili?_
    - _Ci sono oggetti con attributi e associazioni simili che non sono nella stessa gerarchia di ereditarietà?_
- Domande per **realismo (?) (penso chiarezza)**
    - _Ci sono caratteristiche innovative nel sistema? Sono stati fatti studi o costruiti prototipi per valutarne la fattibilità?_
    - _Le richieste di performance e affidabilità possono essereassicurate? E’ stato costruito un prototipo per assicurarsi della fattibilità? Tale prototipo è in esecuzione su qualche hardware particolare?_

  

### Analisi UML activity diagram

![[image 103.png]]

  

  

# Assegnazione responsabilità

Tre tipi di ruoli:

- _**Generazione di informazione**_
    - L’**utente finale** è l’esperto del dominio di applicazione e genera informazioni sul sistema corrente
    - L’**analista**, lo sviluppatore con la maggiore conoscenza del dominio di applicazione, genera informazioni sul sistema da sviluppare. Ognuno di essi è responsabile di uno o più use case. Identifica oggetti, associazioni, attributi, etc…
- _**Generazione di integrazione**_
    - Il **cliente** definisce lo scopo del sistema sulla base delle richieste dell’utente
    - L’**architetto** unifica use case e oggetti dal punto di vista del sistema. Differenti analisti hanno differenti modi di modellare e l’architetto ovvia a questo problema
- _**Generazione di revisione**_
    - Il **manager delle configurazioni** è responsabile di mantenere la storia delle revisioni e la tracciabilità del RAD con gli altri documenti
    - Il **reviewer** valida il RAD per correttezza, completezza, consistenza e chiarezza

  

### L’accordo con il cliente

L’accordo è l’accettazione delm modello di analisi dal cliente.

Sviluppatore e cliente convergono sul decidere le caratteristiche del sistema.

Si accordano anche su:

- Lista di priorità
- Processo di revisione
- Lista di criteri per accettare o rigettare il sistema
- Scheduling delle attività e budget