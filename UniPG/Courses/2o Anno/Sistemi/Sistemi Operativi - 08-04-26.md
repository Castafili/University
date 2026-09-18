---
date: 08/04/26
tags:
  - UniPG
---
## Condizioni per lo stallo

Necessarie:
1) Mutua esclusione
2) Possesso e attesa
3) Assenza di prerilascio

Condizione determinante:
4) Attesa circolare: 
	   Esiste una catena chiusa di processi tale che ogni processo possiede una risorsa richiesta dal processo successivo (ciclo grafo di Holt)

Azioni contro lo stallo
-  Prevenzione
- Esclusione
- Rilevamento

---

## Metodi indiretti

>[!warning] ** Mutua esclusione:**
>Impossibile disabilitarla per risorse seriali. (solo in rari casi e.g., file in lettura)

#### **Possesso e attesa:** 
Possibilità di imporre ai processi un'unica richiesta globale di tutte le risorse, sospendendolo fino a che non l ha ottenute tutte simultaneamente. 
Inefficiente per:
- Processi sospesi in attesa delle risorse
- Risorse assegnate e non utilizzate

#### **Assenza di prerilascio**
Si impone ai processi in attesa di una risorsa di rilasciare quelle che possiede. 
Il sistema prerilascia il processo che utilizza la risorsa richiesta e gli impone di rilasciare la risorsa utilizzata (*Priorità*)
- Realizzabili solo se lo stato della risorsa può essere salvato e ripristinato

---

## Metodi diretti

#### **Assegnazione ordinata**
Si definisce un ordine totale sulle categorie di risorse.
Un processo cui siano già state assegnate delle risorse può richiedere solo risorse di categorie successive a quelle delle risorse assegnate.

## Rifiuto di esecuzione

Inizia un nuovo processo $$P_{n+1} \Longleftrightarrow \forall j, \hspace{5px} R_j \geq C_{n+1,j} + \sum_{i=1}^{n}{C_{ij}}$$Cioe ci sono risorse sufficienti per soddisfare tutti i processi
- Insufficiente:
	  Assume che tutte le richieste di tutti i processi debbano essere soddisfatti simultaneamente

---
## Algoritmo del banchiere

#### Stato del sistema:
I vettori **R** e **V** e le matrici **C** e **A**

#### Stato sicuro:
Se esiste almeno una sequenza di allocazione che porta a termine tutti i processi

#### Strategia per evitare lo stallo:
Una richiesta è rifiutata se porta in uno stallo insicuro



Source: [[00 - Sistemi Operativi]]

---
Created: 