---
date: 13/03/26
tags:
  - UniPG
  - compilatori
---
## Espressioni Regolari

Operazioni sui linguaggi:
1. Unione, intersezione, complemento
2. Concatenazione $L_1L_2=\{uv \hspace{5px}|\hspace{5px} u \in L_1, v \in L_2 \}$
3. Potenza: $L^n = L\hspace{3px}L...L, (n volte)$
4. Chiusura di Kleene: $L^{*}\bigcup_{n\ge0}L^n=\{u_1u_2 ...u_n|n \ge 0, u_1,...,u_n \in L \}$

>[!INFO] Osservazione
>Unione, concatenazione e chiusura di Kleene sono dette **Operazioni Regolari**


Definizione: 
Sia $\hat \Sigma$ l'alfabeto ottenuto aggiungendo a $\Sigma$ le lettere $\cancel0, +, *, (, ).$ Si dicono **espressioni regolari** sull'alfabeto $\Sigma$ le parole sull'alfabeto $\hat\Sigma$ che si ottengono applicando un numero finito di volte le seguenti regole:
1) Ogni lettera $a \in\Sigma$ è un'espressione regolare, $\cancel0$ è un espressione regolare.
2) Se $E$ e $F$ sono espressioni regolari, allora $(E+F)$, $(EF)$ e $E^*$ sono espressioni regolari.

A ogni espressione regolare è associato un linguaggio, detto **linguaggio denotato dall'espressione regolare** e definito dalle seguenti regole:
1) $\forall a \in \Sigma$, l'espressione regolar $a$ denota il linguaggio $\{a\}$; l'espressione regolare $\cancel0$ denota il linguaggio vuoto
2) Detti $L_E$ e $L_F$ i linguaggi denotati dalle espressioni regolari $E$ ed $F$, i linguaggi denotati dalle espressioni regolari $(E+F)$, $(EF)$, $E^*$ sono, rispettivamente, $L_E \cup L_F$, $L_EL_F$, $L_E^*$.

## Linguaggi Regolari

>[!INFO] Definizione
>I linguaggi denotati da espressioni regolari si dicono linguaggi regolari

Osservazione:
	La classe dei linguaggi regolari è la più piccola famiglia di linguaggi che:
	- contiene i linguaggi finiti,
	- è chiusa per le operazioni regolari.

Osservazione:
	Possiamo omettere qualche parentesi rispettando la priorità:
	1) Chiusura di Kleene,
	2) Concatenazione,
	3) Somma
	   Esempio: 
		$bab+ab^*$ equivale a $(((ba)b)+(ab^*)).$





Source: [[00 - Linguaggi Formali e Compilatori]]

---
Created: 