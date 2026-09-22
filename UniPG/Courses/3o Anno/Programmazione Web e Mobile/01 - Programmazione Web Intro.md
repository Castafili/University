---
date: 21/09/26
tags:
  - UniPG
  - web
  - review
---
# Introduzione al Corso e Architettura del Web

## Informazioni sul Corso ed Esame
- **Docente:** Carlo Taticchi (Email: carlo.taticchi@unipg.it, Sito: [carlotaticchi.it](https://www.carlotaticchi.it))
- **Ricevimento:** Su appuntamento
- **Modalità d'esame:**
  - **Progetto:** Singolo (no gruppi), da concordare con il docente; necessario per accedere all'orale (richiesti HTML, CSS, JS, Node.js; scontata la navbar; essere consci del codice inserito, no AI-slop).
  - **Prova orale:** Discussione del progetto e verifica delle conoscenze generali sugli argomenti del programma.

---

## World Wide Web e Standard Fondamentali
Il World Wide Web è un servizio di Internet che permette di navigare e usufruire di contenuti connettendo i nodi (computer/dispositivi) della rete tramite un **sistema ipertestuale** (testo con rimandi ad altri testi).

> [!INFO] Gli Standard del Web
> - **HTML:** Linguaggio di markup con cui sono scritte le pagine web.
> - **HTTP:** Protocollo di rete operante a livello applicazione della pila ISO/OSI.
> - **URL:** Schema di identificazione univoca dei contenuti e dei servizi sul Web.

### Evoluzione del Web
- **Web 1.0 (1990-2000):** Pagine statiche, contenuti fissi, siti creati da programmatori/aziende con semplice markup HTML; utenti con ruolo di sola lettura.
- **Web 2.0 (2000-2010):** Web dinamico e interattivo; pagine aggiornate in tempo reale (es. AJAX); contenuti generati dagli utenti e nascita dei social media (Wikipedia, YouTube, Facebook).
- **Web 3.0 (2010-presente):** Web semantico con dati strutturati e ontologie; uso di AI e Machine Learning per personalizzazione e assistenza; forte integrazione tra piattaforme.

---

## Architettura Client-Server e Browser
- **Client:** Condividono e richiedono risorse.
- **Server:** Gestisce e limita l'accesso a tali risorse.
- Modello alla base di LAN, Web e molti altri sistemi informatici.

> [!INFO] Il Browser Web
> Applicazione deputata all'acquisizione, presentazione e navigazione di risorse sul Web (pagine HTML). Implementa la funzionalità di **client** per il protocollo HTTP, regolando il download delle risorse dai server web a partire dal relativo URL.

### Componenti Fondamentali di una Pagina Web
È fondamentale **disaccoppiare** la struttura logica dalla sua rappresentazione:
1. **HTML:** Struttura e contenuti.
2. **CSS:** Rappresentazione visiva e layout.
3. **JavaScript:** Funzionalità e interazione dinamica.

---

## HTML (HyperText Markup Language)
- Sintassi stabilita dal **W3C** (World Wide Web Consortium).
- Definisce la struttura semantica delle pagine (HTML 5.3 rilasciato il 28 gennaio 2021).
- Struttura a blocchi principali: `<header>`, `<nav>`, `<main>`, `<article>`, `<video>`, `<footer>`.

**ref immagine struttura HTML pagina 8 [slides](https://www.carlotaticchi.it/courses/programmazione_web_e_mobile_con_laboratorio/lectures/pwm_lezione1.pdf)**

---

## Protocollo HTTP e Livello di Trasporto
L'**HyperText Transfer Protocol (HTTP)** regola la trasmissione delle informazioni su richiesta del client:
- **TCP (Transmission Control Protocol):** Connette due host assicurando che i pacchetti arrivino integri e nello stesso ordine di invio.
- **TLS (Transport Layer Security):** Cifra il canale per impedire intromissioni nella comunicazione (evitando attacchi Man-In-The-Middle). L'unione costituisce **HTTPS over TCP + TLS**.
- **Funzionalità:** Cache, CORS, Autenticazione, Proxy, Sessioni.

> [!INFO] Natura Stateless e Risoluzione
> HTTP è un protocollo **stateless** (non mantiene memoria o collegamento logico tra due richieste consecutive). Per ovviare a questo limite e gestire le sessioni si ricorre all'uso dei **cookie**.

### Versioni del Protocollo
- **HTTP/1.1:** Testuale; richiede connessioni parallele per scaricare le risorse (HTML, stili, script, immagini).
- **HTTP/2:** Messaggi incapsulati in frame binari multiplexati su una singola connessione TCP.
- **HTTP/3:** Basato sul protocollo di trasporto **QUIC** (su UDP) con cifratura TLS integrata.

---

## Anatomia delle Richieste e Risposte HTTP

### Richiesta HTTP
- **Metodo:** Definisce l'operazione da eseguire.
- **Path:** Posizione in rete della risorsa richiesta.
- **Header:** Metadati e parametri addizionali della richiesta.
- **Body (opzionale):** Risorsa o dati inviati al server.

**ref immagine Richiesta HTTP pagina 14 [slides](https://www.carlotaticchi.it/courses/programmazione_web_e_mobile_con_laboratorio/lectures/pwm_lezione1.pdf)**

> [!INFO] Sicurezza e Idempotenza dei Metodi HTTP
> Un metodo si dice **idempotente** se l'esecuzione ripetuta della medesima operazione non altera lo stato del sistema rispetto alla singola esecuzione.
> - **GET, HEAD, OPTIONS, TRACE:** Sicuri e Idempotenti.
> - **PUT, DELETE:** Non sicuri, ma **Idempotenti**.
> - **POST, PATCH, CONNECT:** **Non sicuri e Non idempotenti** (es. richieste di acquisto duplicate richiedono controlli preventivi sia lato client che lato server).

### Risposta HTTP
- **Status code e Status message:** Indicano l'esito della richiesta (es. `200 OK`) e la motivazione.
- **Header:** Informazioni sulla tipologia di dato (`content-type`), gestione cache (`cache-control`), ecc.
- **Body (opzionale):** Contenuto effettivo della risorsa restituita (es. file HTML, JSON).

---

## URL e Risoluzione DNS

> [!INFO] Uniform Resource Locator (URL)
> Identifica univocamente l'indirizzo di una risorsa in rete. Si compone di: **Protocollo**, **Sottodominio**, **Nome di Dominio**, **TLD (Top Level Domain)**, porta (opzionale, es. 80 per HTTP), **Path** e **Anchor**.

**ref immagine struttura URL pagina 18 [slides](https://www.carlotaticchi.it/courses/programmazione_web_e_mobile_con_laboratorio/lectures/pwm_lezione1.pdf)**

### Risoluzione da URL a IP (Workflow DNS)
Esempio: risoluzione da `https://www.dmi.unipg.it` a `141.250.197.175`:
1. Controllo della **cache locale**.
2. Se l'IP non è presente, interrogazione del **DNS pubblico** per il TLD (`.it`).
3. Il server TLD risponde indicando il **DNS autoritativo**.
4. Richiesta dell'IP associato al dominio al server DNS autoritativo.
5. Il server autoritativo restituisce l'indirizzo IP corrispondente al dominio (`unipg`), dominio secondario (`dmi`) e sottodominio (`www`).
6. Il browser utilizza l'IP ottenuto per stabilire la connessione con il server.

### Ciclo di Rendering del Browser
1. Inoltro della richiesta all'IP e ricezione dell'HTML (eventualmente generato lato server con PHP).
2. Analisi e costruzione dell'albero del **DOM (Document Object Model)**.
3. Download e applicazione dei fogli di stile **CSS** per layout e rendering.
4. Esecuzione di **JavaScript** per:
   - Manipolazione del DOM e aggiornamento dinamico della pagina.
   - Interazione asincrona con il server (es. AJAX).

---

## Esercizio per Giovedì
- Realizzare una pagina web minimale contenente i tag: `<h1>` e `<p>`.

---

Source: [[00 - Programmazione Web e Mobile]]

---
Created: