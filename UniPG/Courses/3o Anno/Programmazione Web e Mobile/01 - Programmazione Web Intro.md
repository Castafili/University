---
date: 21/09/26
tags:
  - UniPG
  - web
  - review
---
Ricevimento: su appuntamento

Pagina web: [carlotaticchi.it](https://www.carlotaticchi.it)

Esame: Progetto + orale (HTML, CSS, JS, Node.js)
	- Scontata una navbar
	- Essere consci di cosa ci mettiamo (**No AI-Slop**)

---

## World Wide Web

- Servizio Internet
- Permette la navigazione e usufruzione contenuti
- Connete nodi della rete
- Sistema **ipertestuale** -> testo con rimandi ad altri testi (hyper)

## Standard del Web

- HTML: markup-language, usato per scrivere le pagine web
- HTTP: Protocollo di rete, opera a livello applicazione della pila ISO/OSI
- URL: Schema identificazione contenuti e servizi su Web


## HTML

- **H**yper**T**ext**M**arkup**L**anguage
- Sintassi stabilita da World Wide Web Consortium **(W3C)**
- Definisce struttura pagine web
- HTML 5.3 - Rilasciato 28 gennaio 2021
**ref immagine struttura HTML pagina 8 [slides](https://www.carlotaticchi.it/courses/programmazione_web_e_mobile_con_laboratorio/lectures/pwm_lezione1.pdf)**

## Browser

- Applicazione per acquisizione, presentazione e navigazione di risorse sul Web (pagine HTML)
- Implementa funzionalita di **client** per protocollo HTTP, che regola download delle risorse dai server web, partendo dal loro indirizzo URL

`aggiungere due righe per le querry`

%%Espandere su database e architetture reti%%

## Architettura Client-Server

- Client condividono risorse
- Server gestisce + limita accessi alle risorse
- LAN, Web e molti sistemi informatici organizzati in formato client-server

## HTTP

- **H**yper**T**ext**T**ransfer**P**rotocol
- Richiesta parte da client (browser)
- **TCP** (**T**ransmission **C**ontrol **P**rotocol): connette due hosts, assicura l'arrivo dei pacchetti nell'ordine di invio
- **TLS** (**T**ransport **L**ayer **S**ecurity): Fa si che nessun'altro puo intomettersi nella comunicazione tra gli hosts (Per evitare attachi tipo Man In The Middle)
- Funzionalita:
	- Cache
	- CORS
	- Autenticazione
	  Proxy
	- Sessioni
- HTTP -> **Stateless** (no collegamento tra due richieste consecutive)
- Soluzione -> Cookies

## Richiesta HTTP

- Metodo: Definizione dell'operazione da eseguire
- Path: Posizione in rete della risorsa da recuperare
- Header: Informazioni extra, inoltrate durante la richiesta
- Body (opzionale): Risorsa da inviare
**ref immagine Richiesta HTTP pagina 14 [slides](https://www.carlotaticchi.it/courses/programmazione_web_e_mobile_con_laboratorio/lectures/pwm_lezione1.pdf)**

Idempotente: Applicato piu volte a se stesso -> non esegue modifiche
Metodo POST -> Non idempotente (ad esempio, per una pagina di acquisto, il tasto "compra" puo "comprare" tale cosa un numero di volte eccessivo) -> Necessita vincoli giusti, sia verso il cliente che verso il server.

## Risposta HTTP

- **Status code/message**: indica successo o fallimento richiesta + la ragione
- **Body** (opzionale): Risorsa richiesta
- Partendo da HTTP/2 messaggi in incapsulati in frames binari non intellegibili
- HTTP/3 funziona sul protocollo di rete QUIC, a sua volta usa UDP come prot. di trasporto

## URL

- **U**niform **R**esource **L**ocator
- Identifica indirizzo risorsa rete
- **Numero di porta** opzionale, alcuni protocolli hanno uno riservato (80 -> HTTPS)
- Risoluzione dell'URL in indirizzo **I**nternet **P**rotocol (IP) avviene tramite **D**omain **N**ame **S**ystem (DNS) (~Rubrica Internet)
**ref immagine struttura URL pagina 18 [slides](https://www.carlotaticchi.it/courses/programmazione_web_e_mobile_con_laboratorio/lectures/pwm_lezione1.pdf)**


## URL to IP

- Da “https://www.dmi.unipg.it” a “141.250.197.175”:
	1) Controllo cache locale
	2) Se IP NON in cache, contatta DNS pubblic per il TLD (.it)
	3) Server TLD risponde con indirizzo DNS autoritativo
	4) Al server DNS autoritativo richiesto IP associato al Dominio
	5) Server autoritativo restituisce IP assogiati a dominio (unipg), dominio secondario (dmi) e sottodominio (www)
	6) Browser utilizza IP per stabilizzazione connessione con server

### A seguito il browser

- Scarica, analizza HTML, eventualmente generato lato server tramite PHP, per la costruzione del **D**ocument **O**bject **M**odel (DOM)
- Scarica, applica CSS per formatting layout e stile
- Esegue JS per:
	- Manipolazione DOM + aggiornamento dinamico della pagina
	- Interagire con server (i.e. AJAX)

## Per giovedi
Scrivere una piccola pagina web con tag: h1, p


Source: [[00 - Programmazione Web e Mobile]]

---
Created: 