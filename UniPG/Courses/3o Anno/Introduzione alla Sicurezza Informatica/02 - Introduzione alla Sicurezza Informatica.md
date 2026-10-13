---
date: 28/09/26
tags:
  - UniPG
  - cybersecurity
---
# Ripasso Reti

Standard di riferimento: TCP

Comunicazione client-server: Su reti **distinte**, TCP crea un canale virtuale da client a server che agisce da "tubo di connessione".

UTP da espandere

## Applicazioni

Pacchetto a livello di app: messaggio
A livello di trasporto: segmento
A livello fisica: datagramma
A livello 2 link/ethernet: frame

## Socket

Il come viene gestito il tunnel del tcp, per aprire un tunnel di comunicazione il linguaggio inizializza una primitiva di socket, che permette di accedere e parlare con l'applicazione dall'altra parte, necessita di definizioni (n. porta che usiamo, n. porta dall'altra parte, IP nostro, IP dall'altra parte) 

Porte standardizzate: 80 (server web), 25 (server mail)

Porta mittente scelta randomicamente

## HTTP

Protocollo per connettersi a server web. Un client, tramite browser, si connette al server con protocollo http.
HTTP -> due tipi di messaggi: richiesta, risposta
Messaggio di richiesta:
	ASCII

Elencare verioni HTTP

## Slides dei cookie ++

Trovare dove vengono memorizzati i cookie, ci sono cookies non cifrati?


Controllo di parita: Mando messaggio -> faccio "una somma byte per byte", devo vedere se la somma è pari o dispare. Dispari: controllo parita +1. Pari -> Contorllo parita +0

## SMTP

Simple Mail Trasport Protocol, protocollo per seguire la posta. 


Cosa vuol dire, encoding base-64?



Source: [[00 - Introduzione alla Sicurezza Informatica]]

---
Created: 
