# Sviluppo di software odierno

![[image 125.png]]

  

- Core developers
    - Coloro che hanno la responsabilità delle release, rispondere alle domande degli utenti finali e settare le visioni del progetto.
- Co-Developers
    - Implementano la visione del progetto, propongono soluzioni di sviluppo e supportano i core developers.
- Community
    - Set di tutte le persone che hanno a che fare con il progetto, dove prendono anche parte discussioni sul software.
- Users
    - Coloro che praticamente usano il software

  

## I passaggi

I passaggi di sviluppo sono distribuiti, e ci sono dei tool necessari per l’integrazione.

- I contribuenti sono coloro che danno una mano sul codice.
- Gli integratori sono coloro che hanno il diritto di integrare il codice

![[image 126.png]]

![[image 127.png]]

$\text{PULL-BASED ENVIRONMENT}$

  

## Integratore

### L’uso delle PULL requests

![[image 128.png]]

Tramite le PULL request gli integratori possono controllare anche la qualità del codice, ma cio’ è maggiormente fatto tramite processo di **Code review**.

Le PULL request servono maggiormente per sollecitare contribuzioni al codice, così che possano contribuire anche chi non ha accesso diretto alla repository.

  

### Accettazione delle PULL requests dagli integratori

![[image 129.png]]

  

Come si puo’ vedere il fattore maggiore è **qualità del codice e stile.**

Molte volte pero’ si tiene conto anche degli aspetti tecnici.

  

### Determinazione della qualità del codice dagli integratori

![[image 130.png]]

  

Con **test cases** il procedimento diventa molto meno tedioso rispetto ad una valutazione soggettiva degli integratori.

  

### Come viene data la priorità delle PULL requests dagli integratori

Si da priorità a questi fattori:

- Se è un cambiamento importante al progetto
- Se è urgente per la prossima release
- Se è piccolo puo’ essere revisionato facilmente
- Se il cambiamento è più recente (FIFO)
    - Comunque viene data priorità ai bug fix

  

### Come avere a che fare con una PULL request come integratore

![[image 131.png]]

  

## Contributore

### Come controllare la qualità del codice come contributore

![[image 132.png]]

  

### Come avere a che fare con le PULL requests come contributore

![[image 133.png]]

  

## Assesment della qualità del codice tramite Ispezione del codice

Generalmente fatto tramite passaggio di **peer-review**, da developer a developer, dove si guarda, con processi definiti, per difetti o problemi di design.

Principali componenti della ispezione del codice:

- **Autore (contributore)**
    - La persona che ha creato il prodotto (artefatto) che è in ispezione
- **Moderatore (integratore)**
    - Leader della ispezione, la schedula e la coordina
- **Ispettore (reviewer)**
    - Colui che crea domande, propone soluzioni e trova problemi, tramite lavoro di critica
- **Recorder**
    - Colui che documenta i difetti e i problemi di design trovati durante l’ispezione

  

### Il processo di Fagan

![[image 134.png]]

  

Nuovo artefatto ricevuto, il moderatore pianifica l’ispezione:

- Trova chi deve ispezionare
- Definisce obiettivi chiave dell’ispezione
- Schedula un meeting
- Prepara e distribuisce il pachetto di ispezione

  

---

  

![[image 135.png]]

  

L’autore descrive il background dell’artefatto e le reagioni dei suoi cambiamenti, agli ispettori.

  

---

  

![[image 136.png]]

  

L’ispettore determina individualmente se ci sono problemi o difetti.

Nel caso, l’ispettore richiede informazioni all’autore.

  

---

  

![[image 137.png]]

  

Moderatore, ispettori e autore si incontrano, e una persona prende il ruolo di reader, che presenta il materiale disponibile. Viene letto tutto l’artefatto e ogni ispettore dice la propria sulle parti che vengono lette.

L’autore puo’ giustificare o chiarire dei punti o delle sue decisioni.

Il recorder documenta i difetti e i problemi di design trovati.

  

---

  

![[image 138.png]]

  

L’autore fa le modifiche all’artefatto basandosi alle azioni pianificate nel meeting e documentate dal recorder.

Ovviamente anche questi cambiamenti verranno verificati dagli ispettori.

L’autore potrà considerare anche cambiamenti ulteriori, che passeranno sempre dagli ispettori.

---

  

![[image 139.png]]

  

L’artefatto è stato migliorato ed è pronto per essere inserito nel codice.

  

### Checklists di ispezione

Da creare e aggiornare, sono delle linee guida utili per trovare le ragioni degli errori, e devono essere brevi, perchè i meeting devono essere brevi, essendo molto più efficaci.

  

### Key points

- Post-mortem analysis
    - Dopo ogni ispezione, i developer devono ricavarne qualcosa, miglioramenti con le proprie conoscenze o magari miglioramento della qualità di testing
- Costi della code inspection
    - Non tutti i cambiamenti possono essere formalmente ispezionati, essendo il processo difficile, anche per questo i team devono essere piccoli
- Misurazione di efficacia e efficienza
    - Il processo dovrebbe funzionare bene, quindi una metrica come “difetti trovati per ogni ora di meeting” dovrebbe essere ben descrittiva
- Code ispection sono una challenge sociale
    - Il tempo impiegato da tutto il team deve essere riconosciuto ugualmente, quindi i reviewers devono essere meno crudeli, e gli autori devono tenere conto dei feedback ricevuti
- L’ispezione del codice non è una valutazione
    - Le ispezioni non devono servire a valutare la qualità dei reviewers o dei developers, e nemmeno a darsi la colpa a vicenda

  

  

## Code Inspection tradizionale vs Modern Code Review

  

![[image 140.png]]

  

Rispetto a prima, il processo è collaborativo e asincrono.

  

## Modern Code Review

### Perchè i developer lo fanno?

![[image 141.png]]

  

### Qual’è il risultato?

![[image 142.png]]

  

### 11 best practices

![[image 143.png]]

  

1. Review meno di 200-400 linee di codice alla volta.

  

![[image 144.png]]

  

1. Inspection rate di meno di 300-500 linee di codice per ora.

  

![[image 145.png]]

  

1. Fare review lenta, col proprio tempo, ma mai più di 60-90 minuti

  

![[image 146.png]]

  

1. L’autore dovrebbe commentare il codice prima della review

  

![[image 147.png]]

  

1. Determinare obiettivi quantificabili così da poter usare delle metriche di misurazione

  

![[image 148.png]]

![[image 149.png]]

![[image 150.png]]

![[image 151.png]]

  

1. Creare una checklist

  

![[image 152.png]]

  

1. Verificare che i problemi sono stati risolti (in un altro momento)

  

![[image 153.png]]

  

1. Il manager deve mandare avanti una buona pratica di code review

  

![[image 154.png]]

  

1. Evitare l’effetto BIG BROTHER
    1. Non bisogna stare a monitorare intenzioni e comportamenti di qualcuno, e il potere dato non deve essere abusato per farne cio’, ma per essere usato per lo scopo primario

  

![[image 155.png]]

  

1. Fare del code review, prima di dire che lo si sa fare (per capirlo)

  

![[image 156.png]]

  

1. Migliorare il codice volta dopo volta, e non tutto assieme, sarebbe impossibile pretenderlo

  

### Considerazioni

In molti casi i tool automatici e statici di analisi sono molto utili allo scopo di code review.

E ovviamente trovare reviewers bravi è un compito arduo, nonostante i tool automatici essi devono essere sempre presenti, non potendo battere l’esperienza.

Bisogna inoltre condividere la conoscenza, e a questo scopo tutti i developer devono agire come reviewers.

Poi bisognerebbe migliorare il processo appena ci sono delle nuove informazioni.

Tutte le best practices dovrebbero essere tracciate e tenute in una wiki page.

Al codice cambiato, bisognerebbe allegare anche il codice di test, che potrà essere usato dai reviewers per determinare la qualità dei cambiamenti e capire come funziona il codice stesso: **i test difatti servono come documentazione.**

Motivare ogni commento in maniera appropriata per evitare socio-technical issues e per renderli più diretti e chiari.