  

# ==Ciclo di vita del software==

---

Il ciclo di vita di un software inizia alla suo concepimento e finisce quando non è più possibile farne uso. E’ composto di più fasi, come abbiamo già visto:

- Concept Phase
- Requirement Phase
- Design Phase
- Implementation Phase
- Test Phase
- Installation
- Checkout Phase
- Operational Phase
- Maintenance Phase
- Retirement Phase

## Ciclo di sviluppo del software

Il ciclo di sviluppo del software inizia nel momento in cui si concepisce l’intenzione di voler sviluppare il software, e finisce con la sua consegna. E’ composto di più fasi:

- Requirement Phase
- Design Phase
- Implementation Phase
- Test Phase
- Installation Phase
- Checkout Phase

Certe volte, per il ciclo di sviluppo, si ha un tempo di fine che corrisponde anche solo a semplicemente il momento in cui il software non viene più mantenuto, ma continua a funzionare, o comunque l’intero ciclo di vita.

### Modello di Ciclo di vita del software

Descrive o prescrive come un sistema viene o dovrebbe essere sviluppato.

> _I modelli di processo software sono precise, formalizzate descrizioni di  
> dettaglio delle attività, degli oggetti, delle trasformazioni e degli eventi  
> che includono strategie per realizzare, ottenere l’evoluzione del software.  
> _

### Fasi CVS: alto livello

- **Definizione**: si occupa del **cosa**
    - Determinazione requisiti, informazioni da elaborare, aspettative, vincoli e criteri
- **Sviluppo**: si occupa del **come**
    - Definizione del progetto, dell’architettura, delle strutture dati e dei dettagli procedurali, traduzione del progetto nel linguaggio di implementazione, collaudi
- **Manutenzione**: si occupa delle **modifiche**
    - Correzioni, adattamenti, miglioramenti, prevenzioni

# ==Tipi di CVS==

---

## ==Cascata==

- Sequenza lineare di fasi, senza ricicli, con separazione di fasi e attività (senza overlap)
- Presenta uscite intermedie, tipo la documentazione
- Consente un controllo costante dell’evoluzione del progetto

Per ogni fase **si raccolgono attività omogenee** in tecnologie e skill, e le se suddivide in **tasks**, da cui si ottengono prodotti (**deliverables**) e in cui vengono eseguiti controlli (**quality control**).

Alla fine di ogni fase si hanno punti rilevanti (**milestones**, o obiettivi), e gli output di ognuna sarà l’input della prossima fase, e in nessun caso normale si possono modificare dopo il loro completamento (se non con specifiche e sistematiche attività di **modifica**).

![[image 26.png]]

  

### Fasi progettuali

- _Specifica dei requisiti_
- _Progetto di sistema_
    - Modello cartaceo
- _Progetto di dettaglio_
    - Modelli dettagliati delle parti
- _Costruzione del sistema_
- _Test dei componenti_
- _Test di integrazione delle componenti_
- _Test di sistema_
    - Deve rispettare lpe specifiche richieste
- _Installazione_
    - Avvio e consegna ai clienti
- _Manutenzione_

![[image 27.png]]

  

### Studio di fattibilità

Studio preliminare costi e benefici, il cui **obiettivo** è SE avviare il progetto, le opzioni adeguate e le risorse necessarie.

L’output sarà il **documento di fattibilità**.

  

### Analisi dei requisiti

Analisi dei bisogni dell’utente e del dominio del problema, coinvolge committente e ingegneri del software. L’**obiettivo** è descrivere funzionalità e qualità richieste.

![[image 28.png]]

L’**output** corrispondente è un documento di specifica dei requisiti, un manuale utente e un piano di accettazione del sistema.

  

### Progettazione

Definisce una struttura per il software scomponento il sistema in componenti e moduli, definendone funzionalità e relazioni fra loro.

Si divide in

- _Design architetturale_: struttura modulare, di componenti
- _Design dettagliato_: dettagli interni a ciascun componente

  

**Obiettivo**

![[image 29.png]]

L’**output** sarà il documento di specifica di progetto.

  

### Fasi bassse

- Programmazione e test di unità
    - Ogni modulo viene codificato testato ISOLATAMENTE
- Integrazione e test di sistema
    - Si compone il sistema usando i moduli verificandone il funzionamento
    - α-test: sistema rilasciato internamente al produttore (alpha dev privata)
    - ß -test: sistema rilasciato a pochi e selezionati utenti (tipo closed beta)
- Deployment
    - Distribuzione e gestione del software all’utenza
- Manutenzione
    - Il software si evolve e segue le esigenze degli utenti, nel processo vi sono altre iterazioni delle stesse procedure precedenti

  

### Vantaggi e svantaggi

Pro:

Punto di partenza e facilmente comprensibile e applicabile

Contro:

Interazione con il cliente solo all’inizio e alla fine

Il nuovo sistema è installabile solo se terminato

  

### Punti finali

La completezza delle specifiche non è possibile averla all’inizio, evolve durante le fasi.

Di fatti non esiste una separazione fra specifica, progettazione e produzione.

Realisticamente overlap e ricicli devono esistere.

### Variante: Retroazione (Feedback)

![[image 30.png]]

![[image 31.png]]

  

### Variante: Modello a V

![[6f5ba3c0-7e63-40ea-aad4-b21d4c94e1d5.png]]

Se a destra si trova un errore, si riesegue il pezzo collegato alla fase, dalla parte sinistra.

  

## ==Prototipazione==

Come dice il nome, viene usato un prototipo per aiutare a comprendere i requisiti per valutare la fattibilità dell’approccio preso per il progetto.

Quindi, si ha una prima implementazione, una prova, per verificare fattibilità e requisiti.

Dopo questa fase di passa alla fase di produzione del sistema finale.

  

### Elementi

- **Mock-ups**: danno un’idea abbastanza completa dell’interfaccia utente e possono già essere usati per il manuale utente
- **Breadboards**: si implementano sottoinsiemi delle funzionalità critiche (**vincoli pesanti**) del sistema, tipo per carichi elevati, tempi di risposta, etc.. e produce feedbacks per come implementare la funzionalità stessa

  

### Tipi

- Prototipazione “Usa e getta”
    
    - Si cerca di precisare la comprensione dei requisiti del prodotto, partendo dai meno compresi
    
    ![[image 32.png]]
    
- Prototipazione “_Esplorativa_”
    - Si cerca di arrivare all’obiettivo finale partendo da una descrizione di massima e lavorando con il cliente, si parte dai requisiti meglio compresi

### Modello misto Cascata/Prototipi

![[832ec231-8cdb-4f61-81fd-29aa1bb3f569.png]]

  

## Approcci evolutivi o Sviluppo evolutivo

![[77bb84a7-28b1-452c-8e4e-a46a51de181b.png]]

Generalmente durante il progetto non si riesce a tener conto del processo intero di realizzazione del sistema, e il prodotto finito molte volte non ha una vera e propria struttura. Il management soprattuto ha questi problemi, dovendo supervisionare il tutto.

  

Lo **Sviluppo Evolutivo** risolve questi problemi, ma è applicabile solo a progetti medio-piccoli, singole parti di sistemi grandi o per sistemi con ciclo di vita breve.

  

### Trasformazioni formali

![[image 33.png]]

L’applicabilità qui risulta problematica quando lo sviluppo formale deve essere fatto su parti del sistema come le interfacce utente, decisamente assai complicate e impossibili da formalizzare per bene.

I costi e le competenze richieste sono molto alte, per via dell’aumento dei dettagli nell’implementazione, e **il cliente** **non comprende le specifiche formali**.

Proprio per la propria complessità e specificità, l’utilizzo è particolarmente adeguato per sistemi critici (safety o security).

  

### Sviluppo a componenti

**Si riusano componenti implementati**, per un development veloce, e ci sono diversi livelli i astrazioni per i suddetti.

Durante l’implementazione di un nuovo sistema, oltre al riutilizzo, si cerca anche di ampliare la repository di componenti per un futuro utilizzo.

Molto adatto per software Object-Oriented.

  

### Iterazioni processuali

Requisiti che cambiano spesso, e all’inizio anche più volte rework.

Correlati:

  

## Modello incrementale

Il sistema viene prodotto non per intero, problemi da cliente o produttore, magari finanziari, e viene consegnato in più rilasci.

  

Il sistema dunque è diviso in più sottosistemi con priorità differenti e vengono trattati nel progetto rispetto alla priorità assegnata.

  

E’ quindi più pesante, ed importante, l’integrazione dei nuovi sottosistemi ad ogni rilascio.

![[image 34.png]]

E’ quindi più difficile che il progetto fallisca interamente, ed è più facile fornire funzionalità a priorità alta prima di tutte le altre.

  

I rilasci iniziali servono anche come prototipazione, quindi il testing all’interno di tutto il progetto sarà maggiore sulle priorità alte, in quanto saranno le prime ad essere implementate e saranno testate per tutto il progetto partendo prima di elementi di altra priorità, fornendo maggiore stabilità più avanti nel progetto.

  

## Modello Iterativo (evolutivo) vs Incrementale

Entrambi forniscono più rilasci, però per ogni versione:

- Lo sviluppo incrementale
    - aggiunge nuovi sottosistemi e funzionalità
- Lo sviluppo iterativo
    - sistema completo che viene raffinato in tutte le componenti in modo iterativo

  

![[image 35.png]]

  

## ==Modello a spirale==

Formalizza il concetto di iterazione, usando il “**riciclo**”.

Rappresentato come una spirale e non come sequenza, ad **ogni giro** della stessa si **completa una fase**, ed ognuna non è predefinita, ma va trovata e all’interno vanno inoltre scoperti gli aspetti di valutazione più importante riguardo ai rischi.

E’ un **meta-modello**, ovvero che possono essere utilizzati uno o più modelli contemporaneamente.

  

### Spirale di Boehm

![[image 36.png]]

### Continuazione

Un progetto basato su questo modello è portato avanti **principalmente dai rischi**, ovvero che ad ogni **milestone**, che devono soddisfare entrambi fattibilità e obiettivi degli stakeholder, diminuiranno i fattori di rischio.

  

Le considerazioni principali in ogni progetto a spirale:

- rispettare obiettivi e vincoli critici
- processi o prodotti alternativi
- identificazione e risoluzione di rischi
- revisione dagli stakeholder
- dedizione per procedere (?)

  

### Modello a spirale tradizionale

![[image 37.png]]

  

### Gestione dei rischi

_Il manager ha il compito di minimizzare i rischi, tipo personale inadeguato, scheduling, budget non realistico, sviluppo di un sistema non rispettante degli obiettivi, etc.._

Altri rischi sono ritardi e costi non previsti.

**Più informazioni, meno rischi.**

  

### Modelli e rischi

- _Cascata_
    - Alti rischi per sistemi nuovi, non familiari per problemi di specifica e progetto
    - Bassi rischi per sistemi familiari e tecnologie usate note
- _Prototipazione_
    - Bassi rischi per nuovi sistemi, specifica e sviluppo vanno di pari passo
    - Alti rischi per la mancanza di un processo definito e visibile
- _Trasformazionale_
    - Alti rischi per tecnologie e professionalità richieste

  

### Problemi risolti dal modello

- Chiarezza mancante per requisiti, tecnologie scelte e la struttura del sistema, **solamente ipotesi non consolidate all’inizio**
- Manca esperienza e saper far fronte a pericoli sconosciuti

  

### Perchè?

Ogni iterazione riduce il rischio del progetto stesso, come già detto.

1. Si inizia con la costruzione di **prototipi**
    1. _**Prototipi di interazione**_ (interfacce utente) per ridurre l’incertezza dei requisiti
    2. _**Prototipi architetturali**_ (realizzazione e test di aspetti infrastrutturali) per risolvere dubbi e risci su tecnologie e struttura del sistema
2. Dopo che i rischi principali sono sotto controllo, le nuove parti del sistema vengono costruite progressivamente, integrate con le precedenti e verificate con gli stakeholder
3. Simile all’incrementale, ma
    1. L’iterativo ha una gestione sistematica dei requisiti durante la realizzazione, e ne prevede la loro ulteriore espansione o creazione di altri, come effetto dell’utilizzo del sistema stesso

  

### Flessibilità (integrazione di altri modelli)

Puo’ essere implementato il modello a cascata ulteriormente per sistemi o sottosistemi conosciuti bene.

Requisiti stabili o sottosistemi critici possono essere sviluppati con approcci trasformazionali.

Zone non specificate, interfacce utente possono usare il modello a prototipi.

  

### Vantaggi

- Esplicita la gestione dei rischi
- Determina errori già in fasi iniziali
- Obbliga il controllo alla qualità
- Integra sviluppo e manuntenzione

  

### Svantaggi

- Per contratto si specifica a priori il modello e i deliverables, e dovendo specificare vincoli, modelli, tempi di consegna e artefatti, bisogna fare un contratto dentro al contratto
- Essendo che ad ogni iterazione il progetto diventa più complesso, va controllato l’avanzamento sistematicamente, così da non avere un’eccessiva complicazione
- La riuscita è dovuta principalmente dalla collaborazione di clienti e gruppo di progetto
- Bisogna avere personale allegato solo alla valutazione di rischi
- Per poter essere usato deve essere adattato alla realtà aziendale e il team

  

# Extreme programming

Approccio moderno dove si sviluppano piccoli incrementi di funzionalità in modo veloce.

Gli stakeholder possono partecipare molto di più alle decisioni, e il codice migliora costantemente e continuamente (verifica e adeguamento in tempi molto ridotti).

### Le dodici regole

- Progettare con il cliente
- Testo funzionali e unitari
- Refactoring (riscrivere codice senza modificare funzionalità)
- Progettare al minimo
- Descrivere il sistema con una metafora, anche per la descrizione formale
- Chiunque faccia parte del progetto fa stesura del codice
- Scegliere ed utilizzare un preciso standard di scrittura del codice
- Integrare continuamente i cambiamenti al codice
- Il cliente deve essere presente e disponibile a verificare (riunioni settimanali)
- Open Workspace
- 40 ore di lavoro settimanali
- Pair Programming (due programmatori su un solo computer lavorano)