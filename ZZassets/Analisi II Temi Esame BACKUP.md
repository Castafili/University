---
date:
tags:
  - UniPG
---
# Massimi e Minimi (E sella)

Questi punti vengono trovati nei **punti critici** ovvero dove il **gradiente** è zero.

Come riconoscere se un punto è massimo, minimo o sella,

1) Si ha la funzione $f(x,y)$, dobbiamo calcolare le derivate parziali $f_x(x,y)$ e $f_y(x,y)$ e si risolve il sistema: $$\begin{cases} f_x=0 \\ f_y=0 \end{cases}$$ Le soluzioni sono i **punti critici**. Esempio: $$f(x,y)=x^2+y^2 \Rightarrow f_x=2x \hspace{5px}| \hspace{5px} f_y=2y $$ Sistema: $$\begin{cases} 2x=0 \\ 2y=0 \end{cases}$$ Percio il punto critico è: $(0,0)$

2) Si calcolano le derivate seconde $f_{xx}, \hspace{10px} f_{yy}, \hspace{10px} f_{xy}$ e si costruisce la **matrice Hessiana**: $$H=\begin{bmatrix}  
f_{xx} & f_{xy} \\  
f_{xy} & f_{yy} 
\end{bmatrix}$$
3) Calcolo del determinante: $$D=f_{xx}f_{yy}-(f_{xy})^2$$
4) regola per i punti:
   - Caso 1: $D>0$ e $f_{xx}>0$ danno **Minimo Locale**
   - Caso 2: $D>0$ e $f_{xx}<0$ danno **Massimo Locale**
   - Caso 3: $D<0$ da un **Punto Sella**
   - Caso 4: $D=0$ è un **Test non Conclusivo** (non ha risultato)

5) Esempio: $$f(x,y)=x^2-y^2$$Derivate prime: $f_x=2x$ e $f_y=-2y$. Punto critico: $(0,0).$ Passiamo ora alle derivate seconde: $$\begin{array}{rcr} f_{xx} & = & 2 \\ f_{yy} & = & -2 \\ f_{xy} & = & 0 \end{array}$$ Determinante: $$D=(2)(-2)-0=-4, \hspace{15px} D<0$$ Quindi è un **Punto Sella**


---
# Integrali Doppi

- Si calcola il volume invece che l'area

### Esempio esercizio con coordinate *cartesiane*:

$$I=\iint_C{(x+2y)\hspace{2.5px}dx\hspace{2.5px}dy}$$
dove $C$ è il triangolo con vertici: $0=(0,0),A=(1,0),B=(0,1)$

1) Si disegna l'insieme $C$ ed in seguito, all'equazione della retta, si sostituiscono i valori $x$ ed $y$. Sostituendo per passaggio su punto $A(x=1,y=0)$ si ha: $y=mx+q \Rightarrow 0=m1+q\hspace{3px}=\hspace{3px}m+q.$ Sostituendo per passaggio su punto $B(x=0,y=1)$ si ha: $y=mx+q \Rightarrow 1=m0+q\hspace{3px}\Rightarrow\hspace{3px}q=1$ Da qui, e da $m+q=0$ si ottiene $m=-1$. Quindi, equazione retta: $$y=-x+1 \hspace{15px} \text{opp.} \hspace{15px} y=1-x \hspace{15px} \text{opp.} \hspace{15px} x=1-y \hspace{15px} \text{opp.} \hspace{15px} x+y=1$$
2) Stabiliamo ora che $C$ è un dominio normale. Si ha: $$C=\{(x,y)\in\mathbb{R}^2:0\le x\le 1, \hspace{10px} 0\le y\le 1-x\}$$ N.B: $y$ varia tra (i segmenti del)le rette $y=0$ e $y=1-x$ NON tra $0$ ed $1$

3) Integriamo prima rispetto ad $y$, poi rispetto ad $x$: $$I=\int_0^1dx \int_0^{1-x}(x+2y)dy$$ Calcoliamo per primo l'integrala **Interno**. N.B: Integriamo rispetto ad $y$ quindi $x$ è **costante**: $$\int{xdx}= xy$$ e $$\int{2ydy}=y^2$$ Mettendoli assieme otteniamo l'integrale indefinito: $$\int{(x+2y)dy}=xy+y^2$$
4) Valutiamo ora tra $0$ e $(1-x)$: $$[xy+y^2]^{1-x}_0 \hspace{10px} = \hspace{10px} (x(1-x)+(1-x)^2)-(x0+0^2)$$ Seconda parte è 0 quindi si ha: $x(1-x)+(1-x)^2$

5) Semplificazione: $x(1-x)=x-x^2$  e $(1-x)^2=1-2x+x^2$. Sommiamo: $$(x-x^2)+(1-2x+x^2)=1-x$$
6) Integrale esterno: $$\int{1dx} - \int{xdx}=x-\frac{x^2}{2}$$ Valutiamo tra 0 ed 1: $$(1-\frac{1}{2})-0=\frac{1}{2} \hspace{5px} \Longrightarrow \hspace{5px} I=\frac{1}{2}$$

### Esempio esercizio con coordinate *polari*:

$$I_1=\iint_C{\frac{xy}{x^2+y^2}dxdy}$$
dove $C= \{(x,y),\in \mathbb{R}^2:1\le x^2+y^2\le 4,\hspace{10px} x \ge 0, \hspace{7px} y \ge 0 \}$

1) Disegnare l'insieme $C$ **IMPORTANTE PER LE POLARI**: ![[Pasted image 20260310094429.png]]

2) Trasformando $C$ in $C'$ mediante le coordinate polari, si ha: $$C'= \{(\rho,\theta),\in \mathbb{R}^2: 1\le \rho \le 2,\hspace{10px} 0 \le \theta\le \frac{\pi}{2} \}$$Quindi c'è un dominio NORMALE sia rispetto a $\rho$ sia a $\theta$

3) Calcoliamo l'integrale doppio, passando alle polari e moltiplicando per il Jacobiano:$$I_1=\iint_C{\frac{xy}{x^2+y^2}dxdy}=\iint_{C'}{\frac{(\cancel{\rho}cos{\theta})(\cancel{\rho}sin{\theta})}{\cancel{\rho^2}}\rho d\rho d\theta}$$ $$\Rightarrow \int_1^2\rho d\rho \int_0^{\frac{\pi}{2}}cos\theta \hspace{5px} sin\theta \hspace{5px} d\theta=[\frac{\rho^2}{2}]_1^2 \hspace{5px} * \hspace{5px} \int_0^{\frac{\pi}{2}}sin\theta \hspace{3px} D(sin\theta)d\theta \Longrightarrow$$
Sostituiamo $sin\theta = w$. Poiché $\theta$ varia da $0$ a $\frac{\pi}{2}$ allora $sin\theta$ va da $0$ a $1$. In aggiunta si ha $dw=\frac{dw}{d\theta}=D(sin\theta)d\theta=cos\theta \hspace{3px}d\theta$. $$\Longrightarrow (\frac{4}{2}-\frac{1}{2})\int_0^1w \hspace{3px}dw = \frac{3}{2} \hspace{3px} [\frac{w^2}{2}]_0^1= \frac{3}{2}\frac{1}{2}=\frac{3}{4}$$

---

# Integrale di Probabilità

Chiamato anche "Probability integral" ha forma: 





---
# Funzione Gamma

Generalizzazione del fattoriale, si estende a numeri non interi, come se fosse, ad esempio, $(\frac{1}{2})!$

---
# Serie

---