### Domini

Come già citato, ci sono domini diversi in un progetto:

- Application domain (_Requirement Analysis_)
    - Ambiente del sistema
- Solution Domain (_System Design, Object Design_)
    - Le tecnologie disponibili per costruire il sistema

  

## Modellamento Object Oriented

![[image 38.png]]

  

# Unified Modeling Language

Linguaggio e notazione universali per la crazione di software, uno standard.

### Cos’è?

Una convergenza di notazioni già usade nella programmazione ad oggetti.

  

I tools commerciali più usati:

- Rational (IBM)
- Together (Borland)
- Visual Architect (Visual Paradigm)
- Enterprise Architect (Sparx Systems)

Mentre i tool open source:

- ArgoUML
- StarUML
- Umbrello (Linux)
- PoseidonUML

Tool di ricerca:

- Unicase
- Sysiphus

  

Con solo il 20% dell’UML, si possono risolvere **l’80% dei problemi di modeling**.

(_Regola di Pareto_)

![[image 39.png]]

  

**L’UML è indipendente da metodi, tecnologie e produttori.**

  

**“Linguaggio”** perchè aiuta a specificare, costruire, visualizzare e documentare gli artefatti di un sistema.

**“Universale”** perchè puo’ rappresentare molti sistemi diversi, fra web e legacy, tradizionali cobol a quelli object oriented.

  

Quindi esso non è un metodo, ma **un linguaggio di modellazione**, o anche una notazione standard, basato su un _**meta-modello**_ integrato dagli elementi del sistema software.

**Non esiste una sequenza di processi da seguire**.

  

Inoltre esso assume che il processo di sviluppo del suddetto software sia:

- Basato sui Casi d’Uso (_use case driven_)
- Incentrato sull’architettura
- Iterativo e incrementale

Aspetti che poi vanno adattati alla peculiarità dei domini di ciascuna organizzazione.

  

### UML come meta-modello

Esso si fonda su un meta-modello integrato, dove vengono definire caratteristiche e relazioni fra i diversi elementi (es: classi, attributi, moduli).

Il meta-modello integrato è inoltre la base per l’implementazione dell’UML stesso negli strumenti di sviluppo (cases, ambienti visuali, …) e per l’operabilità fra i diversi strumenti.

  

### Obiettivi dell’UML

- Fornire all’utente un linguaggio di specifica espressivo, visuale e pronto all’uso
- Offrire meccanismi di estensibilità e specializzazione del linguaggio
- Indipendenza da linguaggi di programmazione e dai processi di sviluppo
- Incoraggiare la crescita dei tool OO commerciali
- Supportare lo sviluppo di idee ad alto livello, quali frameworks, pattern e componenti

  

Esso pero’:

- Non è un linguaggio di programmazione visuale
    - E’ un linguaggio di **specifica visuale**
- Non è un modello per definizione di interfacce
- Non è dipendente dal paradigma di sviluppo nel quale puo’ essere usato

  

# L’uso di modelli per descrivere sistemi software

- **Modello di sistema**: Modello funzionale + Modello ad oggetti + Modello dinamico
    - Modello funzionale: _Quali sono le funzioni del sistema?_
        - UML: Diagrammi ad use cases
            - Descrive le il comportamento funzionale del sistema dalla visione dell’user
    - Modello ad oggetti: _Qual’è la struttura del sistema?_
        - UML: Diagramma a classi
            - Descrive una struttura statica del sistema: oggetti, attributi, associazioni
    - Modello dinamico: _Come reagisce il sistema ad eventi esterni?_
        - UML: Diagramma di sequenza, diagramma statechart, diagramma ad attività
            1. Descrive il comportamento dinamico fra gli oggetti del sistema
            2. Descrive il comportamento dinamico di un unico oggetto individualmente
            3. Descrive il comportamento dinamico del sistema, in un flusso di lavoro specifico

  

  

---

## Diagramma di use cases

Mostra le modalità d’uso del sistema con gli **use cases**, così come gli utilizzatori e coloro che in generale interagiscono col sistema (**attori**) e le relazioni fra quest’ultimi con i casi d’uso.

Uno use case descrive l’interazione tra attori e sistema, e dunque è una visione dall’esterno, di conseguenza **NON E’ LA DESCRIZIONE DELLA LOGICA INTERNA ALLA FUNZIONE**.

  

E’ usato nella requirements elicitation e nella requirements analysis per rappresentare comportamento visibile dall’esterno del sistema.

![[image 40.png]]

Il _Passenger_ è un **attore**, che detiene un ruolo all’interno dello scenario, e all’interno dello stesso è l’elemento che comunica con il sistema e utilizza le sue funzionalità.

_PurchaseTicket_ è uno **use case**, ed è una funzionalità offerta dal sistema.

Il modello di use cases è quindi un set di use cases che descrive in completezza le funzionalità offerte dal sistema.

![[image 41.png]]

### Attori

Possono essere non solo gli end users, ma una qualsiasi entità che comunica col sistema.

Siano:

- Users
- Sistemi esterni (es: componenti intercollegati)
- Ambiente fisico (es: recettori iot)

Ha un **nome unico** e una descrizione opzionale.

![[d8cd3029-3799-4a16-84ad-fe8fc1c55131.png]]

### Use cases

Uno use case = Classe di funzionalità del sistema

Possono essere descritti testualmente con focus sul flusso che c’è fra attore e sistema.

La descrizione di solito ha:

- Un nome unico
- Attori partecipanti
- Condizioni di entry
- Condizioni di exit
- Flusso di eventi
- Requisiti speciali

![[image 42.png]]

  

Gli use case possono essere collegati come:

- Relazione “Extends”
    
    - Aggiunge funzionalità ad uno use case
    - Gli use case di eccezione che sono anche “Extends” possono esserlo per più di un padre
    - Direzione = Figlio → Padre
    
    ![[image 43.png]]
    
- Relazione “Includes”
    
    - Gli use case figli rimpiazzano parte dello use case padre (che quindi avranno in comune un comportamento con i figli)
    - I figli sono realizzati in questo modo non perchè sono un’eccezione, ma perchè dovranno essere riusati più volte
    
    ![[15d3f076-b123-4f8a-b92a-50509915029d.png]]
    

  

  

---

## Diagramma delle classi

Come l’object oriented programming, rappresenta le classi di oggetti del sistema con i loro attributi e le operazioni, e mostra le relazioni tra le classi stesse.

L’utilizzo è possibile in analisi e in disegno.

**Sono usati maggiormente:**

- Durante l’analisi dei requisiti per modellare i concetti che fungono da base per il dominio dell’applicazione
- Durante il system design per modellare i sottosistemi (sistemi componenti)
- Durante l’object design per specificare il comportamento di classi e loro attributi

### Classe

![[image 44.png]]

Una classe singola racchiude **stato (attributi)** e **comportamento (operazioni)**.

L’unica informazione obbligatoria è il nome:

### Istanza

![[image 45.png]]

Un’istanza è un **fenomeno** e il suo nome è sottolineato.

Il nome puo’ contenere solo il nome della classe a cui l’istanza fa riferimento (**istanza anonima**).

### Ricapitolazione I

Attore:

- Entità che comunica col sistema da modellare, dall’esterno

Classe:

- Modellamento dell’astrazione, entità nell’applicazione o dominio di soluzione
- La classe fa parte del modello del sistema

Oggetto:

- Specifica istanza di classe

  

### Associazioni

![[image 46.png]]

Denotano le relazioni fra classi.

La molteplicità di un'estremità di un'associazione indica quanti oggetti un'istanza  
di una classe può legittimamente referenziare..  

![[image 47.png]]

![[image 48.png]]

  

### Aggregazioni

![[image 49.png]]

Caso speciale di associazione, dove vi è una gerarchia di elementi figli che fanno parte di uno più grande padre (un concetto che li racchiude tutti).

L’**aggregato** è la classe padre, i componenti le classi figlie.

![[image 50.png]]

Poi vi è la **composizione**, segnata con un rombo pieno.

E’ una forma forte di aggregazione **dove l’esistenza stessa del componente figlio è controllata dall’aggregato (padre).**

  

### Eredità

![[image 51.png]]

  

Altro caso speciale di associazione.

Semplifica il modello di analisi introducendo la **tassonomia**, ovvero un’ordine di gerarchia.

- Le classi figlie ereditano gli attributi e operazioni delle classi padre

  

  

---

## Diagrammi di sequenza

Usato per descrivere la specifica sequenza di eventi di un caso d’uso.

- Uno dei principali input per l’implementazione dello scenario
- Mostra la sequenza temporale dei messaggi degli oggetti coinvolti

  

**E’ un** _**diagramma di interazione**_**, quindi evidenza come un caso d’uso è realizzato tramite la collaborazione fra oggetti.**

![[image 52.png]]

Usato durante l’analisi per raffinare gli use case e trovare altri oggetti.

Usato inoltre nel system design per raffinare le interfacce dei sottosistemi.

- **Istanze**: rettangolo alto e grosso nella figura
- **Attori**: stickmans!
- **Lifelines**: linee tratteggiate
- **Messaggi**: rappresentati dalle freccie
- **Attivazioni**: rettangoli piccoli

  

### Proprietà

Rappresenta il comportamento in termini di interazioni, e serve molto per identificare o trovare oggetti mancanti al dominio di soluzione.

Complementa il diagramma a classi (che rappresenta la struttura).

  

  

---

## Diagramma di stato (statechart)

Specifica il ciclo di vita di un oggetto e ne rappresenta il comportamento in termini di

- Eventi a cui gli oggetti (la classe) sono sensibili
- Azioni prodotte
- Transizioni di stato
    - Identifica stati interni agli oggetti

  

### Elementi

![[image 53.png]]

Esempio: telefonata

![[image 54.png]]

  

### Stato

L’oggetto che è in uno _stato_, soddisfa qualche condizione, esegue qualche attività o aspetta qualche condizione che si verifichi.

Attributi opzionali:

- Nome
- Entry / Exit conditions
- Transizioni interne (non cambiano lo stato)
- Attività dello stato
- Sottostati
    - Disgiunti (sequenzialmente attivi)
    - Concorrenti (concorrentamente attivi)

  

Uno stato completo:

![[image 55.png]]

  

### Transizioni

Cambiamento da uno stato iniziale a uno finale

- Transizione esterna (iniziale diversa da finale)
- Transizione interna (iniziale uguale a finale)

  

Attributi opzionali:

- Evento (segnale, cambiamento)
- Condizione di guardia (transizione avviene se evento accaduto + condizione di guardia = true)
- Azione (eseguita durante la transizione **e non interrompibile**)

  

Una transizione senza eventi (triggerless) scatta se

- Con guardia, essa diventa vera
- Senza guardia, se l’attività interna allo stato iniziale è completata

  

Esempio: libro

![[image 56.png]]

  

### Sottostati sequenziali

_Un macro-stato è una composizione di un’insieme di stati OR._

I sottostati ereditano le transizioni dei loro superstati.

![[image 57.png]]

  

### Sottostati concorrenti

_Un macro-stato è una composizione di un’insieme di stati AND._

Più stati sono racchiusi in uno stato più grande e sono eseguiti in parallelo.

Tutti gli stati che terminano aspettano gli altri al punto finale.

- Quando avviene una transizione in uno stato con concurrent substate, il flusso di controllo subisce un fork per ciascun concurrent substate; alla fine esso si ricompone in un unico flusso con uno join

  

Esempio:

![[image 58.png]]

  

  

---

## Diagramma di attività

Sequenza di operazioni per definire un’attività più complessa, che possono rappresentare processi paralleli assieme alla loro sincronizzazione.

_Sono state-diagrams particolari_.

- Ogni stato contiene (è) un’azione

  

Ogni diagramma di attività puo’ essere associato ad

- Una classe
- All’implementazione di un’operazione
- Ad uno use case

  

Più generalmente: descrivono un workflow o una logica interna.

Utili per modellare:

- Comportamenti sequenziali
- Non determinismo
- Concorrenza
- Sistemi distribuiti
- Business workflow
- Operazioni

Inoltre le azioni possono essere stereotipate.

  

### Elementi

![[image 59.png]]

  

- Attività
    - Esecuzione non atomica entro uno stato
    - Composta da Azione, Elaborazioni atomiche, comportano un cambiamento di stato del sistema o il ritorno di un valore
- Transizione
    - Flusso fra due azioni
- Espressione di guardia
    - Booleano di verifica all’attivazione di Transizioni
- Branch
    - Percorsi alternativi in base a valori booleani
    - Una transition in entrata - Due o più transition in usciota
- Barra di sincronizzazione
    - Sincronizza flussi concorrenti
    - Fork: splitta un flusso su più Transizioni verso Azioni concorrenti
    - Join: unifica più Transizioni verso un’Azione
    - **FORK E JOIN DEVONO ESSERE BILANCIATI**

  

### Action State e Activity State

Activity State:

- Stati non atomici (e interrompibili) che possono essere rappresentati ognuno col proprio activity diagram

Action State:

- Azioni eseguibili atomiche (e non interrompibili)
- Caso particolare di Activity State

  

Hanno la stessa rappresentazione grafica, ma Activity State puo’avere altri elementi in più tipo Entry ed Exit conditions.

  

Esempio: gestione ordini

![[image 60.png]]

  

### Swimlanes

Costrutto grafico che raggruppa parti di action/activity.

Servono ad identificare responsabilità nelle diverse operazioni.

- Parti di oggetto
- Oggetti diversi

In un business model, di fatti, identificano le unità organizzative.

Per ogni oggetto responsabile di action/activity viene definito un swimlane, identificato da un nome univoco nel diagramma.

- Swimlane dividono oggetti
- Non hanno ordine
- Le Transizioni possono attraversare le swimlanes

  

Esempio

![[image 61.png]]

  

### Attività e flussi di oggetti

I flussi di gogetti sono associazioni tra action/activity state e oggetto, modellandone l’utilizzo e l’influenza action/activity sull’oggetto.

Gli oggetti:

- Possono essere output di una action
- Possono essere l’input di una action
- Possono essere manipolati da qualsiasi numero di action
- Possono essere presenti più volte nello stesso diagramma
    - Ogni presenza differente è un punto di vita differenze dell’oggetto stesso

  

Il flusso puo’ avere lo stato di un object fra [ ] al di sotto del nome dell’oggetto.

![[image 62.png]]

Di seguito gli abomini che i professori hanno voluto fare fotografando e non fotocopiando le pagine, laboratorio di ricerca in dipartimento di eccellenza.

![[image 63.png]]

![[e260fe2d-f601-4585-8c58-e5fe4a12945e.png]]

![[3594dfcd-a4ca-4398-a355-0d2923982572.png]]

![[image 64.png]]

  

  

---

# Pacchetti

Servono ad organizzare i modelli UML per migliorare la leggibilità.

Possono servire ad organizzare classi in sottosistemi.

Inoltre tutti i sistemi complessi possono essere decomposti in sottosistemi, ed ogni sottosistema è modellato come pacchetto.

  

## Package Diagrams

Un pacchetto racchiude dunque un insieme di classi la cui interazione è funzionale.

Un diagramma fatto dai pacchetti verrebbe come segue:

![[image 65.png]]

**Collega e separa i vari sottosistemi**.

  

### Dipendenze

Esistono solo se in un package c’è una classe dipendente da una classe di un altro package.

  

![[image 66.png]]

Esempio qui, occorrerebbe controllare le classi dei package sopra orders.

**LE DIPENDENZE NON SONO TRANSITIVE**.

  

### Altri esempi

![[image 67.png]]