# Grammatiche

1. Descrivere i linguaggi generati dalle grammatiche con le seguenti produzioni:
    1. $S \rightarrow aaSbb, \quad S \rightarrow aabb$.
    2. $S \rightarrow abS, \quad S \rightarrow \varepsilon$.
    3. $S \rightarrow aXb, \quad X \rightarrow aX, \quad X \rightarrow bX, \quad X \rightarrow \varepsilon$.
2. Costruire delle grammatiche che generino i seguenti linguaggi:
    1. $L = \{a^nb^{2n} \mid n > 0\}$
    2. L'insieme delle parole sull'alfabeto $\{a,b\}$ che contengono lo stesso numero di $a$ e di $b$
    3. L'insieme delle parole sull'alfabeto $\{a,b,c\}$ che contengono lo stesso numero di $a$ e di $b$
    4. (difficile) $L = \{uu \mid u \in \Sigma^*\}$, ove $\Sigma = \{a,b\}$

---

# Automi a stati finiti

1. Si dia una descrizione delle parole accettate dai seguenti automi a stati finiti
    1. ![[Pasted image 20260713145755.png|218]]
    2. ![[Pasted image 20260713145810.png]]
2. Costruire degli automi a stati finiti che riconoscano i seguenti linguaggi
    1. L'insieme delle parole sull'alfabeto $\Sigma = \{a,b\}$ la cui seconda lettera è $a$.
    2. L'insieme delle parole sull'alfabeto $\Sigma = \{a,b\}$ che non contengono due $a$ consecutive.

---

# Automi a stati finiti non deterministici

1. Si costruiscano degli automi non deterministici che riconoscano i seguenti linguaggi:
    1. L'insieme delle parole sull'alfabeto $\{a,b\}$ che terminano con $aba$.
    2. L'insieme delle parole sull'alfabeto $\{a,b\}$ in cui la prima lettera è diversa dall'ultima.
    3. L'insieme delle parole sull'alfabeto $\{a,b\}$ in cui la prima lettera è uguale all'ultima.
2. Si costruiscano automi deterministici equivalenti agli automi seguenti:
    1. ![[Pasted image 20260713145838.png]]
    2. ![[Pasted image 20260713145855.png]]

---

# Espressioni regolari

1. Si trovino delle espressioni regolari per i linguaggi descritti di seguito:
    1. L'insieme delle parole sull'alfabeto $\{a,b\}$ che terminano con $aba$.
    2. L'insieme delle parole sull'alfabeto $\{a,b\}$ che non contengono due $a$ consecutive.
    3. L'insieme delle parole sull'alfabeto $\{a,b\}$ che contengono esattamente tre $a$.
    4. L'insieme delle parole sull'alfabeto $\{a,b\}$ in cui il fattore $ab$ compare una volta sola.
2. Si costruiscano automi a stati finiti (non deterministici con $\varepsilon$-transizioni) che accettano i linguaggi denotati dalle seguenti espressioni regolari:
    1. $a(a+b)^*$
    2. $a^*(a+b)a^*$
    3. $(a+\varepsilon)(bb+\varepsilon)abb$.
    4. Le espressioni regolari prodotte nel precedente esercizio.
    
    Si costruiscano poi degli automi deterministici equivalenti.
3. Si determinino delle espressioni regolari per i linguaggi accettati dagli automi seguenti:
    1. ![[Pasted image 20260713145916.png]]
    2. ![[Pasted image 20260713145928.png]]

---

# Automa minimo

Si determinino gli automi a stati finiti deterministici col minimo numero di stati equivalenti agli automi seguenti:
    1. ![[Pasted image 20260713145950.png]]
    2. ![[Pasted image 20260713150000.png]]
    3. ![[Pasted image 20260713150014.png]]

---

# Grammatiche regolari

1. Si determinino delle grammatiche di tipo 3 che generano i linguaggi accettati dagli automi seguenti:
    1. ![[Pasted image 20260713150025.png]]
    2. ![[Pasted image 20260713150035.png]]
    3. ![[Pasted image 20260713150047.png]]
2. Si determinino degli automi a stati finiti che accettano i linguaggi generati dalle grammatiche con le produzioni seguenti. Si forniscano inoltre delle espressioni regolari per tali linguaggi.
    1. $S \rightarrow aX, \quad S \rightarrow a, \quad X \rightarrow aX, \quad X \rightarrow bX, \quad X \rightarrow b$.
    2. $S \rightarrow aA, \quad A \rightarrow bB, \quad B \rightarrow aX, \quad X \rightarrow aX, \quad X \rightarrow bX, \quad X \rightarrow a$.
    3. $S \rightarrow \varepsilon, \quad S \rightarrow ab, \quad S \rightarrow baX, \quad X \rightarrow \varepsilon, \quad X \rightarrow baX$.

---

# Grammatiche non contestuali

Sia $\Sigma$ l'alfabeto $\Sigma = \{a,b\}$. Si determinino delle grammatiche non contestuali che generano i seguenti linguaggi:

1. $\{a^n b^m a^m b^n \mid m,n \geq 0\}$
2. $\{w \in \Sigma^* \mid |w|_a = 2|w|_b\}$ (difficile)
3. L'insieme delle parole antipalindrome sull'alfabeto $\Sigma$.
   (N.b.: una parola si dice antipalindroma se la parola rovesciata risulta uguale a quella ottenuta scambiando le $a$ con le $b$. Per esempio, sono antipalindrome $abbaab$, $bbabababaa$, $ab$)

---

# Semplificazioni

1. Si considerino le grammatiche con le produzioni seguenti.
    * Si determinino le variabili annullabili e si costruiscano grammatiche prive di $\varepsilon$-produzioni equivalenti a quelle assegnate.
    * Si determinino le derivazioni unarie nelle grammatiche ottenute e si costruiscano grammatiche prive di produzioni unarie equivalenti a quelle precedentemente ottenute.
    * Si determinino poi le variabili produttive e quelle accessibili.
    * Infine si costruiscano grammatiche prive di variabili improduttive e inaccessibili, equivalenti a quelle ottenute in precedenza.
        1. $S \rightarrow aXb, \quad X \rightarrow YZ \mid bSa \mid \varepsilon, \quad Y \rightarrow a \mid \varepsilon, \quad Z \rightarrow YZ$
        2. $S \rightarrow XY \mid XA, \quad Y \rightarrow X \mid \varepsilon, \quad X \rightarrow aSb \mid Y, \quad A \rightarrow bB, \quad B \rightarrow ba$.
        3. $S \rightarrow Xa \mid aBa, \quad X \rightarrow YY \mid Xb, \quad Y \rightarrow a \mid \varepsilon, \quad Z \rightarrow Ac \mid b, \quad A \rightarrow a, \quad B \rightarrow bCb$.
2. Si determinino delle grammatiche in forma normale di Chomsky equivalenti a quelle dell'esercizio precedente.

---

# Algoritmo di Cocke-Kasami-Younger

1. Si considerino le grammatiche con le produzioni seguenti. Per ciascuna delle parole indicate si calcoli la matrice di riconoscimento e si dica se la parola appartiene al linguaggio generato dalla grammatica.
    1. $S \rightarrow AB \mid AY \mid XB \mid XY, \quad X \rightarrow AS, \quad Y \rightarrow BS, \quad A \rightarrow a, \quad B \rightarrow b$.
       Parole: $aabb$, $aaab$, $abaabb$, $abbaab$.
    2. $S \rightarrow XA \mid YB \mid a \mid b, \quad X \rightarrow AS, \quad Y \rightarrow BS, \quad A \rightarrow a, \quad B \rightarrow b$.
       Parole: $abba$, $abbba$, $bbaabb$, $bbabb$
    3. $S \rightarrow XY, \quad X \rightarrow AB \mid CB, \quad Y \rightarrow BA \mid DA, \quad C \rightarrow AX, \quad D \rightarrow BY, \quad A \rightarrow a, \quad B \rightarrow b$.
       Parole: $abba$, $aaba$, $abbbaa$, $baaba$
2. Si considerino le grammatiche e le parole dell'esercizio precedente. Per ciascuna parola appartenente al linguaggio generato dalla corrispondente grammatica, si tracci un albero di derivazione.

---

# Automi a pila

1. Per ciascuno dei seguenti linguaggi, si determini la tabella delle transizioni di un automa a pila che accetta tale linguaggio per pila vuota.
    1. $\{a^n b^{2n} \mid n \ge 0\}$,
    2. $\{a^n b^n \mid n \ge 0\} \cup \{b^n a^n \mid n \ge 0\}$,
    3. L'insieme delle parole sull'alfabeto $\{a,b\}$ che contengono lo stesso numero di $a$ e $b$.
2. Per i medesimi linguaggi, si determinino le tabelle delle transizioni di automi a pila che li accettano per stato finale.



---
