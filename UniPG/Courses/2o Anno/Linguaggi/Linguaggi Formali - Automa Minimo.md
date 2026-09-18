---
date: 20/03/26
tags:
  - UniPG
  - compilatori
  - review
---
>[!INFO] Equivalenza:
>**Equivalenza** è una relazione riflessiva, simmetrica e transitiva

>[!WARNING] Osservazione:
>Ogni equivalenza su un sistema *S* determina una partizione dell'insieme *S* in **classi di equivalenza**.
>Viceversa, ogni partizione dell'insieme *S* è assoaciata a un'equivalenza di cui le parti sono classi di equivalneza

---

>[!info] Congruenza: 
>Sia $\Sigma$ un alfabeto. Una relazione di equivalenza ~ su $\Sigma\text{*}$ si dica una **congruenza destra** (risp. **sinistra**) se $\forall u, v \in \Sigma\text{*}$ tali che $u ~ v$ e $\forall$ lettera $a \in \Sigma$, si ha $ua ~ va$ (risp. $au ~ ua$).
Una relazione che sia contemporaneamente di congruenza destra e una congruenza sinistra dice **congruenza**.

# Equivalenza di Nerode

>[!info] Definizione
>Sia $L$ un linguaggio sull'alfabeto $\Sigma$. L'equivalenza di Nerode associaa al linguaggio $L$ è una relazione $N_L$ definita in $\Sigma\text{*}$ da:
>$$u\hspace{3px}N_L \hspace{3px}v \hspace{5px}\text{se}\hspace{5px} \forall \hspace{5px} y \in \Sigma\text{*}, \hspace{5px} uy \in L \Longleftrightarrow uy \in L$$
>CIoe, $u \hspace{3px} N_L \hspace{3px} v$ hanno gli stessi completamenti a destra in $L$

>[!tip] Lemma
>Sia $L \subseteq \Sigma\text{*}$ un linguaggio:
>1) La relazione $N_L$ è una congruenza destra.
>2) $L$ è unione di classi di equivalenza di $N_L$



Source: [[00 - Linguaggi Formali e Compilatori]]

---
Created: 