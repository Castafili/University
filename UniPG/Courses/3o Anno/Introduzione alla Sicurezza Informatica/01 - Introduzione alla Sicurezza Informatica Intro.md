---
date: ---
tags:
  - UniPG
  - cyber
---
Sito web [qui](https://bista.sites.dmi.unipg.it/didattica/intro-sec/)
	Libro di riferimento: Network Security Essentials William Stallings
	Part I: Capitolo 2, 3, 4 no approfondimenti - 9
	Part III Capitoli 10, 11, 12

## Esame

Orale

---
## Autenticazione vs Identificazione

(+Autorizzazione, Accounting)

Identificazione viene prima della autenticazione

Esercizio(?): Verificare situazioni in cui si fa Autenticazione SENZA aver fatto prima un'identificazione

---

## Sicurezza

Definizione: fa quello che deve fare e SOLO a chi lo deve fare

- Confidenzialita: I dati posso essere accessi solo da chi autorizzato
- Integrita: I dati sono modificabili solo da chi autorizzato
- Disponibilita (Availability): La macchina è accessibile
La triade della C.I.A.


## Cosa NON è sicurezza

- Crittografia
- Firewall
- Antivirus
- Password
- Smartcard
- ...


La sicurezza è una proprieta a livelli, non è un concetto assoluto, ad esempio in casa il computer potrebbe essere sicuro ma all'esterno potrebbe NON esserlo

---

La sicurezza si basa sulla **costanza** perche un sistema puo essere sicuro ogii e smettere di esserlo il giorno dopo

---

## Come proteggersi

- Physical Security
	- Accesso fisico di utenti alle macchine
- Operational
	- Policy di Sicurezza
- Personnel
	- Chi puo fare cosa
- System
	- Acl, log
- Network security (cosa tratteremmo)
	- Firewall, IDS, buon routing e filtri


## Piano di sicurezza

- Risk Avoidance
	- Necessitiamo di una connessione Internet permanente?
- Deterrence
	- Pubblicizzare strumenti di difesa e di punizione
- Prevention
	- Firewall
- Detection
	- IDS (**I**ntrusion **D**etection **S**ystem)
- Reaction
	- Recovery
	- Tribunale


---

## Stato dell'arte in Sicurezza

La sicurezza:
1) Richiederebbe spesso ridisegno, non sempre possibile
2) Proprieta a vari livelli (OS, Rete, ...)
3) Non è semplice predicato booleano
4) Costosa nel senso di risorse computazionali, gestione, mentalita, utilizzo
5) Rimano un campo aperto anche per i colossi informatici

---

## Definizione di Sicurezza Informatica

Sicurezza:
	Assenza di rischio e di pericolo
Sicurezza informatica:
	Prevenzione o protezione contro
		Accesso, distuzione o alterazione di risorse/informazioni da parte di utenti non autorizzati


Computer Security

- Protecting **information**
	- Stored in a computer system


Cyber security != Computer Security

Why so much interest?
IT systems are **pervasive** and connected
- IoT
- Industry 4.0
- Critical infrastructures
- Government sercives
- Financial Services

## Esempi di pericoli

- Furto d'identita
- Disruption dei databases
- BReach di dati
- Attachi Cyber-fisici
- Denial of Service
- Furto dell'equipment
- Rasnomware
- Spionaggio
- Cyberterrorismo


## Proprierta di Sicurezza

+++



> [!Definition] Confidentiality
> Information should only be
accessed (read) by authorized
entities

> [!Integriy] Information should only be
modified (written) by
authorized entities

> [!Availability] Information and services should
be available and usable

> [!Authenticity] The possibility of correctly
identifying an entity

> [!Definition] Accountability
> The possibility of tracing an
event to a unique entity

---
## Note

5-9 Ottobre no lezione
5 Ottobre evento (sara notari): Evento gratuito su IA
AIxIA 2026



Source: [[00 - Introduzione alla Sicurezza Informatica]]

---
Created: 