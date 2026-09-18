---
date: 30/03/26
tags:
  - UniPG
  - algoritmi
---
## Struttura dati per set disgiunti

- Conosciuti come "union find"
- Hanno una collezione $S = S \{ S_1,...,S_k \}$ di set dinamici (cambiano col temp) disgiunti
- Ogni set e identificato da un **rappresentativo**, che è un qualche membro del set
  Non importa quale membro sia il rappresentativo, se chiedi per per il rappresentativo senza modificare il set, otterrai la stessa risposta entrambe le volte

---
## Minimum Spanning Trees

### Problema:
- Un villaggio ha un set di case ed un set di strade
- Una strada collega solo 2 case
- Una strada che connette le case $u$ e $v$ ha un costo di riparazione $w(u,v)$
- **_Obbiettivo:_** Riparare abbastanza (non più) strade cosi che:
	1) Tutti rimangono connessi: possibilità di raggiungere ogni casa da tutte le altre case
	2) Il costo di riparazione e minimo

### Modello come un grafo:

- Indiretto grafo $G=(V,E)$
- **Peso** $w(u,v)$ so ogni margine $(u,v)\in E$
- Trovare $T \subseteq E$ cosi che:
	1) $T$ connette tutti i vertici ($T$ è uno **spanning tree**)
	2) $w(T)=\sum_{u,v}\in T w(u,v)$ è minimizzato

---

### Costruendo la soluzione

- Costruiamo un set $A$ di margini
- Inizialmente $A$ non ha margini
- Mentre margini sono aggiunti ad $A$ si mantiene un loop invariate
	- **Loop invariante:** $A$ è un sottoset di un qualche MST
- Aggiungono solo margini che mantengono l'invariante. Se $A$ è un sottoinsieme di un qualche MST, un margine $(u,v)$ è sicuro per $A$ se e solo se $A \cup \{ (u,v) \}$ è anche un subset di un qualche MST. Percio aggiungi solo margini sicuri


---

### Algoritmo MST Generico

MST-GENERICO($G,w$)
```
A = 0
while A does not form a spanning tree
	find an edge (u,v) that is safe for A
	A = A U {(u,v)}
return A
```


---

### Definizioni

- Un **taglio** ($S, V - S$) è partizione di vertici in set disgiunti $V$ e $S - V$
- Margine $(u,v) \in E$ **crosses** cut 




Source: [[00 - Algoritmi e Strutture dati]]

---
Created:  