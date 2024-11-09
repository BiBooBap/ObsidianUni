Essi descrivono il comportamento del sistema in funzione del tempo e sono un tipo di modello **operazionale** (descrive il comportamento desiderato.

Molto utili soprattutto per sistemi orientati al controllo (tipo iot).

  

### Diagrammi per la modellazione dinamica

- Interaction Diagrams
    - Descrive il comportamento dinamico fra oggetti
        1. _Sequence Diagram_: comportamento di un set di oggetti in sequenza temporale
        2. _Collaboration Diagram_: relazioni fra oggetti senza mostrare la temporalità
- Statecharts
    - Descrive il comportamento dinamico di un solo oggetto
    - Macchina a stati che descrive la risposta di un oggetto agli stimoli esterni (Eventi)
        1. _Activity Diagram_: Tipo speciale di statechart dove tutti gli stati sono stati delle azioni

  

# Modellazione dinamica

Trova e supporta metodi per il modello ad oggetti.

Si inizia con use case o scenari

- Sequence Diagram se si vuole descrivere l’interazione fra oggetti
- Statechart Diagram se si vuole descrivere il comportamento di un singolo oggetto

  

Per esempio, il flusso di eventi di uno use case, dove ogni evento trasmette informazioni da un oggetto ad un altro.

  

## Interaction Diagrams

Descrive comportamento dinamico di un insieme di oggetti che collaborano a risolvere un prolema.

Un’**interazione** è un comportamento che comprende un insieme di messaggi scambiati tra un insieme di oggetti nell’ambito di un contesto per raggiungere uno scopo.

  

Due tipi nell’UML:

- Sequence Diagram
- Collaboration Diagram

Esprimono le stesse cose ma in modo diverso.

  

### Interazioni e messaggi

L’interazione avviene tra oggetti che hanno un **link** fra di loro (istanza di un’associazione).

Un messaggio è una comunicazione tra oggetti dove, trasmessa un’informazione, ci si aspetta una risposta sotto forma di attività.

- La ricezione di un messaggio puo’ essere considerata un’istanza di un evento.
- Un oggetto si attiva alla ricezione di un messaggio.
- Una classe determina i messaggi a cui un oggetto puo’ rispondere.
- Necessari
    - Ricevente
    - Messaggio
    - Informazioni aggiuntive (opzionali)

  

![[image 104.png]]

  

# Sequence Diagrams

Servono a modellare ad alto livello oggetti attivi del sistema, oppure le interazioni che essi hanno fra di loro all’interno di un caso d’uso, o magari anche solo in un’operazione.

Usa il **DAG** come notazione (Direct Acyclic Graph).

  

Come già detto:

- Evidenziano una sequenza temporale
- Associazioni non visibili
- Attività su linee verticali
- La sequenza di messaggi in orizzontale
- Scenario specifico o intero use case

  

Esempio degli oggetti:

![[image 105.png]]

Oggetto inteso come istanza (nomeOggetto : NomeClasse).

- Asse X
    - Oggetti
- Asse Y
    - Tempo

  

**Messaggi.**

Ad un messaggio possono corrispondere diverse azioni, come vedremo:

- _Call_
    - Invoca operazione
- _Return_
    - Restituisce un valore al chiamante
- _Send_
    - Invia segnale ad un oggetto (inizio esecuzione)
- _Create_
    - Crea un oggetto
- _Destroy_
    - Distrugge un oggetto, anche se stesso volendo

  

**Scambio di messaggi sincroni.**

- Rappresentata come freccia chiusa da chiamante a chiamato
    
    ![[image 106.png]]
    
    - Nome sulla freccia del metodo invocato
    - Opzionali parametri e valori di ritorno (se presenti)
- Chiamante aspetta la terminazione del metodo chiamato
- La durata è il quadratino piccolo collegato dalla freccia
- Ritorno segnato con freccia tratteggiata
    - Opzionale, se omesso la fine del metodo determina la fine della durata di vita

![[image 107.png]]

  

**Scambio di messaggi asincroni.**

- Interazioni concorrenti
- Freccia aperta da chiamante a chiamato con nome del metodo chiamato, e opzionalmente parametri e valori di ritorno
    
    ![[image 108.png]]
    
- _Il chiamante non attende la terminazione del metodo chiamato, ma continua subito dopo che l’ha invocato_
    - _Il ritorno non segue quasi mai la chiamata_
- La chiamata del metodo puo’ avere una **condizione** che deve essere verificata a run-time
    - Nel caso non sia verificata, il diagramma NON dice cosa succede (accade solo se viene esplicitamente modellato il caso)
    - La condizione è rappresentata sulla freccia come [condizione] : nomeMetodo()

![[image 109.png]]

  

**Costruzione di un nuovo oggetto.**

Inteso come oggetto non esistente nel sistema fino ad un dato momento, corrisponde all’**allocazione dinamica** e il messaggio corrispondente viene etichettato con **new o create**, e il nuovo oggetto ha collocazione parallela all’invocazione del new o create.

![[image 110.png]]

  

**Distruzione di un oggetto (preesistente).**

Inteso come la distruzione di un oggetto già presente nel sistema, corrisponde alla **deallocazione dinamica** e si rappresenta con una X in corrispondenza della durata dell’oggetto, e diventa “illegale” fare chiamate ai metodi di quell’oggetto.

![[image 111.png]]

  

**Esempio di creazione e distruzione:**

![[image 112.png]]

  

**Box di attivazione.**

Periodo in cui un oggetto esegue un’azione e rimane in esecuzione su di essa.

Cima = start dell’azione

Fondo = fine dell’azione (con eventuale messaggio di ritorno

![[image 113.png]]

  

**Iterazione (ricorrenza) e condizioni.**

Ciclo, rappresentata raggruppando con un **blocco** i metodi (messaggi) da iterare e puo’ avere una **condizione** in alto a sinistra tramite “ *[condizione]”.

I cicli e condizioni possibili (con le notazioni):

- **Loop (while-do, do-while)** e condizione all’inizio o alla fine
- **Alt (if-then-else)** e condizione all’inizio
    - Per rappresentare gli else si divide la sezione if dalla sezione else con una linea tratteggiata, con possibile condizione accanto alla parola “else”.
- **Opt (if-then)** e condizione, esclusivo accesso solo se la condizione è vera

![[image 114.png]]

  

**Auto-chiamata.**

Un oggetto che invoca un suo metodo, rappresentato con una freccia circolare che va dal chiamante a se stesso (rappresenta anche la ricorsione).

![[image 115.png]]

  

**Vincoli sul tempo di risposta.**

![[image 116.png]]

  

## Euristiche per Sequence Diagrams

### Layout

- 1° colonna
    - Attore che ha iniziato lo use case
- 2° colonna
    - Oggetto BOUNDARY
- 3° colonna
    - Oggetto CONTROL che gestisce la parte di use case restante

### Creazione

- Oggetti CONTROL creati all’inizio dello use case
- BOUNDARY sono creati dai CONTROL

### Accesso

- CONTROL e BOUNDARY hanno accesso alle ENTITA’
- Le ENTITA’ non possono chiamare i CONTROL e BOUNDARY

  

## Torneo ARENA: Sequence Diagram

Grazie al Sequence Diagram istanziamo nuovi oggetti e eventi (metodi).

  

![[image 117.png]]

  

  

![[image 118.png]]

  

  

**Chi detiene gli eventi (metodi) all’interno del diagramma?**

![[image 119.png]]

  

  

![[image 120.png]]

  

  

## Ulteriori considerazioni

Essendo che i Sequence Diagrams sono derivati degli use cases, ne riusciamo a descrivere meglio la struttura e ci aiutano a capire **quanto è decentralizzato il sistema.**

### Fork Diagram

Si alloca il comportamento dinamico maggiormente ad un oggetto solo, CONTROL iniziale (di solito). Ne deriva che esso conosce tutti gli altri oggetti e li usa per ricavare informazioni tramite domande e comandi diretti.

![[image 121.png]]

  

### Stair Diagram

Il comportamento dinamico è distribuito fra i vari oggetti, che delegano parte della loro responsabilità agli altri oggetti. Ne deriva che alcuni oggetti conoscono alcuni oggetti, non tutti. Aiuta con comportamenti specifici.

![[image 122.png]]

  

### Quali dei due?

- Si sceglie FORK in casi di centralizzazione
    - Le operazioni possono cambiare ordine
    - Nuove operazioni possono essere inserite
- Si sceglie STAIR in casi di decentralizzazione
    - Le operazioni hanno una connessione molto forte fra loro
    - Le operazioni saranno fatte nello stesso ordine, sempre

  

  

# Da use case a sequence diagram

Uno use case = un sequence diagram.

Si parte mettendo un attore e un oggetto, e quest’ultimo rappresenta l’intero sistema.

- Punto di partenza detto Black Box
    - Tralasciare eccezioni e essere ottimistici (ovvero descrivere solo casi positivi)
    - Altro viene aggiunto dopo

  

Elementi come prima revisione:

- Attore che attiva il use case
- Oggetto per presentarlo (BOUNDARY)
- Oggetto per coordinare le attività del sistema (CONTROL)
- Oggetto per rappresentazione/gestione/memorizzazione dei dati (ENTITY)

  

  

# Collaboration Diagram

Specifica gli oggetti che collaborano fra loro in uno scenario ed i loro messaggi.

Sequence diagram:

- PIù evidente sequenza di messaggi

Collaboration diagram:

- Più evidente legame tra oggetti

Può essere utilizzato in fasi diverse (analisi, disegnodi dettaglio) e rappresentare diverse tipologie di oggetti. Inoltre è molto adatto per concorrenza e threads.

  

## Messaggi e Link

![[image 123.png]]

![[image 124.png]]