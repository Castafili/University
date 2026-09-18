---
date: 08/04/26
tags:
  - UniPG
---
ORG N (origin)
- $N \in [0,2^{12}-1]$ in *esadecimale* specifica da quale cella di memori si deve iniziar a caricare il programma.

END
- Indica la fine del programma (**Non esecuzione**)

DEC N (decimal)
- Il numero decimale N espresso in modulo e segno

HEX N (hexadecimal)
- Il numero esadecimale N

---

```pdp8
ORG 100 /programma vuoto
END
```
Lascia invariato lo stato dell memoria dato che non c'è nessuna istruzione o dato da caricare

```pdp8
ORG 100 /programma piu corto
HLT
END
```
Esegue un unica istruzione che termina l'esecuzione

---

ADD
	Esegue somma tra accumulatore AC e:
	- 











Source: [[Architettura degli elaboratori]]

---
Created: 