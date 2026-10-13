---
date: 01/10/26
tags:
  - UniPG
  - web
  - review
---
## Video

Il tag video necessita il tag src (come img) e il tag type nel quale si specifica il tipo di file (.mp4), aggiungiendo una riga di testo apparira un testo in caso il video non funzioni.

Attributi:
- **controls** -> mostra controlli
- **autoplay** -> avvia automaticamente
- **loop** -> riproduce il video in loop
- **muted** -> disattiva l'audio

---

## Audio

Funziona similarmente al video, con un source ed un type. Ed hanno gli stessi attributi


## Ancore

tag \<a\> crea collegamenti ipertestuali tra pagine web, od anche sezioni della stessa pagina. 
Attributi principali:
- **href**: l'URL o ID dell'elemento al quale si collega
- **target**: dove aprire al link (\_blank lo apre in una nuova pagina)

---

## Div e Span

Div: un elemento di blocco usanto per raggruppare contenuti

span: elemento inline usato per l'assegnazione di stile a porzioni di testo da id o da classe


## Layout Multi-Colonna

- column-count: numero di colonne
- column-width: larghezza minima delle colonne
- column-gap: spazio tra colonne
- column-rule: stile del bordo tra colonne

## Float

+++

---

## Position

Dice al browser come è la posizione degli elementi, alcune proprieta correlate sono: **top, left, bottom, left**. Mentre i valori che puo prnedere sono:
- **static** (default)
- **relative**: sposta l'elemento rispetto alla sua posizione originale
- **absolute**: posizione l'elemento rispetto al suo primo antenato e rimuove l'elemento dal flusso normale
- **fixed**: posiziona l'elemento rispetto alla finestra del browser (fisso durante lo scorrimento della pagina)
- **sticky**: elemento trattato come relative fino a che non supera una certa soglia di scorrimento, quindi diventa fixed

## Display

#### Inline:
Questi elementi sono disposti uno accanto all'altro sulla stessa righa e non interrompono il flusso del layout come quelli di blocco. Seguono la larghezza del loro contenuto

#### Blocco:
Occupano l'intera larghezza disponibile e iniziano su una nuova righa ed accettano proprietà come width, height, margin e padding.

>![Warning] Importante
>Entrambe le modalita possono essere cambiate (un elemento prevalentemente di blocco (come una div) puo diventare di linea e viceversa)

#### Flex
Crea contenitori fleesibili per la gestione semplicie del posizionamento e l'allineamento dei figli. Li allinea lungo una direzione, verticale od orizzontale

#### Grid:
Crea un layout a griglia per l'organizzazione degli elementi in righe e colonne, le proprieta correlate sono:



Source: [[00 - Programmazione Web e Mobile]]

---
Created: 