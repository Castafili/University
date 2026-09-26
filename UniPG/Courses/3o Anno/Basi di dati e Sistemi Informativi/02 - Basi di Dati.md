---
date: 25/09/26
tags:
  - UniPG
  - basi
  - review
---
# Concetti e Architetture di un Sistema di BD

## Modelli dei Dati

> [!INFO] Definizione
> **Modello dei dati**: un insieme di concetti per descrivere la struttura di una BD e le operazioni di manipolazione dei dati.

Il modello dei dati può includere inoltre concetti per specificare l'aspetto dinamico di una BD, oltre alle operazioni di base (inserimenti, aggiornamenti, cancellazioni...). Questo consente al progettista della BD di specificare un insieme di *operazioni definite dall'utente* (ad esempio, l'operazione `calcola_media` applicata ad uno studente). Nel modello relazionale (quello che vedremo noi) esiste la possibilità di associare il comportamento alle relazioni (triggers, stored procedures).

---

## Categorie Modelli dei Dati

Esistono varie categorie: quelle ad **Alto Livello** o **Concettuali**, che forniscono concetti che sono vicini alle modalità di percezione dei dati degli utenti finali.
Esistono poi i modelli a **Basso Livello** o **Fisici**, i quali forniscono concetti che descrivono dettagli sulla memorizzazione fisica dei dati.
Infine esistono modelli **Implementabili**, che sono una via di mezzo tra i due: forniscono concetti compresi dagli utenti ma nascondono alcuni dettagli di memorizzazione dei dati; si possono implementare direttamente sul calcolatore.

---

## Schemi vs Istanze

Qualsiasi sia il modello dei dati, è importante distinguere tra la descrizione della BD e la BD in sé.

Lo **schema** è la descrizione della BD e viene specificato durante la fase di progettazione della BD. Può essere rappresentato graficamente tramite un **diagramma di schema**, che ne descrive solo alcuni aspetti (come le associazioni). Ciascun oggetto dello schema (es. studente, corso...) è definito costrutto di schema.

Lo **stato** (o **istanze**) di una BD si riferisce ai dati della BD in un particolare istante di tempo. Nella BD, ciascun costrutto dello schema ha un proprio insieme corrente di istanze.

Esistono stati con particolare importanza:
- **Stato Iniziale**: si riferisce allo stato della BD nel momento in cui viene per la prima volta popolata o caricata con i dati iniziali.
- **Stato Valido**: è lo stato della BD che soddisfa la struttura ed i vincoli specificati nello schema della BD.

Lo schema di una BD non cambia frequentemente (viene anche detto *intensione*), mentre lo stato di una BD cambia ogni volta che la BD viene aggiornata (viene anche detto *estensione*).

---

## Architettura a Tre Livelli

È una proposta per supportare le caratteristiche di un DBMS di:
- Indipendenza dei dati
- Viste multiple sui dati

È utile per illustrare e spiegare l'organizzazione di un sistema di base di dati.
Definisce gli schemi DBMS in **tre livelli**:
1. **Schema Interno**: livello interno per descrivere la memorizzazione fisica dei dati e le strutture di accesso (ad esempio, gli indici). Usa tipicamente un modello dei dati **fisico**.
2. **Schema Concettuale**: livello concettuale per descrivere le strutture ed i vincoli sulla BD per una classe di utenti. Usa un modello dei dati **concettuale** oppure **implementabile**.
3. **Schema Esterno**: livello esterno per descrivere le varie viste degli utenti. Si utilizzano gli stessi modelli dei dati usati per lo schema concettuale.

L'opera di mappatura è necessaria per trasformare le richieste ed i dati tra i livelli di schema:
- I programmi fanno riferimento allo schema esterno, e sono mappati dal DBMS verso lo schema interno per essere eseguiti.
- I dati estratti dal livello interno del DBMS vengono riformattati per corrispondere alle viste esterne degli utenti (ad esempio, la formattazione del risultato di una query SQL per una pagina WEB).

---

## Indipendenza Dati

- **Indipendenza Dati Logica**: capacità di apporre cambiamenti allo schema concettuale senza dover cambiare gli schemi esterni ed i programmi applicativi associati.
- **Indipendenza Dati Fisica**: capacità di apporre cambiamenti allo schema interno senza dover cambiare lo schema concettuale. Ad esempio, lo schema interno potrebbe essere modificato in seguito alla creazione di nuovi indici per ottimizzare le performance del DBMS.

In un DBMS che supporta l'indipendenza dei dati, quando uno schema viene modificato ad un livello più basso, è necessario modificare soltanto il mapping con i livelli di schema più alti. I livelli di schema più alti rimangono invece inalterati, e ciò consente di preservare intatti anche i programmi che fanno riferimento agli schemi esterni.

---

## Linguaggi DBMS

I DBMS offrono linguaggi specifici per operare:

- **Data Definition Language (DDL)**: utilizzato dai DBA e dai progettisti della BD per specificare lo schema concettuale della BD. In molti DBMS, il DDL viene utilizzato anche per definire schemi interni ed esterni. In alcuni DBMS, vi sono linguaggi speciali dedicati: lo *storage definition language (SDL)* per gli schemi interni e il *view definition language (VDL)* per gli schemi esterni.
- **Data Manipulation Language (DML)**: utilizzato per specificare interrogazioni ed aggiornamenti. I comandi del DML possono essere applicati direttamente alla BD (*query language*) oppure possono essere integrati in un linguaggio di programmazione (linguaggio ospite) come C, C++, o Java. È possibile anche avere a disposizione apposite librerie per accedere ad un DBMS da un linguaggio di programmazione.

---

## Tipi di DML

I linguaggi di **Alto Livello** o **Non-Procedurali**, come SQL (che è quello che useremo), sono dichiarativi, ovvero specificano *quali* dati reperire piuttosto che *come* procedere all'interrogazione della BD, ed operano in modalità *set-oriented*.

Invece, i linguaggi di **Basso Livello** o **Procedurali**, reperiscono i dati procedendo record per record. Sono necessari costrutti di loop e puntatori per reperire insiemi di record.

---

## Interfacce

Esistono diversi tipi di interfacce DBMS destinate a diverse figure:

- **Stand-alone query language interface**.
- **Interfacce a DBMS per Linguaggi di Programmazione**: permettono ai programmatori di utilizzare il DML nei linguaggi di programmazione tramite:
  - *Approccio Embedded*: ad esempio embedded SQL (per C, C++...), SQLJ (per Java).
  - *API*: ad esempio JDBC per Java, ODBC per altri linguaggi di programmazione.
  - *Approccio basato su linguaggi nativi*: ad esempio PL/SQL per ORACLE o PL/pgSQL per PostgreSQL, che uniscono SQL e programmazione strutturata.
- **Interfacce User-Friendly**:
  - *Menu-based*: popolari per il WEB.
  - *Forms-based*: definite per utenti naive.
  - *Graphics-based*: sistemi point and click, drag and drop...
  - Interfacce facenti uso di linguaggi naturali.
  - Combinazioni miste, come ad esempio menu+form nelle interfacce WEB a BD.
- **Altre Interfacce**:
  - Input ed output vocale.
  - Web Browser.
  - Interfacce parametriche.
  - *Interfacce per DBA*: permettono di creare account utenti, gestire autorizzazioni, definire parametri di sistema e modificare schemi/cammini di accesso ai dati.

---

## Architettura

Le architetture dei sistemi di basi di dati si dividono principalmente in:

### Architettura Centralizzata
Prevede un singolo sistema hardware/software sia per il DBMS, che per i programmi applicativi e la gestione interfacce utenti. Gli utenti possono connettersi in remoto tramite terminali, ma tutta la computazione avviene strettamente a livello centralizzato.

### Architettura Client-Server
Questa architettura prevede la presenza di server specializzati (Server di Stampa, File Server, DBMS Server, Web Server, Email Server) per gestire specifiche funzionalità. Molteplici macchine client possono accedere alle risorse fornite, offrendo all'utente le interfacce appropriate. I client possono essere workstation senza dischi o computer equipaggiati di disco fisso con installato solo il software client, connessi ai server tramite rete (LAN, wireless...).

### Architettura Client/Server a 2 Livelli per DBMS
- Il **DBMS Server** (RDBMS, detto anche server SQL, server delle interrogazioni o server delle transazioni) gestisce tipicamente le funzionalità transazionali e di interrogazione.
- I programmi applicativi risiedono sui client e utilizzano API standardizzate (come ODBC e JDBC) per accedere al DBMS.
- In architetture diverse o sistemi a oggetti (OODBMS), alcune funzionalità vengono spostate lato client: il server si occupa della memorizzazione (pagine su disco, buffer e cache), mentre il client può gestire il dizionario dei dati, l'ottimizzazione globale delle interrogazioni e le interazioni del DBMS con i compilatori.

### Architettura Client/Server a 3 Livelli
Ampiamente usata nelle applicazioni Web, introduce un livello intermedio detto **Server delle Applicazioni** (o Server Web).
Questo livello memorizza le regole aziendali (procedure e vincoli) per accedere ai dati, fungendo da tramite per passare i dati elaborati tra il server BD e i client. Tale architettura migliora sensibilmente la sicurezza, permettendo il controllo delle credenziali prima di inoltrare le richieste al server della BD.

---

## Classificazione DBMS

I DBMS possono essere classificati in base a molteplici fattori:
- **In base al modello dei dati**: Tradizionali (relazionale, gerarchico, reticolare) o Emergenti (ad oggetti, relazionale ad oggetti).
- **In base al numero di siti**: sui quali è distribuita la BD, dividendoli in centralizzati vs distribuiti.
- **General purpose vs special purpose**.
- **In base a criteri di costo**.

---

## Modello Gerarchico

Rappresenta i dati come strutture gerarchiche ad albero. A partire da un dato padre, si accede ai dati figli da cui essi dipendono. È stato definito durante la prima fase di sviluppo dei DBMS (negli anni '60) ed implementato da IBM e North American Rockwell intorno al 1965. Non esiste un linguaggio standard per il modello gerarchico, ma un DML diffuso è il linguaggio `DL/1` del sistema IMS.

> [!INFO] Pro e Contro
> **Vantaggi**: Rispecchia la natura gerarchica di una molteplicità di domini.
> **Svantaggi**: La struttura gerarchica impone regole rigide sull'esecuzione di aggiornamenti ed interrogazioni, lasciando scarso spazio per l'ottimizzazione automatica delle query. C'è un'alta dipendenza dei programmi dalle strutture e non si presta a rappresentare in modo efficiente le relazioni N:M (le relazioni più generiche richiedono l'introduzione di duplicati).

---

## Modello Reticolare 

Il primo DBMS reticolare venne implementato da Honeywell nel 1965 (IDS System) e supportato in seguito dalla CODASYL (Conference on Data Systems Languages / DBTG Report del 1971). Fu alla base di una varietà di sistemi in voga fino a metà degli anni '80 come IDMS, DMS 1100, IMAGE, e VAX-DBMS.
Questo modello rappresenta i dati come tipi di record. I record sono legati tra loro tramite puntatori che permettono all'utente di accedere ai dati più facilmente, senza i vincoli imposti dal modello gerarchico.

> [!INFO] Pro e Contro
> **Vantaggi**: Un record può avere uno o più record padri, evitando così problemi di ridondanza. Ogni nodo può essere il punto di partenza per raggiungere un determinato campo, permettendo di modellare agevolmente relazioni N:M.
> **Svantaggi**: Implica la gestione di un complesso reticolo di puntatori all'interno della BD. Anche in questo caso si ha uno scarso spazio per l'ottimizzazione automatica delle query.

---

## Modello Relazionale

Proposto nel 1970 da E. F. Codd (IBM), vide nascere i primi sistemi commerciali nel 1981-82.
Oggi è integrato in molteplici prodotti commerciali (come DB2, ORACLE, MS SQL Server, INFORMIX, SYBASE). È passato per un progressivo processo di standardizzazione SQL (SQL-89, SQL-92, SQL99...). Ad oggi rappresenta il prodotto largamente dominante nel mercato dello sviluppo di BD.

---

## Modello ad Oggetti

Il modello ad oggetti definisce la BD in termini di oggetti, delle loro proprietà, e delle operazioni associate. Incorporano molte caratteristiche del paradigma ad oggetti quali i tipi di dati astratti, l'incapsulamento e l'ereditarietà.
Gli OODBMS (Object-Oriented DBMS) iniziarono a diffondersi alla fine degli anni '80. Inizialmente considerati concorrenti insidiosi alle BD relazionali, oggi la loro penetrazione complessiva nel mercato dei prodotti BD rimane marginale, al di sotto del 5%.

---

## Modello Ibrido Relazionale ad Oggetti

Si tratta del trend più recente, inaugurato con l'avvento di Informix Universal Server. I sistemi RDBMS tradizionali iniziano a incorporare stabilmente concetti relativi alle basi di dati ad oggetti, fondendosi nel modello relazionale ad oggetti.
Tra gli altri, questo modello ibrido è supportato dalle ultime versioni di Oracle-10i, DB2, e PostgreSQL, con standard appositi inclusi fin da SQL'99.

---

Source: [[00 - Basi di Dati e Sistemi Informativi]]

---
Created: 25/09/26