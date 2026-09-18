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

Chiamato anche "Probability integral" ha forma: $$I=\int_0^{+\infty}{e^{-t^2}dt}=\frac{\sqrt{\pi}}{2}$$ Dove: $$\int_0^{+\infty}{e^{-t^2}dt} = \lim_{x \to \infty} (R)\int_0^xe^{-t^2}dt$$ Ed equivalentemente: $$K=\int_{-\infty}^{+\infty}{e^{-t^2}dt}=\sqrt{\pi}$$ Si ha percio che $K=2I$, quindi da $I=\frac{\sqrt{\pi}}{2}$ si deduce che $K=2\frac{\sqrt{\pi}}{2}=\sqrt{\pi}$.

Osserviamo che $I$ e $K$ non possono essere calcolati con metodi dell'analisi *classica* come neanche l'integrale indefinito $\int{e^{-t^2}dt}$. Sappiamo pero che la funzione ammette primitive in tutto $\mathbb{R}$, ma appunto non le passiamo calcolare con i metodi che già conosciamo. Percio useremo gli **integrali doppi**

>[!INFO] Idea di procedimento
>- Esprimere $K$ come la radice quadrata di un opportuno integrale doppio $J$
>- Calcolare $J$, passando per le coordinate polari

Partendo da $K=\int_{-\infty}^{+\infty} e^{-t^2}dt$ definiamo l'integrale doppio $J$ e facciamo vedere che $J=K^2$. Poniamo per definizione: $$J=\iint_{\mathbb{R}^2}{e^{-(x^2+y^2)}dxdy}$$ Con le coordinate cartesiane si ha che: $\mathbb{R}^2=\{(x,y): -\infty < x +\infty, \hspace{10px} -\infty < y < +\infty \}$.

Separiamo $J$ in due integrali: $$J=\iint_{\mathbb{R}^2}{e^{-(x^2+y^2)}dxdy} \hspace{7px} = \hspace{7px} \int_{-\infty}^{+\infty}dx \int_{-\infty}^{+\infty}e^{-(x^2+y^2)}dy$$ 
Moltiplichiamo la parentesi per $-1$ e separiamo la potenza: $$\int_{-\infty}^{+\infty}dx \int_{-\infty}^{+\infty}e^{-x^2-y^2}dy \hspace{7px} = \hspace{7px} \int_{-\infty}^{+\infty}dx \int_{-\infty}^{+\infty}e^{-x^2}e^{-y^2}dy$$ 
Portiamo le variabili $x$ nell'integrale $dx$ e cambiamo le variabili $x$ e $y$ in $t$: $$\int_{-\infty}^{+\infty}e^{-x^2}dx \int_{-\infty}^{+\infty}e^{-y^2}dy \hspace{7px} = \hspace{7px} \int_{-\infty}^{+\infty}e^{-t^2}dt \int_{-\infty}^{+\infty}e^{-t^2}dt \Rightarrow$$
$$\Rightarrow (\int_{-\infty}^{+\infty}e^{-t^2}dt )^2=K^2 \hspace{15px} \text{Percio,}\hspace{5px} J=K^2$$

Ora dobbiamo calcolare il valore di $J$ con le coordinate polari. Vediamo che fare l'integrale su $\mathbb{R}^2$ è lo stesso che farlo su $\mathbb{R}^2\backslash \{(0,0) \}$. Dunque abbiamo: $$J=\iint_{\mathbb{R}^2\backslash \{(0,0) \}}e^{-(x^2+y^2)}dxdy$$
Notiamo adesso che se parametrizziamo $\mathbb{R}^2\backslash \{(0,0) \}$ con le coordinate polari, dove $x=\rho \hspace{5px} cos\theta$ e $y=\rho \hspace{5px} sin\theta$ si ha: $x^2+y^2=\rho^2$. Percio:$$\mathbb{R}^2\backslash \{(0,0) \}=\{(\rho,\theta)\in\mathbb{R}^2:0<\rho<+\infty, \hspace{5px} 0\le\theta\le2\pi\}$$Passando per le polari, moltiplicando per lo Jacobiano ed applicando la formula di riduzione abbiamo: $$J=\iint_{\mathbb{R}^2\backslash \{(0,0) \}}e^{-\rho^2}\rho \hspace{5px} d\rho d\theta=\int_0^{+\infty}dp\int_0^{2\pi}d\theta \hspace{5px}e^{-\rho^2}\rho$$Portiamo le variabili $\rho$ nell'integrale $d\rho$: $$\int_0^{+\infty}\rho e^{-\rho^2}d\rho \int_0^{2\pi}d\theta= J_1J_2$$Da questo abbiamo che $J_2=\int_0^{2\pi}1d\theta=[\theta]_0^{2\pi}=2\pi$. 

Per calcolare ora $J_1$ passiamo prima per il corrispondente integrale indefinito. 
Iniziamo con moltiplicare e dividere per $-2$: $$L_1\int \rho e^{-\rho^2}d\rho = -\frac{1}{2}\int(-2\rho)e^{-\rho^2}d\rho$$
A seguire troviamo la primitiva dell'integrale: $$-\frac{1}{2}\int D(e^{-\rho^2})d\rho=-\frac{1}{2}e^{-\rho^2}+c$$
Per calcolare or $J_1$ applichiamo la def. di integrale generalizzato e la Formula Fondamentale del Calcolo Integrale. Si ha: $$\lim_{x \to +\infty}\int_0^x\rho e^{-\rho^2}d\rho=\lim_{x \to +\infty}[-\frac{1}{2}e^{-\rho^2}]_0^x \Rightarrow$$ $$\Rightarrow\lim_{x \to +\infty}(-\frac{1}{2}e^{-x^2}+\frac{1}{2}e^0)=-\frac{1}{2}e^{-\infty}+\frac{1}{2} $$ $$=\frac{1}{2}$$Si ottiene quindi che $J=J_1J_2=\frac{1}{2}2\pi$, ovvero $J=\iint_{\mathbb{R}^2}e^{-(x^2+y^2)}dxdy=\pi$.    Ma $J=K^2$,   $K=\int_{-\infty}^{+\infty}e^{-t^2}dt$ e quindi $K=\sqrt{\pi}$. **INFINE**: $$I=\int_0^{+\infty}e^{-t^2}dt=\frac{K}{2}=\frac{\sqrt{\pi}}{2}$$  

---
# Funzione Gamma

Generalizzazione del fattoriale, si estende a numeri non interi, come se fosse, ad esempio, $(\frac{1}{2})!$. 
Definizione: $$\forall t>0, \hspace{10px} \Gamma(t)=\int_0^{+\infty}x^{t-1}e^{-x}dx$$ dove l'integrale è inteso in senso generalizzato, cioè: $$\Gamma(t)=\lim_{y \to +\infty}= \int_0^{y}x^{t-1}e^{-x}dx$$
Facciamo vedere che la funzione $\Gamma$ è una generalizzazione del fattoriale, usando le seguenti proprietà: 
1) $\Gamma(1) = 1 (=0!)$
2) $\Gamma(t+1)=t\hspace{5px}\Gamma(t), \hspace{10px} \forall t>0$

- Si ha: $$\Gamma(1)=\int_0^{+\infty}x^{1-1}e^{-x}dx=\int_0^{+\infty}x^0e^{-x}dx=\int_0^{+\infty}e^{-x}dx$$ 
  Ricordiamoci che: $\int{e^{-x}dx}=-e^{-x}+c$. Per la FFCI si ha: $$\Gamma(1)=\int_0^{+\infty}e^{-x}dx=\lim_{y \to +\infty} \int_0^y e^{-x}dx=\lim_{y \to +\infty}[-e^{-x}]_0^y \Rightarrow$$ $$\Rightarrow \lim_{y \to +\infty} (-e^{-y}-(-e^0))=\lim_{y \to +\infty}(-e^{-y}+1) \Rightarrow$$Per la somma dei limiti: $$\Rightarrow \lim_{y \to +\infty}(-e^{-y})+\lim_{y \to +\infty}1=-e^{-\infty}+1=0+1=1$$Percio 1) è stato **Provato**

- Si ha: $$\Gamma(t+1)=t\hspace{5px}\Gamma(t), \hspace{10px} \forall t>0$$ $\forall t>0$ si ha: $\Gamma(t+1)=\int_0^{+\infty}x^{t+\cancel{1}-\cancel{1}}e^{-x}dx$ visto che: $\Gamma(t)=\int_0^{+\infty}x^{t-1}e^{-x}dx$ (abbiamo sostituito $t+1$ al posto di $t$).
  
  Iniziamo col calcolare l'integrale **indefinito** $\int x^te^{-x}dx$. Integrale di prodotto, quindi usiamo la formula di integrazione per parti. Scriviamo: $$\int x^te^{-x}dx=\int x^t(-e^{-x})'dx=\int f(x)g'(x)dx$$Ed applichiamo la formula di integrazione per parti:$$\int f(x)g'(x)dx=f(x)g(x)-\int f'(x)\hspace{4px}g(x)\hspace{4px}dx$$ 
   Con $f(x)=x^t$, $f'(x)=tx^{t-1}$, $g(x)=-e^{-x}$, $g'(x)=e^{-x}$ abbiamo che: 
  
$$\left(\genfrac{}{}{0pt}{}{\triangle}{\triangledown}\right) \int x^te^{-x}dx=\int x^t(-e^{-x})'dx=-x^te^{-x}-\int tx^{t-1}(-e^{-x})dx=-x^te^{-x}+t\int x^{t-1}e^{-x}dx$$(L'ultimo addendo, "integrato" fra $0$ e $+\infty$, sara proprio $t\hspace{5px}\Gamma(t)$; t è una costante moltiplicativa (perché è una quantità fissata che non dipende da x), e quindi è stata portata fuori dall'integrale). Integrando ora $\left(\genfrac{}{}{0pt}{}{\triangle}{\triangledown}\right)$ da $0$ e $+\infty$ si ha: $$\Gamma(t+1)=\int_0^{+\infty}x^te^{-x}dx=[-x^te^{-x}]_0^{+\infty}+t\int_0^{+\infty}x^{t-1}e^{-x}dx=0+t\hspace{5px}\Gamma(t)= t\hspace{5px}\Gamma(t)$$ 
 
Questo, se si dimostra che $[-x^te^{-x}]_0^{+\infty}=0$. Si ha: $$[-x^te^{-x}]_0^{+\infty}=\lim_{y \to +\infty}[-x^te^{-x}]_0^y=\lim_{y \to +\infty}(-y^te^{-y}-0^te^0)-\lim_{y \to +\infty}(-y^te^{-y})=-(+\infty)^te^{-\infty}=(-\infty)0$$Sappiamo che $(-\infty)0$ è una forma indeterminata, **MA** l'esponenziale è più veloce, quindi "vince" $e^{-\infty}=0$. Percio abbiamo dimostrato che $[-x^te^{-x}]_0^{+\infty}=0$
  

---
# Serie

---