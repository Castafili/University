---
date: 12/10/26
tags:
  - UniPG
  - basi
---
## Algebra Relazionale


Fino a slide 21 da recuperare
### Concatenazione: Introduzione a join

Operatore derivato dall'algebra relazionale di join:
- Indicato col simbolo "" dove F inidca la condizione di join
- Unisce tuple logicamente collegate, provenienti da due relazione, in tuple singole
- Definito mediante operatori primitivi (non derivati) di selezione e prodotto cartesiano)

θ-Join
	Siano $R(X)$, $S(Y)$ due schemi iniziali di relazione t.c. $X \cap Y=\emptyset$ e siano r,s due istanze di $R(X)$, $S(Y)$. Sia F una formula proporzionale su condizioni atomiche di tipo $A\theta B$, dove $A \in X$, $B \in Y$ e θ un operatore di confronto.
	L'operatori di θ-join $r \bowtie_F) s$ produce una relazione formata da tutte le combinazioni di tuple che soddisfano la condizione di $F$: $$r\bowtie_F s = \sigma_F(r \times s)$$


### Equijoin

Un θ-join, dove la condizione di join F -> congiunzione  di condizioni atomiche di uguaglianze

### Join Naturale: Premesse

- Risultato operazione equijoin -> relazione dove ogni tupla assume gli stessi valore sugli attributi di equijoin
- Questi attributi appaiono ripetuti nel risultato
- L'operatore di join naturale permette l'eliminazione delle suddette duplicazioni di un equijoin
- Date due istanze di relazioni $r,s$ il join naturale produce una relazione le cui tuple sono ottenute concatenando le tuple di $r$ ed $s$ che hanno gli stessi valori sugli attributi comuni


Source: [[00 - Basi di Dati e Sistemi Informativi]]

---
Created: 