---
date: 18/03/26
tags:
  - UniPG
  - sistemi
  - teoria
---
## Elaborazione Concorrente

Nell'uniprocessore: le esecuzioni dei processi si alternano
Nel multiprocessore: si alternano e si sovrappongono

>[!WARNING] In entrambi i casi: La velocità di esecuzione non è prevedibile e dipende da:
> - Attività degli altri processi
> - Gestione delle interruzioni
> - Politiche di schedulazione

### Difficoltà

- condivisione di risorse globali
- Allocazione ottimale di risorse
- Debugging

### Conclusione
- Necessita di proteggere variabili condivise
- Controllare il codice che accede alla variabile

#### Race condition
Succede quando molteplici processi/threads leggono e scrivono dati in modo che il risultato dipenda dall'ordine di esecuzione delle istruzioni

## Problemi determinati dalla concorrenza

### Compiti dell' OS
- Tenere traccia dei processi
	- PCB
- Allocare e deallocare risorse per i processi attivi
	- Tempo di elaborazione
	- Memoria
	- Files
- Proteggere dati e risorse di ogni processo da interferenze involontarie di altri processi
- Risultato di ogni processo DEVE essere indipendente dalla sua velocità relativa a quella dei processi concorrenti

## Competizione per le risorse
I processi concorrenti sono in conflitto per l'uso delle risorse

>[!WARNING] Problemi
>- Mutua esclusione:
>	- Risorsa critica
>	- *Sezione critica*
>- Stallo (*deadlock*)
>- Starvation

## Cooperazione per condivisione

- Processi interagiscono senza conoscersi
- (Grazie all'uso ed alla modifica di dati condivisi)
- Devono cooperare per la corretta gestione di questi dati
- Meccanismo di controllo si assicura della loro integrità
- Si presentano i problemi di *mutua esclusione*, *stallo*, *starvation*
	- Le operazioni di lettura non richiedono mutua esclusione

## Cooperazione per scambio mess.

- Processi collaborano per obbiettivo comune
- Comm. permette sincronizzazione e coordinazione
- Non richiede *mutua esclusione*
- Può determinare *stallo* o *starvation*

## Requisiti Mutua Esclusione

- 1 solo processo alla volta ammesso nella sezione critica per ogni risorsa condivisa
- Processo fermo **fuori** dalla sua zona critica NON deve inferire con gli altri processi
- Si deve evitare *deadlock* e *starvation*
- Se nessun processo nella zona critica, DEVE essere concesso a ogni processo di entrare senza ritardo
- Nessuna ipotesi su velocità relativa dei processi ne sul numero dei processori
- Processo rimane nella sezione critica per un tempo finito

---

# Mutua Esclusione - 2

## Algoritmo di Dekker

> [!INFO] Obiettivo
> Protocollo che permette a due processi di assicurasi la mutua esclusione
> - Senza, necessariamente, support hardware
> - Senza stallo
> - Senza *starvation*

## Algoritmo di Peterson

```c
boolean flag [2];
int turn;

void P0()
{
	while (true) {
		flag [0] = true;
		turn = 1;
		while (flag [1] && turn == 1) // Do nothing;
		//Critical section;
		flag [0] = false;
		// Remainder
	}
}

void P1() { . . . }

```

Source: [[00 - Sistemi Operativi|Sistemi Operativi]]

---
Created: 