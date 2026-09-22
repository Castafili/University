---
date: 04/03/26
tags:
  - UniPG
  - sistemi
  - teoria
---
## Sistema di elaborazione

Unita Centrale:
	‎ 
	Microprocessore:
		- Processore su singolo chip
		- Multiproc. (più processori, core, su un chip, socket)
		- con cache
		‎ 
	Processore grafico (GPU):
		- Computa su array con "Single-Instruction Multiple-Data" (SIMD)
		- Non solo per applicazioni grafiche
		‎ 
	Processore segnale digitale (DSP):
		- Codifica/Decodifica segnali audio e video
		- Supporto crittografico
		‎
	SoC:
		- Sistema su chip: per smartphone e palmare


## Ciclo Fetch-Execute

Si inizia il processo, si preleva l'istruzione successiva, si esegue tale istruzione e: 
- O si ritorna alla fase di prelievo
- O finisce il processo


>[!INFO] Interruzioni
> Evitano di lasciare CPU attiva in attesa di I/O
> Si puo sospendere l'esecuzione di un programma


‎ 
## Classi:
Programma: Errori di esecuzione di programma (overflow ecc. d'indirizzo ecc.)
Timer: Permettono all' OS di eseguire funzioni ad intervalli regolari
I/O: Generate da controllore I/O per segnalare completamento o un errore di operazione
Errore HW: Problemi hardware

---

## ‎‎ 



Source: [[00 - Sistemi Operativi|Sistemi Operativi]]

---
Created: 