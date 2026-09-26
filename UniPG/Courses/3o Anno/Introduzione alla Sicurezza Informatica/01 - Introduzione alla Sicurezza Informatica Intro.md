---
date: 26/09/26
tags:
  - UniPG
  - cybersecurity
  - review
---

# Introduzione alla Sicurezza Informatica

> [!INFO] Informazioni sul Corso
> Sito web [qui](https://bista.sites.dmi.unipg.it/didattica/intro-sec/)
> Libro di riferimento: Network Security Essentials William Stallings
> Part I: Capitolo 2, 3, 4 no approfondimenti - 9
> Part III: Capitoli 10, 11, 12
> Esame: Orale

> [!INFO] Note Personali
> 5-9 Ottobre no lezione
> 5 Ottobre evento (Sara Notari): Evento gratuito su IA AIxIA 2026

---

## Autenticazione vs Identificazione

L'identificazione viene prima dell'autenticazione. Seguono poi autorizzazione e accounting (+Autorizzazione, Accounting).

> [!EXAMPLE] Esercizio (?)
> Verificare situazioni in cui si fa Autenticazione SENZA aver fatto prima un'identificazione

---

## Cos'è la Sicurezza?

Definizione: un sistema sicuro fa quello che deve fare e SOLO a chi lo deve fare.

La sicurezza è una proprietà a livelli, non è un concetto assoluto. Ad esempio, in casa il computer potrebbe essere sicuro ma all'esterno potrebbe NON esserlo. 
La sicurezza si basa sulla **costanza** perché un sistema può essere sicuro oggi e smettere di esserlo il giorno dopo.

### Definizione Formale di Sicurezza Informatica

- **Sicurezza:** Assenza di rischio e di pericolo
- **Sicurezza informatica:** Prevenzione o protezione contro accesso, distruzione o alterazione di risorse/informazioni da parte di utenti non autorizzati

La triade della **C.I.A.** definisce le proprietà principali:
- **Confidenzialità:** I dati possono essere accessi solo da chi autorizzato
- **Integrità:** I dati sono modificabili solo da chi autorizzato
- **Disponibilità (Availability):** La macchina è accessibile e utilizzabile

---

## Cosa NON è Sicurezza

La sicurezza non si limita a singoli strumenti:
- Crittografia
- Firewall
- Antivirus
- Password
- Smartcard
- ...

---

## Come Proteggersi

I livelli di protezione si suddividono in:
- **Physical Security:** Accesso fisico di utenti alle macchine
- **Operational/Procedural Security:** Policy di Sicurezza
- **Personnel Security:** Chi può fare cosa
- **System Security:** ACL, log, ecc.
- **Network Security** *(cosa tratteremo in questo corso)*: Firewall, IDS, buon routing e filtri

---

## Piano di Sicurezza

Un piano di sicurezza si struttura in diverse fasi:
- **Risk Avoidance (evitare rischi):** Necessitiamo di una connessione Internet permanente?
- **Deterrence (deterrenza):** Pubblicizzare strumenti di difesa e di punizione
- **Prevention (prevenzione):** Utilizzo di Firewall
- **Detection (rilevamento):** Utilizzo di sistemi IDS (**I**ntrusion **D**etection **S**ystem)
- **Reaction (reazione):** Recovery e procedure legali (Tribunale)

---

## Stato dell'Arte in Sicurezza

Punti chiave sulla sicurezza moderna:
1. Richiederebbe spesso un ridisegno, il che non è sempre possibile!
2. È una proprietà di vari livelli architetturali (OS, Rete, ...)
3. Non è un semplice predicato booleano
4. È costosa nel senso di risorse computazionali, gestione, mentalità, utilizzo
5. Rimane un campo aperto anche per i colossi informatici

---

## Computer Security vs Cybersecurity

- **Computer Security:** Protecting **information** stored in a computer system
- **Cybersecurity:** Protezione più ampia, concettualmente diversa dalla sola Computer Security (Cyber security != Computer Security)

> [!INFO] Why so much interest?
> IT systems are **pervasive** and connected:
> - IoT
> - Industry 4.0
> - Critical infrastructures
> - Government services
> - Financial Services

### Esempi di Pericoli

- Furto d'identità
- Disruption dei databases
- Breach di dati
- Attacchi Cyber-fisici
- Denial of Service (DoS)
- Furto dell'equipment
- Ransomware
- Spionaggio
- Cyberterrorismo

---

## Proprietà di Sicurezza

> [!INFO] Confidentiality
> Information should only be accessed (read) by authorized entities

> [!INFO] Integrity
> Information should only be modified (written) by authorized entities

> [!INFO] Availability
> Information and services should be available and usable

> [!INFO] Authenticity
> The possibility of correctly identifying an entity

> [!INFO] Accountability
> The possibility of tracing an event to a unique entity

---

Source: [[00 - Introduzione alla Sicurezza Informatica]]

---
Created: 26/09/2026