---
date: 21/09/26
tags:
  - UniPG
  - basi
  - review
---
Martedi: Dedicato al laboratorio

Lezione basata su libro: "Sistemi di Basi di Dati (Fondamenti)". Autori: R. Elmosri e S.B Novathe

Esame: Due compiti (esonero):
1) 09/11/2026 durante la lezione
2) 18/11/2026 

PostgreSQL per laboratorio

Ufficio: 6o piano, con prenotazione tramite email



---

>[!INFO] Curiosita
>1969 "IMS" definito da IBM per gestione dati



Nozioni Preliminai:
	Base di Dati: Collezione di dati correlati
	Dati: Fatti noti, possono essere memorizzati, con significato implicito

Proprieta Basi di Dati:
1) Rappresenta aspetto mondo reale (mini-mondo / universo del discorso)
2) Collezione di dati logicamente coerenti con significato intrinseco
3) Progettata, costruita e popolata da dati con scopo specifico. Ha determinato gruppo utenti e applicazioni interessi per utenti

Sistema di Gestione BD (DBMS):
	Sistema software, facilita processi di definizione, costruzione, manipolazione e condivisione BD per varie applicazioni.

Sistema di Basi di Dati:
	Base di Dati + DBMS

**ref a Figure 1.1 slides 1a lezione**

---
## DBMS

Funzioni Generali:
	- Definizione BD -> indicare i tipi di dati, la struttura ed i vincoli
	- Costruire BD, immagazinando i dati su supporto di memoria adeguato (popolare la BD)
	- Manipolare BD
		- Interrogare BD (Reperire dati specifici e generare report partendo dai dati)
		- Aggiornare BD (Rispecchio cambiamenti mini-mondo)
		- Accedere a BD tramite web
	- Condividere BD, permesso a piu utenti e applicazzioni ad accedere senza violare consistenza dati
	- Protezione + Manutenzione BD
		- Protezione sistema da crash
		- Protezzione da accessi di utenti malintenzionati
		- Manutenzione BD + applicazioni relativo del sistema di BD
	- Processing attivo, per attivare autom. molteplici azioni sui dati dopo determinati eventi
	- Funzioni di Presentazione + Visualizzazione dati


---

## Approccio BD

Principali caratteristiche:
	Natura autodescrittiva di sistema BD
	Separazione programmi - dati. Astrazione dei dati
	Supporto di viste multiple dei dati
	Condivisione dati + gestione transazioni in ambiente multiutente


### Natura Autodescrittiva Sistema BD:
- Sistema BD contiene: dati stessi + descrizione completa della sua natura e dei suoi vincoli
- Definizione -> memorizzata nel **catalogo** di sistema, mantenute informazioni come:
	- Struttura ciascun file
	- Tipo + formato di memorizzazione $\forall$ dato
	- Vincoli sui dati
- Informazione memorizzate nel catalogo: **METADATI**
- I paccheti software di un DBMS possono interagire con diverse applicazioni di DB
- Software del DBMS puo accedere a diverse basi di dati estraendone le definizioni dal catalogo

**(Per esempio catalogo) ref a Figure 1.3 slides 1a lezione**

### Separazione Dati e Programmi, e Astrazione sui Dati

Astrazione dati:
- DBMS fornisce a utenti rappresentazione concettuale dei dati. NO dettagli sulla memorizzazione
- Questa rappresentazione conettuale si chiama "**modello dei dati**"
- Programmi si riferiscono a concetti logici del modeeli dei dati, invece che alla memorizzazione dei dati

Separazione Dati - Programmi:
- Struttura file di dati -> memorizzata nel catalogo del DBMS, separatamente dei programmi di accesso
- Questa proprieta si chiama "**indipendenza tra programmi e dati**"
- In virtu dell'indipendenza tra dati - programmi e dell'astrazione dei dati è possibile modificare le strutture dati + l'orfanizzazione in memoria senza modificare i relativi programmi

### Supporto Viste Multiple sui Dati

- Approccio con BD fornisce supporto per gestione di viste multiple sui dati
- Una BD ha molti utenti, ognuno puo richiedere diversa prospettiva o vista
- Vista:
	- Sottoinsieme della BD
	- Insieme Dati Virtuali. i.e. non memorizzate esplicitamente nella BD ma piuttosto derivati dai dati della BD

### Condivisione Dati e Gestione Transazioni in Ambienti Multiutenti (I)

- DBMS multiutende DEVE consentire a piu utenti di accedere contemporaneamente alla BD
- Un DBMS deve contenere porzione di software per controllo della concorrenza

### Condivisione Dati e Gestione Transazioni in Ambienti Multiutenti (II)

Tranzsazioni:
	- Processo/programma in esecuzione che esegue uno o piu accessi alla BD
	- DBMS deve garantire delle proprieta fondamentali delle transazioni:
		- Isolamento: Ogni transazione sembra eseguita in isolamento rispetto ad altre, nonostante possano essere in esecuzione centinaia di trnsazioni conteporaneamente
		- Atomicita: Operazioni di una transazione vengono eseguite nella loro interezza (o non vengono eseguite affatto)

## Utenti BD

Due macrocategorie:
- Attori in scena: Progettano, usano o amministrano una BD
- Attori dietro le quinte: COllaborano al disegno, sviluppo e funzionamente dell'ambiente software + sistema del DBMS, non essendo interessate alla BD in se

### Attori in Scena

**Progettisti**:
- Responsabili per individuare dati da memorizzare nella BD + scegleire strutture adeguate per la rappresentazione e memorizzazione
- Interazione con utenti finali della BD per definirne i requisiti in base alle esigenze delgi utenti
**Amministratori (DBA)**:
- Autorizzazione accesso a BD
- Coordinazione + monitoraggio uso BD
- Rispondere a problemi tipo violazioni sistema/tempi di risposte scadenti
**Utenti Finali** attivita lavorativa richiede accesso alla BD, con diverse categorie:
1) Occasionali: Accedono occassionalmente a BD. Possono avre bisogno ogni volta di info diverse
2) Non Esperti: Interagiscono abitualmente con BD via metodi standard (canned transactions)
3) Esperti: Comprendono persone chge acquisiscono completa familiarita con funzionalita DBMS
4) Indipendenti: Mantengo BD per uso personale, usando pacchetti di programmi con interfaccie e menu di facile uso
**Analisti di Sistema + Programmatori**:
- Analisti: Determinano esigenze utenti finali. Sviluppano specifiche di transazioni standard in accordo con le esigenze
- Programmatori: Implementano le specifiche menzionate sopra. Testano e mantengono le transazioni standard

### Attori dietro le Quinte

Includono sviluppatori di moduli e pacchetti sw, perosnale amministrazione sistema, responsasbili manutenzione sw/hw. Non usano la BD per obbiettivi propri

## Vantaggi uso DBMS

1) Controllo Rindondanza:
	- **Problema**: RIdondanza dati (tipica sviluppo tradizionale BD mediante gestione files) genera rischi di incostistenza e puo essere utile a miglorare prestazioni delle interogazzioni
	- **Soluzione**: Rinondanza Controllata. Approccio con DBMS fa controllare eventulae intro. di ridondanza dei dati, fine: garantire consistenza
	- Verifiche Consistenza: 
		- Specificate al DBMS durante progettazione
		- Imposte automaticamente al DBMS dop aggiornamento
	
2) Divieto accesso non autorizzato
	- **Problema**: Piu utenti condividono una BD -> impedire l'acceso di alcune informazioni a certe classi di utenti
	- **Soluzione**: DBMS fornisce sottosistema per sicurezza e autorizzazione, utilizzato da DBA per definizione account/autorizzazioni
3) Memorizzazione Persistente Oggeti di Programma
	- BD utilizzate per fornire memorizzazione persistene di oggetti di programmi + strutture dati
	- **Problema**: 


Source: [[00 - Basi di Dati e Sistemi Informativi]]

---
Created: 