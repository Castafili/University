---
date: 25/09/26
tags:
  - UniPG
  - basi
---
# Concetti e Architetture di un Sistema di BD


## Modelli dei Dati


> [!Definition] Definizione
> **Modello dei dati**: insieme di concetti per descrivere la struttura di una BD e le operazioni di manipolazione dei dati

Il modello dei dati puo includere concetti per specifiicare l'aspetto dinamico di una BD, oltre alle operazioni di base (inserimenti, aggiornamenti cancellazioni...). Questo permette al progettista della BD di specificare delle *operazioni definite dall'utente* (Es. l'operazione calcola_media applicata ad uno studente). Nel modello relazionale (quello che vederemmo noi) esiste la possibilita di associare il comportamento alle relazioni

---

## Categorie Modelli dei Dati

Esistono varie categorie: quelle ad **Alto Livello** o **concettuali**, che forniscono concetti vicini concettualmente alla percezione dei dati degli utenti finali.
Esistono poi i modelli a **Basso Livello** o **Fisici**, i quali forniscono concetti che descrivono dettagli sulla memorizzazione fisica dei dati.
Infine esistono modelli **Implementabili**, sono una via di mezzo tra i due, nascondono dei dettagli di memorizzazione, ma possono essere implementati direttamente sul calcolatore.

---

## Schemi vs Istanze

Per qualsiasi modello dei dati l'importante è la distinzione tra la descrizione della BD e la BD in se.

Lo schema è la descrizione della BD e viene specificata durante la fase di progettazione, indica i "frame" delle tabelle (i titoli delle categorie).
Possono essere rappresentati graficamente tramite un **diagramma di schema** e descrive alcuni aspetti dello schema (come ad esempio le assoccazioni).

Invece le istanze (o stato) di una BD si parla di dati della BD in un particolare istante di tempo. In una BD, ogni costrutto ha un proprio insieme corrente di istanza.

Esistono alcune istanze con importanza, ovver l'istanza **iniziale** che è lo stato iniziale della BD nel momento che viene popolata (caricata con dati iniziali) per la prima volta. Ed esiste l'istanza **valida** la quale soddisfa la strutture ed i vincoli specificati nello schema dell BD.

Lo schema *solitamente* non cambia frequentemente, mentre invece le istanze cambiano igni volta che la BD viene aggiornata.

---

## Architettura a Tre Livelli


Una proposta per supportare le caratteristiche di un DBMS di:
- Indipendenza dei dati
- VIste multiple sui dati
Ed è utile per l'illustrazione e per spiegare l'organizzazione di un DBMS.

Gli schemi DBMS sono definiti in **tre livelli**:
1) **Schema Interon**: per la descrizzione della memorizzazione fisica dei dati (come ad esempio, gli indici)
	- Di solito usa un modello **fisico** (od anche implementabile)
2) **Schema Concettuale**: Per descrovere le strutture ed i vincoli sulla BD per una user class
	- Usa un modello **concettuale** (od anche implementabile)
3) **Schema Interno**: Per la descrizione delle viste degli utenti
	- Si usano gli stessi modelli per lo schema concettuale

QUesta mappatura è necessare per trasformare le richieste ed i dati tra i vari livelli di schema
- Programmi riferiscono allo schema esterno, e sono mappati dal DBMS verso lo schema interno per l'esecuzione
- I dati estratti dal livello interno del DBMS vengono riformattati per corrispondere alle viste esterne degli utenti (ES. FOrmattazione del risultato di una query SQL)

---

## Indipendenza Dati

Indipendenza Dati Logica:
Capacita aporre cambiamenti a schema concerttuale senza il bisogno di cambiare gli schemi esterni ed i programmi applicativi associati

Indipendenza Dati Fisica:
- Capacita di aporre cambiamenti allo shcema interno senza dover cambiare lo schema concettuale
- Es. schema interno potrebbe essere modificato in seguito alla creazione dinuovi indici per ottimizzare le perfomrance del DBMS

In un DBMS che supporta l'indipendenza dei dati, se uno schema viene modificato ad un livello piu basso è necessario modificare solo il mapping con i livelli di schema piu alti. I livelli, invece, piu alti saranno inalterati, cosi che i programmi che riferiscono agli schemi esterni vengono preservati.

---

## Linguaggi DBMS

+++


---

## Tipi di DML

I linguaggi ad **alto livello** o **non procedurali**, come SQL (che è quello che useremo), sono dichiarativi, ovvero specificano quali dati reperire invece che come procedere all'interogazione della BD, è "set-oriented"

Invece, i linguaggi di **basso livello** o **procedurali**, reperiscono dati procedendo record per record e sono necessari cstrutti di loop e puntatori per reperire insiemi di record\

## Interfacce

+++

---


## Architettura

+++

---

## Classificazione DBMS

+++

---

## Modello Gerarchico

Rappresenta i dati come strutture gerarchiche ad albero, partendo da un dato padre si accede ai dati figli da qui essi dipendono, è stato definito durante la prima fase di sviluppo dei DBMS, implementato da IBM. Non esiste un linguaggio standard per il modello gerarchico. Un DML diffuso è il linguaggio DL/1 del sistema IMS.

Un vantaggio sarebbe il **rispecchiamento** della natura gerarchica di una molteplicita di domini.
Come svantaggi invece ha delle regole rigide, impste dalla struttura gerarchica, sull'esecuzione di aggiornamenti ed interrogazioni. Dato lo scarso spazio l'ottimizzazione automatica delle query non è una cosa semplice. Non è pensato per la rappresentazione efficace di relazioni N:M. Ed infine, la definizione di relazioni piu generiche richiede l'introduzione di duplicati.

---

## Modello Reticolare 

+++

---

## Modello Relazionale

Proposto nel '70 da Codd, ed i primi sistemi commerciali nel '81-'82
+++

---

## Modello ad Oggetti

Il modello ad oggetti definisce BD in termini di oggetti, delle loro proprieta, e delle operazioni associate. Incorporano anche molte caratteristiche del paradigma ad oggetti (tipi da dati astratt, incaplulamento, ereditarieta...). Gli OODBMS iniziano ad essere piu diffuse alla fine degli anni '80, inizialmente considerate come concorrenti alle BD relazionali, mentre oggi la loro penetrazione nel mercato BD rimane sotto al 5.

---

Modello Ibrido Relazionale ad Oggetti



Source: [[00 - Basi di Dati e Sistemi Informativi]]

---
Created: 