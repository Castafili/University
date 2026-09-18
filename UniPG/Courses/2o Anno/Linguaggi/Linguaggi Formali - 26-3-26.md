---
date: 26/03/26
tags:
  - UniPG
  - compilatori
---
# Costruzione automa di Nerode


### Problema della minimizzazione

Dato un automa a stati finiti deterministico $A=\langle Q, \Sigma, \delta, q_0, F \rangle$, costruire un automa deterministico equivalente ad $A$ col minimo numero di stati.
- Possiamo ridurci al caso in cui tutti gli stati siano accessibili
- gli stati dell'automa di Nerode sono le classi di$N_L...$ 
- ma anche unione di insiemi $L_q$ con $q \in Q$ (cf. dimostrazione del Teorema di Nerode, (ii) $\Rightarrow (iii) )$;
- Dunque, la partizione di $\Sigma$* nelle clssi di $N_L$ induce una partizione di $Q$
- Tale partizione gode delle seguenti 3 proprietà:
	1) Insieme $F$ è unione di classi
	2) Se $p$ e $q$ sono della stessa classe, allora $\forall$ lettera $a \in \Sigma, \delta(p,a)$ e $\delta(q,a)$ cadono in una stessa classe
	3) è la meno din tra le partizione che soddisfano le precedenti condizioni.
- il problema della minimizzazione si ridurrà pertanto alla ricerca della partizione di $Q$ che soddisfa tali condizioni

---

### Algoritmo di minimizzazione

La partizione di $Q$ che soddisfa la condizioni 1-3 si ottiene per le seguenti approssimazioni: costruiamo la sequenza di partizioni $\Pi_n$ di $Q$ definite cosi:
- La partizione $\Pi_0$ ha le sole due classi $F$ e $Q$ \ $F$
- $\forall \hspace{3px} n \hspace{3px} \geq \hspace{3px}0$ le classi di $\Pi_{n+1}$ si ottengono spezzando quelle di $\Pi_n$ in modo da "separare" le coppie di stati che non soddisfano la 2a condizione
- Smettiamo non appena $\Pi_{n+1}=\Pi_n$

 L'automa minimo di $L$ si ottiene cosi:
 - Gli stati sono le classi della partizione $\Pi$
 - $\forall$ classe $C$ e ogni lettera $a \in \Sigma, \delta'(C,a)$ è la classe che contiene tutti gli stati $\delta(q,a)$ con $q\in C$ 
 - Lo stato iniziale è la classe $C_o$ che contiene lo stato iniziale $q_0$ di $A$
 - Gli stati finali sono le classi in $F$

---

```Raffinamento
Function Raffina (Π)


Πₙᵤₒᵥₒ <- ( )
for S ∈ Π
	for q ∈ S
		for a ∈ Σ
			C_{qa} <- classe di δ(q,a)
		$L$ <- {C_q|q ∈ S}
		for $l ∈ L$
			appendi {q|C_q = $l$} a Πₙᵤₒᵥₒ
Π <- Πₙᵤₒᵥₒ
```

---

# Lemma di Iterazione

Lemma: sia L un linguaggio regolare:
Esiste un intero $n$ talee che ogni parola $w \in L$ di lunghezza $|w| \hspace{3px} \geq \hspace{3px} n$ si può fattorizzare $w = xyz$ con $y \neq \epsilon$ $$xy^mz \in L \hspace{10px} \forall \hspace{3px} m \geq 0$$ In altre parole, se $L$
 è un linguaggio regolare, in ogni parola di $L$ *abbastanza lunga* si può trovare un fattore **non vuoto** che può essere iterato (pumped) senza uscire dal linguaggio.
Percio:
	Se un linguaggio non ha questa proprietà non può essere regolare... ma ci sono linguaggio che hanno questa proprietà e non sono regolari.

---

>[!proof] Dimostrazione
>- Per il teorema di Kleene, $L$ è accetato da un automa a stati finiti $A$
>- Sia n il numero di stati
>- Sia $w \in L$ e $|w| \geq n$ Scriviamo $w=a_1a_2...a_k$, con $a_1,a_2,...,a_k \in A, \hspace{3px} k \geq n$
>- nel grafo di $A$ c'è un cammino 

![[Pasted image 20260326111203.png]]
 

Source: [[00 - Linguaggi Formali e Compilatori]]

---
Created: 