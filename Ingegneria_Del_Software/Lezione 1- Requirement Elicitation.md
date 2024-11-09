Come possiamo approcciarci alla complessità?

- ==**Astrazione**==
- ==**Decomposizione**== ==(==_==Divide et Impera==_==)==
    - Orientata agli ogetti
    - Decomposizione funzionale (crea codice difficile da aggiornare)
- ==**Gerarchia**== ==(==_==Layering==_==)==

Si inizia generalmente con la descrizione delle funzionalità tramite i modelli di use cases, per poi trovare dei possibili modelli di oggetti.

  

### Ciclo di vita dello sviluppo di un software

E’ un set di attività, assieme alle relazioni fra ognuna di loro, che supportano lo sviluppo di un sistema software.

Alcune domande sporgono spontanee:

- _Quali attività dovrei scegliere per il progetto?_
- _Quali dipendenze ci sono fra le attività?_
- _Come dovrei pianificare le attività?_
- _Qual’è il risultato di un’attività?_

  

### Attività

Ogni attività genera minimo uno o più modelli.

Attività che esistono in un progetto:

- _**Requirements Elicitation**_
    - Modello “Use Case”
- _**Analysis**_
    - Application Domain Objects (esprime gli Use Case)
- _**System Design**_
    - SubSystems (che strutturano gli Use Case)
- _**Object Design**_
    - Implementation Domain Objects (realizzazione degli Use Case)
- _**Implementation**_
    - Source Code (implementazione degli Use Case)
- _**Testing**_
    - Test Cases (verificano gli Use Case)

  

![[image 1.png]]

  

# Primi step per determinare i requirements

## Identificazione del sistema

Dobbiamo identificare qual’è lo scopo del sistema e i confini del sistema per capire cosa sta dentro e cosa fuori.

Questo viene fatto tramite l’assesment dei requisiti, che si divide in:

- _==**Requirement Elicitation**==_
    - consiste nella definizione del sistema nel modo in cui viene capito dal customer (_Problem Description_)
- _==**Requirements Analysis**==_
    - specificazione tecnica del sistema nel modo in cui viene capito dal developer (_Problem Specification_)

I problemi che possono verificarsi sono tanti

- Ambiguità (d’interpretazione del pc)
- Funzionalità non calcolate (uso del software in maniere non previste)

Questi dovrebbero essere i prodotti:

![[image 2.png]]

## System Specification vs Analysis Model

Entrambi si focalizzano sul punto di vista dell’utente finale, ma

- il _System Specification_ usa un **linguaggio naturale** (e derivante dal _problem statement_)
- l’_Analysis Model_ usa **notazioni formali o semi-formali** (tipo l’UML)

  

## Problem statement - Statement of Work

Il cliente esplica la descrizione del problema che il sistema dovrà risolvere.

Un Problem Statement ben fatto descrive:

- la situazione attuale
- le funzionalità che questo nuovo sistema dovrà supportare
- l’ambiente in cui il sistema dovrà lavorare
- consegne che il cliente si aspetta
- date di consegna
- **criteri di accettazione**

  

Si inizia da una situazione in cui bisogna appunto capire il problema in se e perchè lo si vuole risolvere.

Per poter proseguire ci servono diverse cose, iniziando dalla **descrizione di uno o più scenari** (di uso), di cui si ha bisogno, oltre a:

- dei **Requisiti**
- una **Project Schedule**
    - le attività nel progetto devono essere schedulate, soprattutto gli incontri col cliente e le _**Deadline**_
- un **Target Environment**
    - dove il suddetto sistema deve inoltre superare dei test
- come già detto, il soddisfacimento dei **Criteri di accettazione**
    - che servono anche ai test di sistema

  

### Situazione iniziale: Presenza del problema

Il cliente ha bisogno di risolvere questo problema, e lo assegna a noi.

Ci sono diverse motivazioni per cui accade ciò, generalmente è per via di qualcosa che è cambiato.

Un cambiamento che puo’ essere:

- nel **Dominio di applicazione**
    - il business ha introdotto una nuova funzionalità
- nel **Dominio della soluzione**
    - una nuova tecnologia permette di aggiornare la soluzione al problema o abilitare per la prima volta alla soluzione di esso

  

Eempio: il problema ARENA

![[image 3.png]]

![[image 4.png]]

  

## Requisiti

Sono dei criteri che bisogna rispettare prima di poter avanzare.

_**Requisi Funzionali**_

Descrive l’interazione tra il sistema e il suo ambiente, indipendentemente dall’implementazione.

Esempio:

- Un’operatore ARENA deve poter definire un nuovo gioco.

_**Requisiti non Funzionali**_

Aspetti del sistema visibili all’utente che non sono legati al funzionamento vero e proprio del sistema stesso.

Esempio:

- tempo di risposta < 1s
- ARENA deve essere raggiungibile 24/24

_**Vincoli (pseudo-requisiti)**_

Imposti dal cliente o l’ambiente del sistema.

Esempio:

- il linguaggio di implementazione deve essere Java
- ARENA deve poter interfacciare con altri giochi di altri developers

---

Generalmente nei requirements non ci sono i **metodi di implementazione, i linguaggi o gli ambienti di developing**, nel caso in cui il cliente cerchi di costringere all’uso specifico su uno di questi argomenti, bisogna combattere per averne il diritto.

  

### Valiazione dei requisiti

Avviene dopo l’analisi dei requisiti, o in concomitanza con la consegna al cliente.

I criteri di validazione sono:

- **Correttezza**
    - I requisiti devono rappresentare il punto di vista dato al cliente.
- **Completezza**
    - Tutti i possibili scenari in cui il sistema puo’ essere usato sono descritti, compresi quelli eccezionali.
- **Consistenza**
    - Controllare se dei requisiti Funzionali e Non-Funzionali vanno in contrasto gli uni con gli altri.
- **Realismo**
    - I requisiti possono essere implementati e consegnati.
- **Tracciabilità**
    - Ogni funzione del sistema puo’ essere tracciata ad un corrispondente set di requisiti funzionali.

  

### Evoluzione dei requisiti

Ovviamente i requisiti possono evolversi, a volte anche molto velocemente durante il _Requirements Elicitation_.

Per ovviare a questi problemi

- **Salvare tutto in una repository condivisa**
- **Dare multi-user access**
- **Creare un documento automatico delle specifiche del sistema dalla repository**
- **Permettere gestione del change**
- **Provvedere tracciabilità attraverso il lifecycle del progetto**

  

### Priorità dei requisiti

- **Alta priorità**
    - Affrontata durante analisi, design e implementazione
    - Di solito è una feature che ha una grande importanza

- **Media priorità**
    - Affrontata durante analisi e design
    - Generalmente nella seconda revisione

- **Priorità bassa**
    - Affrontata solo durante l’analisi
    - Dimostra come il sistema si adatterà con le tecnologie del futuro

  

# Tipi di Requirements Elicitation

## Greenfield Engineering

Lo sviluppo parte da zero, non esiste nessun sistema e i requisiti sono ricavati dagli end users e dal cliente.

Generalmente viene iniziato dopo il riconoscimento di alcuni bisogni degli utenti.

## Re-Engineering

Re-design e/o re-implementazione di un sistema già esistente usando una tecnologia più avanzata.

Inizia a causa del “technology enabler”.

## Interface Engineering

Non si cambia la funzionalità basica del sistema già esistente, ma si migliora la sua interfaccia, che può essere

- tra sistema e persone
- tra sistemi diversi

Inizia anche esso a causa del “technology enabler”, oppure anche per bisogni del mercato.

# Metodi per il Requirements Elicitation

![[image 5.png]]

# ==Requirements Elicitation==

Richiede la collaborazione di esperti di diverso tipo

1. **utenti con conoscenza del dominio d’applicazione**
2. **sviluppatori con conoscenza del dominio di soluzione (design, implementazione)**

  

Per collegare meglio questi due background diversi si usano:

# Scenari

Esempi di uso del sistema descrivendo una serie di interazioni fra utente e sistema stesso in modo **informale**. Possono avere diversi usi nel lifecycle di un software:

- “**As-is**” scenario
    - Scenario che descrive la situazione attuale ed è l’utente a fornire la descrizione. Generalmente si usa nel _**Re-Engineering.**_
        
        _Example: Description of Letter-Chess._
        
- “**Visionary**” scenario
    - Descrive un sistema futuro. Non puo’ essere fato solo da user o solo da developer. Di solito usato per il _**Greenfield Engineering**_ e _**Re-Engineering.**_
        
        _Example: Description of an interactive internet-based Tic Tac Toe game  
        tournament.  
        _
        
- “**Evaluation**” scenario
    - Sono delle task in cui il sistema viene controllato e valutato.
        
        _Example: Four users (two novice, two experts) play in a TicTac Toe tournament in  
        ARENA.  
        _
        
- “**Training**” scenario
    - Istruzioni step by step che guidano un utente all’interno del sistema.
        
        _Example: How to play Tic Tac Toe in the ARENA Game Framework._
        

### Come trovare degli scenari

Non dobbiamo aspettarci di poter ricavare informazioni dal cliente se il sistema non esiste e non dobbiamo aspettare comunicazioni o informazioni se invece esso esiste.

Il nostro compito è quello di ricavare le informazioni **collaborando** con il cliente:

- aiutare il cliente a decidere dei requisiti
- il cliente ti aiuta a capirli
- i requisiti poi si evolvono mentre gli scenari si sviluppano ulteriormente

### Euristiche per trovare degli scenari

Domande ponibili a cliente e a se stessi:

- _Quali sono le task principali del sistema?_
- _Che dati potranno essere manipolati dagli Attori?_
- _Che cambiamenti esterni deve conoscere il sistema?_
- _Che aggiornamenti dovrà ricevere l’attore dal sistema?_

Oltre delle domande bisognerebbe osservare il sistema stesso e le task che esegue, se già esiste.

# Use Cases

Astrazione che descrive una classe di più scenari

- modella il punto di vista dell’utente (requisiti funzionali)
- descrive ogni possibile flow di eventi e interazioni fra oggetti

Possono servire come base per i **manuali d’uso**.

### Come descrivere gli use cases

Dopo la formulazione degli scenari, si passa a **classificare degli scenari paralleli in uno use case.**

Esempio di rappresentazione nel modello use case:

![[image 6.png]]

Il set di tutti gli use case esprime la **completa funzionalità** del sistema.

### Euristiche per trovare gli use cases

- Selezionare uno scenario per dividere **verticalmente** il sistema e discuterne con l’utente per capire come preferisce interagire
- Selezionare più scenari per dividere **orizontalmente** il sistema e definire il contesto del sistema assieme all’utente
- Usare i **mock-ups** come metodo illustrativo visuale per facilitare il procedimento
- Scoprire cosa l’utente fa
    - ====Task observation====
    - ====Questionari====

### Step per formulare gli use cases

- Darne un **nome**
    - Preferibilmente un verbo
    - Dovrebbe descrivere cosa l’utente sta provando ad ottenere
- Trovare gli **attori partecipanti** (dandone un nome generico)
- Descrivere la **entry condition**
- Concentrarsi sul **events flow** (usando linguaggo informale e naturale)
    - Usare le forme attive
    - Gli step devono iniziare con “L’attore” oppure con “Il sistema”
    - La relazion di causa fra gli step deve essere chiara
    - Tutti i flow di eventi devono avere una propria descrizione
    - I limiti del sistema devono essere chiari
    - Componenti esterni devono essere descritti come tali
    - Termini importanti vanno inseriti in un glossario
- Descrivere la **exit condition**
- Aggiungere **eccezioni** (ad esempio se le cose vanno nel verso sbagliato)
- Aggiungere **special requirements** (lista non funzionale di requisiti e limiti)

$\text{LA LUNGHEZZA NON DEVE MAI} \\\text{SUPERARE LE 1-2 PAGINE}$

Esempio generale nell’use case model:

![[image 7.png]]

Esempio generale di use case alternativo:

![[image 8.png]]

![[image 9.png]]

![[image 10.png]]

![[image 11.png]]

### Associazioni di Use Case

Sono le dipendenze che si hanno fra gli use cases, e servono a **ridurre la complessità**

- dividendo use case in parti più piccole
- separando event flows alternativi nello stesso use case

I tipi che esistono

- _**Includes**_
    
    - uno use case include un altro use case (_**decomposizione funzionale**_), si fa generalmente per facilitare uno use case rendendolo anche più veloce nella sua risoluzione.
    
    ![[image 12.png]]
    
    - si puo’ anche usare quando uno use case **fa in parte una funzione già delegata ad un altro use case**.
    
    ![[image 13.png]]
    
- _**Extends**_
    
    - uno use case estende un altro use case. serve ad estendere la soluzione al problema originale, già completo di suo ma ampliabile.
    
    ![[image 14.png]]
    
    - **l’attivazione può avvenire in un punto qualsiasi del flusso di eventi  
        dello use case base.  
        **
- _**Generalization**_
    
    - ovvero uno use case astratto, che poi ha delle specializzazioni. si usa generalment quando più use case hanno in comune il proprio comportamento. i figli prendono dal padre il funzionamento, aggiungendolo al loro (già esistente) oppure sovrascrivendolo in parte.
    
    ![[image 15.png]]
    

  

# Considerazioni importanti

## La raccolta di use cases e requisiti è connessa

1. **Raccolta dei requisiti**
2. **Identificazione degli use case**
3. **Scrittura degli use case**
4. **Verifica e validazione finali**

## Specifica dei requisiti

- Descrizione testuale
- Standard maggiormente usato: _ISO/IEC/IEEE standard 29148:2011 (E)_
    
    Accessibile ad
    
    > [!info] IEEE Xplore  
    > IEEE Xplore, delivering full text access to the world's highest quality technical literature in engineering and technology.  
    > [https://ieeexplore.ieee.org/](https://ieeexplore.ieee.org/)  
    

## Requisiti “well-formed” (ben fatti)

- Possono essere verificati
- Devono risolvere il problema posto dagli **stakeholder** o comunque i loro obiettivi
- Si qualifica come soluzione tramite **condizioni misurabili** che sono anche soggette a specifici limiti
- Definisce le performance del sistema quando usato dagli stakeholder o comunque la capabilità generica del sistema, ed è unica per quello stakeholder.

## Sintassi generale dei requisiti

> ==**[Condition][Subject][Action][Object][Constraint]**==

Esempi:

- _When signal x is received [__==Condition==__], the system [__==Subject==__]  
    shall set [  
    __==Action==__] the signal x received bit [__==Object==__] within 2  
    seconds [  
    __==Constraint==__]_
- _At sea state 1 [__==Condition==__], the Radar System [__==Subject==__]  
    shall detect [  
    __==Action==__] targets [__==Object==__] at ranges out to  
    100 nautical miles [  
    __==Constraint==__]_
- _The invoice system [__==Subject==__], shall display [__==Action==__]  
    pending customer invoices [  
    __==Object==__] in ascending  
    order in which invoices are to be paid [  
    __==Constraint==__]_

## Punti di risalto ulteriori

- **Requisiti**
    - Uso di “_==**DEVE**==_”, obbligatori nel soddisfacimento
- **Preferenze e obiettivi**
    - Uso di “_==**DOVREBBE**==_”, non obbligatori ma desiderati
- **Suggerimenti o permessi**
    - Uso di “_==**PUO’**==_==”, non obbligatori==
- **Non-requisiti, come testo descrittivo**
- **Usare affermazioni positive**
- **USARE LA FORMA ATTIVA DEI VERBI**

## Requirement characteristics

- Completi
    - Contengono tutto riguardo al sistema
- Consistenti
    - **Nessun conflitto**
- Abbordabile
    - L’obiettivo puo’ essere soddisfatto con tecnologie ottenibili
- **Delimitato**
    - **Rimane nel limite di cio’ che l’utente ha bisogno**

## Raggiungibili o realizzabili

Il primo intende che con le risorse a disposizione e i vincoli immessi, si riesce comunque ad arrivare al compimento dell’obiettivo.

Il secondo intende che è semplicemente tecnicamente realizzabile, o puo’ essere messo in pratica.

Quindi, _**un obiettivo puo’ essere tecnicamente realizzabile, ma non necessariamente raggiungibile.**_

## Matrice di tracciabilità

![[image 16.png]]

## Attributi di qualità popolari

- **AFFIDABILITA’**
    - Disponibilità, fault tolerance, possibilità di recupero, etc…
- **PERFORMANCE**
    - Utilizzo minore di tempo e risorse.
- **OPERABILITA’**
    - Facilità d’uso, uso di interfacce visuali, accessibilità tecnica, etc…
- **SICUREZZA**
    - Confidenzialità, integrità, autenticità, etc…
- **COMPATIBILITA’**
    - Co-esistenza, etc…
- **MANTENIBILITA’**
    - Modularità, reusabilità, modificabilità, etc…
- **PORTABILITA’**
    - Adattabilità, possibilità di rimpiazzamento, installabilità, etc…

---

Esempi:

![[image 17.png]]

## FURPS+: categorie di requisiti non-funzionali

- Usabilità
    - Facilità di comprensione e di learning, oltre che di capire gli output del sistema
- Affidabilità
    - Sotto determinate condizioni gravi il sistema deve essere funzionante
    - Deve essere possibile riconoscere problemi e poterli risolvere
    - _Dependability_, ovvero la dipendenza che l’intero sistema ha sul servizio che esso offre, ed include Affidabilità, Robustezza e Sicurezza
- Performance
    - Quantificabile con misure appropriate al tipo di servizio
- Supportabilità
    - Facilità di cambio o modifica del sistema dopo il deployment
    - Include Adattabilità e Mantenibilità

### Identificazione dei suddetti

![[image 18.png]]

![[image 19.png]]

![[image 20.png]]

![[image 21.png]]

![[image 22.png]]

![[image 23.png]]

![[image 24.png]]

## FURPS+: categorie di pseudo-requisiti

- Requisiti di implementazione
    - Limitazioni sull’utilizzo di determinati tool per l’implementazione
- Requisiti di interfaccia
    - Limiti posti da sistemi esterni, tipo sistemi legacy o di format interchange
- Requisiti operazionali
    - Limiti sulla parte amministrativa e manageriale del sistema nelle operazioni
- Requisiti di packaging
    - Limiti sulla consegna del sistema
- Requisiti legali
    - Licensing, regolazione, certificati

# Considerazioni finali

## Gestiore della elicitazione dei requisiti

- Specificazione della negoziazione: Joint Application Design (JAD)
    - Ognuno dei differenti stakeholders presenta il proprio punto di vista, su cui poi si negozia e si arriva ad un accordo
    - La specifica dei requisiti è collegata fra i vari stakeholders e deve essere fatta in pari accordo assieme ad ognuno di essi
- Tracciabilità della Mantenibilità
    - Controllare se il sistema è completo, se rispetta i requisiti
    - Cross-reference attraverso i documenti così da poter capire la struttura delle dipendenze all’interno del sistema

## Documento dell’Analisi dei Requisiti

![[image 25.png]]