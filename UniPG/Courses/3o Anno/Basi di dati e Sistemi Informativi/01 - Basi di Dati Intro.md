---
date: 21/09/26
tags:
  - UniPG
  - basi
  - review
---
# Introduzione alle Basi di Dati e Utenti di BD

## Informazioni sul Corso ed Esame
- **Libro di riferimento:** "Sistemi di Basi di Dati (Fondamenti)" - Autori: R. Elmasri e S. B. Navathe
- **Laboratorio:** Martedì, con utilizzo di PostgreSQL
- **Ufficio docente:** 6° piano, con prenotazione tramite email
- **Modalità d'esame:** Due compiti di esonero
  1. 09/11/2026 (durante la lezione)
  2. 18/11/2026

---

> [!INFO] Curiosità Storica
> Nel 1969 viene introdotto da IBM il sistema "IMS" per la gestione dei dati.

## Nozioni Preliminari
- **Base di Dati (BD):** Collezione di dati correlati.
- **Dati:** Fatti noti che possono essere memorizzati, aventi un significato implicito.

### Proprietà Implicite di una Base di Dati
1. **Rappresenta un certo aspetto del mondo reale** (**mini-mondo** o *universo del discorso*); i cambiamenti del mini-mondo si riflettono direttamente sulla BD.
2. **Collezione di dati logicamente coerenti** con un significato intrinseco.
3. **Progettata, costruita e popolata con dati per uno scopo specifico**, rivolta a un determinato gruppo di utenti e applicazioni di loro interesse.

> [!INFO] Sistema di Gestione di BD (DBMS) e Sistema di BD
> - **DBMS (Database Management System):** Sistema software che facilita i processi di definizione, costruzione, manipolazione e condivisione di BD per varie applicazioni.
> - **Sistema di Basi di Dati:** Base di Dati + Software DBMS.

**ref a Figure 1.1 slides 1a lezione**

---

## Funzioni Principali di un DBMS
- **Definizione della BD:** Specificare tipi di dati, strutture e vincoli coinvolti.
- **Costruzione della BD:** Immagazzinare i dati su un adeguato supporto di memoria (popolamento).
- **Manipolazione della BD:**
  - *Interrogare* la BD per reperire dati specifici e generare prospetti/report.
  - *Aggiornare* la BD per rispecchiare i mutamenti del mini-mondo.
  - *Accedere* alla BD attraverso applicazioni web.
- **Condivisione della BD:** Consentire accessi contemporanei a più utenti e applicazioni senza violare la consistenza dei dati.
- **Protezione e Manutenzione:**
  - Protezione del sistema contro i crash.
  - Sicurezza contro accessi abusivi da parte di utenti malintenzionati.
  - Manutenzione della BD e delle applicazioni nel corso del ciclo di vita.
- **Processing Attivo:** Esecuzione automatica di azioni sui dati al verificarsi di determinati eventi (DBMS attivi).
- **Presentazione e Visualizzazione dei Dati**.

---

## Caratteristiche dell'Approccio con BD
Rispetto alla tradizionale gestione mediante file, l'approccio con BD si contraddistingue per quattro proprietà essenziali:

### 1. Natura Autodescrittiva del Sistema BD
- Il sistema contiene sia i dati sia una descrizione completa della loro struttura e dei vincoli.
- Tale definizione è memorizzata nel **catalogo di sistema**, contenente informazioni su:
  - Struttura di ciascun file
  - Tipo e formato di memorizzazione di ogni dato
  - Vincoli imposti sui dati
- Le informazioni archiviate nel catalogo prendono il nome di **METADATI**.
- Grazie a questa natura autodescrittiva, il software del DBMS può interagire con diverse basi di dati estraendone la definizione direttamente dal catalogo.

**(Per esempio catalogo) ref a Figure 1.3 slides 1a lezione**  
**ref a Figure 1.4 slides 1a lezione**

### 2. Separazione tra Dati e Programmi ed Astrazione dei Dati
- **Astrazione dei dati:** Il DBMS offre agli utenti una rappresentazione concettuale evitando i dettagli dell'effettiva memorizzazione fisica. Tale schema concettuale costituisce il **modello dei dati**.
- **Separazione dati-programmi:** La struttura dei file è conservata nel catalogo del DBMS, separata dai programmi applicativi di accesso.
- Questa caratteristica prende il nome di **indipendenza tra programmi e dati**: è possibile variare strutture fisiche o formati di memorizzazione senza dover modificare i programmi applicativi esistenti.

### 3. Supporto di Viste Multiple sui Dati
- Un sistema BD supporta molteplici utenti, ciascuno con prospettive o esigenze informative distinte.
- **Vista:**
  - Un sottoinsieme della BD.
  - Un insieme di dati virtuali, ovvero non memorizzati fisicamente in modo esplicito, ma derivati dinamicamente dai dati presenti nella BD.

**ref a Figure 1.5 slides 1a lezione**

### 4. Condivisione Dati e Gestione Transazioni in Ambienti Multiutenti
- Il DBMS multiutente garantisce l'accesso contemporaneo concorrente per mezzo di un sottosistema per il **controllo della concorrenza**, assicurando efficacia e correttezza.

> [!INFO] Transazione e Proprietà Fondamentali
> Una **transazione** è un processo o programma in esecuzione che compie una o più operazioni di accesso (lettura o aggiornamento) alla base di dati. Il DBMS garantisce:
> - **Isolamento:** Ciascuna transazione viene eseguita come se fosse del tutto isolata rispetto alle altre, anche con centinaia di transazioni attive in parallelo.
> - **Atomicità:** Le operazioni di una transazione vengono completate nella loro interezza oppure, in caso di errore, nessuna operazione viene eseguita affatto (*tutto o niente*).

---

## Gli Utenti di una BD

### Gli "Attori in Scena"
Coloro che progettano, amministrano o utilizzano direttamente la BD:
- **Progettisti:** Individuano i dati da memorizzare e selezionano le strutture idonee alla rappresentazione e memorizzazione, interfacciandosi con gli utenti finali per raccoglierne i requisiti.
- **Amministratori (DBA - Database Administrator):** Autorizzano gli accessi, coordinano e monitorano l'uso del sistema e risolvono criticità legate a violazioni di sicurezza o degrado delle prestazioni.
- **Utenti Finali:** Accedono alla BD per motivi operativi:
  1. *Occasionali:* Accedono sporadicamente con necessità informative variabili.
  2. *Non Esperti:* Interagiscono con transazioni predefinite e standardizzate (*canned transactions*).
  3. *Esperti:* Figure (es. ingegneri, scienziati) con piena familiarità con le funzionalità avanzate del DBMS.
  4. *Indipendenti:* Gestiscono BD ad uso personale tramite interfacce applicative intuitive.
- **Analisti di Sistema e Programmatori:** Gli analisti rilevano le necessità degli utenti finali e definiscono le specifiche delle transazioni standard; i programmatori applicativi le sviluppano, collaudano e mantengono.

### Gli "Attori dietro le Quinte"
Figure che sviluppano e mantengono l'infrastruttura software e hardware del DBMS (sviluppatori DBMS, sistemisti, operatori di supporto) senza utilizzare la base di dati per propri scopi di business.

---

## Vantaggi dell'Uso di un DBMS

1. **Controllo della Ridondanza:**
   - *Problema:* La ridondanza non controllata (tipica della gestione tradizionale a file) provoca rischi di inconsistenza.
   - *Soluzione:* **Ridondanza controllata**. Il DBMS gestisce l'eventuale duplicazione per velocizzare le interrogazioni, imponendo verifiche di consistenza definite in fase di progettazione e applicate automaticamente a ogni aggiornamento.
   
   **ref a Figure 1.6 slides 1a lezione**

2. **Divieto all'Accesso Non Autorizzato:**
   - *Problema:* Limitare l'accesso ai soli utenti legittimati.
   - *Soluzione:* Presenza di un sottosistema di sicurezza e autorizzazione gestito dal DBA mediante assegnazione di account e privilegi.

3. **Memorizzazione Persistente degli Oggetti di Programma:**
   - *Problema:* **Conflitto di impedenza (impedance mismatch)**, dovuto all'incompatibilità tra le strutture dati del linguaggio di programmazione e quelle fornite dai DBMS relazionali tradizionali.
   - *Soluzione:* Nascita delle **basi di dati orientate agli oggetti (OODBMS)**, capaci di integrarsi nativamente con linguaggi come C++ e Java eseguendo conversioni automatiche.

4. **Strutture di Memorizzazione per l'Esecuzione Efficiente delle Interrogazioni:**
   - Adozione di **indici** (strutture ad albero o tabelle hash) per velocizzare le ricerche e gli accessi su disco.
   - Il DBA seleziona gli indici nel progetto fisico e nell'ottimizzazione.
   - Il modulo **Query Optimizer** stabilisce il piano di esecuzione ottimale, mentre il **modulo di buffering** mantiene porzioni della BD in memoria principale.

5. **Backup & Recovery:** Funzioni integrate per il ripristino automatico a seguito di guasti software o anomalie hardware.
6. **Molteplicità di Interfacce Utente:** Form semplificati per utenti non esperti, tool grafici e interfacce integrate nei linguaggi di programmazione.
7. **Rappresentazione di Relazioni Complesse:** Capacità di modellare e navigare associazioni articolate tra dati differenti in modo rapido e coerente.
8. **Impostazione dei Vincoli di Integrità:** Definizione e applicazione automatica di regole di consistenza specifiche per il dominio applicativo.
9. **Inferenze e Azioni Tramite Regole:**
   - *BD Deduttive:* Meccanismi basati su regole per inferire nuove informazioni dai dati presenti.
   - *BD Attive:* Definizione di trigger e stored procedure in grado di avviare azioni automatiche al verificarsi di eventi e condizioni stabilite.
10. **Potenziale per Imporre Standard:** Standardizzazione a livello aziendale di formati e convenzioni.
11. **Tempi Ridotti per lo Sviluppo Applicativo:** Disponibilità di servizi centralizzati che accelerano la creazione di nuove applicazioni.
12. **Flessibilità ed Evolutività:** Possibilità di aggiornare schemi e strutture dati senza inficiare i programmi già in produzione.
13. **Disponibilità di Informazioni Aggiornate:** Aggiornamenti immediatamente visibili a tutti gli utenti concorrenti.
14. **Economie di Scala:** Riduzione dei costi ed eliminazione delle ridondanze operative tra dipartimenti diversi.

---

## Quando Non Usare un DBMS
L'adozione di un DBMS comporta spese generali (investimenti in licenze, hardware, formazione e overhead di calcolo per concorrenza e sicurezza). È conveniente l'approccio convenzionale a singoli file in caso di:
- Basi di dati e applicazioni semplici, ben definite e senza previsione di aggiornamenti o modifiche.
- Requisiti stringenti di **tempo reale (real-time)** che non tollerano l'overhead del DBMS.
- Assenza di accessi concorrenti multiutente.

---

## Cenni Storici sull'Evoluzione dei Sistemi di BD

### Anni '60 - '70: Modelli Reticolari e Gerarchici
- Utilizzati su grandi mainframe per gestire i dati di organizzazioni complesse (aziende, ospedali, banche, università) divisi in sistemi gerarchici, reticolari e inverted file.
- *Limiti:* Forte commistura tra legami concettuali e memorizzazione fisica/disposizione su disco; presenza di sole interfacce verso linguaggi di programmazione.

### Fine Anni '70: L'Avvento del Modello Relazionale
- Proposto da **Edgar F. Codd** (celebre paper ACM del 1970) per separare la memorizzazione fisica dalla rappresentazione concettuale e dotare le basi di dati di un solido fondamento matematico.
- Introduzione dei linguaggi di interrogazione ad alto livello (SQL).
- Nonostante la lentezza iniziale dovuta all'assenza di puntatori espliciti, i DBMS Relazionali (**RDBMS**) sono oggi i sistemi dominanti per le applicazioni tradizionali.

### Dagli Anni '80 a Oggi
- **Fine Anni '80:** Basi di dati a oggetti, sviluppate per gestire strutture complesse e ovviare al mismatch con i linguaggi OOP; diffusione rimasta limitata per assenza di standard e complessità del modello.
- **Anni '90 (E-commerce e Web):** Integrazione dinamica tra pagine web e DBMS; adozione di **XML** come standard primario per l'interscambio eterogeneo di dati.
- **Nuove Applicazioni e Information Retrieval (IR):** Estensione a dati scientifici, serie temporali, immagini, video e text-retrieval combinando tecniche di Information Retrieval e motori DBMS evoluti.

---

Source: [[00 - Basi di Dati e Sistemi Informativi]]

---
Created: