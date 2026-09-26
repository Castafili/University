---
date: 25/09/26
tags:
  - UniPG
  - reti
  - mod2
  - review
---
## Esame
L'esame scritto è in comune per entrambi i moduli.
L'esame scritto è svolto tramite la piattaforma LibreEOL per verificare le conoscenze teoriche.
Ogni test sarà costituito da domande a risposta multipla del tipo Multiple Choice e Multiple Response.
I test sono individuali, di uguale difficoltà tra i candidati, con domande e risposte presentate in ordine casuale.

---

## Risorse Per la Ricerca
- [IEEE Search Engine](https://ieeexplore.ieee.org/Xplorehelp/searching-ieee-xplore/search-engine)
- [ACM Search Engine](https://dl.acm.com)
- [Springer Link Home](https://link.springer.com)
- [Google Scholar](https://scholar.google.com)
- (VPN universitaria Fortinet per scaricare pdf aggratis)

---

## Introduzione Networking
Il settore delle **Reti di Calcolatori** e dei sistemi telematici è in estrema crescita. Questo sviluppo è legato a molteplici aspetti:
- Sviluppo delle telecomunicazioni
- Sviluppo delle micro-nano tecnologie
- Sviluppo di sensori più efficienti
- Sviluppo di soluzioni software
- Sviluppo di soluzioni combinate hardware/software
- Necessità di trasferimento di dati, voce e video assieme ed in tempo reale

Si è passati da sistemi centralizzati a sistemi di elaborazione distribuita, con tecnologie che permettono la spedizione di quantità di dati sempre maggiori con segnali sempre più veloci.

> [!INFO] Teoria dell'Informazione
> L'informazione è l'insieme di dati, correlati tra loro, con cui un'idea (o un fatto) prende forma ed è comunicata.
> Il processo comunicativo, secondo il modello Shannon-Weaver, si basa su 7 elementi fondamentali e si inquadra nella Piramide DIKW (Dati, Informazione, Conoscenza, Saggezza).

---

## Comunicazione Dati
Calcolatori di ogni tipo possono oggi comunicare e interagire a livello planetario (scambiare informazioni sia in modo locale, che remoto).
Un processo comunicativo è definito dalla coesistenza di:
- Una **sorgente** di informazione
- Un **mezzo** che permette l'invio dell'informazione (cammino fisico)
- Un **destinatario** (dispositivo ricevente)

> [!INFO] Definizione: Comunicazione Dati
> Scambio di informazione fra 2 o più dispositivi grazie ad un mezzo trasmissivo.

Per avere comunicazione abbiamo bisogno che gli stessi siano parte di un sistema di comunicazione, composto da hardware e software.

---

## Protocollo di Comunicazione
Il **Protocollo** è una componente fondamentale del sistema di comunicazione.
È un insieme di regole che consentono la comunicazione; definisce un **cosa** si sta scambiando e un **come** viene scambiato.

> [!WARNING] Attenzione
> Senza un protocollo, 2 o più dispositivi possono essere connessi senza riuscire a comunicare.

### Standardizzazione
Gli standard internazionali dei protocolli sono definiti e mantenuti da varie organizzazioni:
- **ISO**
- **IEEE SA** (Standards Association)
- **IETF**
- **ITU** (ex CCITT)
- **W3C** (World Wide Web)
- **ICANN**

---

## Modelli di Riferimento: ISO/OSI e TCP/IP

> [!INFO] Architettura a Livelli
> I protocolli di rete inoltrano le PDU (Protocol Data Unit) incapsulate del Transport Layer tra gli host.
> L'architettura è suddivisa in **Media Layers** (livelli inferiori) e **Host Layers** (livelli superiori).

| Data Unit | ISO/OSI Layer | TCP/IP Layer |
| :--- | :--- | :--- |
| **Data** | 7. Application | 4. Application Layer |
| **Data** | 6. Presentation | 4. Application Layer |
| **Data** | 5. Session | 4. Application Layer |
| **Segments** | 4. Transport | 3. Transport Layer |
| **Packets** | 3. Network | 2. Internet Layer |
| **Frames** | 2. Data Link | 1. Network Access Layer |
| **Bits** | 1. Physical | 1. Network Access Layer |

---

Source: [[00 - Architettura Reti e Internet]]

---
Created: