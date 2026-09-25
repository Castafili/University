---
date: 24/09/26
tags:
  - UniPG
  - web
  - review
---
# HTML

Quando si parla di HTML si parla di HTML 5, usa dei tag semantici come: article, section, header, footer, nav

> [!info] Tag Semantici
> *inserire breve definizione di tag semantici*

Ha supporto multimediale per video e/o audio senza l'uso di plugin esterni. Ed è progettato per la compatibilita con dispositivi mobile e touch

## Tag

Esistono due tipi di tag, tag contenitori e tag vuoti:
- I tag **contenitori** hanno un tag di apertura ed un tag di chiusurea, racchiudono contenuti come testo, immagini o altri elementi HTML:

>[!Example] Esempio
> - &ltdiv&gt...&lt/div&gt
> - &ltp&gt...&lt/p&gt
> - &ltsection&gt...&lt/section&gt

--- 

- I tag **vuoti** invece non racchiudono contenuti e non hanno un tag di chiusura:

>[!Example] Esempio
> - &ltimg&gt
> - &ltinput&gt
> - &lthr&gt

Google cerca questi tag e se vede che sono usati nella maniera sbagliata non indicizza la pagina, l'use dei tag è anche importante per l'uso di e-readers per raggiungere multeplici utenti


I tag contengono "attributi" ovvero parole chiavi che si trovano dentro i tag come ad esempio:

>[!Example] Esempio attributi
> &ltimg src="fiore.jpg" alt="Girasole"&gt

> alt puo essere usato dagli e-reader per descrivere l'immagine all'utente

---

Un'ulteriore divisione è la divisione in tag **di linea** e tag **di blocco**

- Tag **di blocco** sono degli elementi che mandano a capo, all'interno possono anche contenere altri elementi, che siano di blocco o inline

>[!Example] Esempio
> - &ltdiv&gt
> - &lth1&gt - &lth6&gt
> - &ltp&gt

- Tag **di linea** non iniziano su una nuova riga e occupano solo lo spazio che necessitano

>[!Example] Esempio
> - &ltspan&gt
> - &lta&gt
> - &ltimg&gt

---
## Struttura Pagina

```html
<!DOCTYPE html>
<html lang="it">
<head>
	<title>Il mio sito web</title>
	<meta charset="utf-8">
</head>
<body>
	<!-- Qui dentro il codice che deve apparire -->
</body>
</html>
```


- !DOCTYPE html:  
- 

---

## Attributi

Contengono infomrmazioni aggiuntive che forniscono dettagli su un elemento HTML, configurano e personalizzano il **comportamento** e **l'aspetto** degli elementi

Alcuni attributi modificano il **comportamento** (src, alt) del tag, mentre altri modificano puramente **l'aspetto** (width, height)

>[!Error] ERRORE
>VIETATO usare attributi che modificano SOLO l'aspetto, tutto quello che ha a che fare con lo stile va definito tramite CSS


Chrome/browser interpretano il tag strong rendendolo in grassetto (scelta stilistica)

---

## Liste

Esistono due tipi, le liste **ordinate** (ol = ordered list) e le liste **non ordinate** (ul = unordered list) e al loro interno posso inserire degli elementi (li = list item). 

Dentro alle liste esiste il concetto di **Nesting**, ovvero la possibilta di inserire (in questo caso) delle liste, all'interno di altre liste.

Esiste anche un tipo di lista **di descrizione** che non verra trattato.


## Citazioni

Con il tag \<q>, è un tag di linea e viene utilizzato per delle citazioni brevi, aggiungendo automaticamente le virgolette  

invece con il tag **\<blockquote>**, che è un tag di blocco e viene utilizzato per citazioni piu lunghe o intere, rappresentato solitamente come rientro e puo includere attribuzioni tramite l'attributo cite.


>[!Error] ERRORE
> &ltbr&gt si usa SOLO se devo andare a capo nelle "poesie" (o comunque se DEVO andare a capo dopo una certa parola)
> INVECE PER LASCIARE spazi si usa css

---

# CSS

**CSS**, derivato da **C**ascading **S**tyle **S**heets (versione 3, uscita insieme a HTML 5), serve a migliorare la user experience, aiuta a ridurre lo sforzo necessario per la creazione di design complessi e facilita l'adattamento dei layout per diverse dimensioni di schermo.

## Scrittura di una regola

Si usa un **Selettore**(l'equivalente di un **tag** in linguaggio HTML), e **seleziono** l'elemento del quale voglio cambiare lo stile. 
A seguito, dentro al selettore si usa un **Blocco di dichiarazione**, racchiuso tra parentesi graffe e contenenti uno o piu dichiarazioni di stile, ognuna con un aproprieta ed un valore. Ogni dichiarazione è separata da un punto e virgola.

```css
h1 {
	color: blue;
	font-size: 24px;
	text-align: center;
}
```

## Linking HTML - CSS

Per collegare un foglio di stile CSS ad una pagina HTML viene utilizzato il tag \<link> all'interno della sezione \<head>

```html
<link rel="stylesheet" href="styles.css">
```

---

## Alcune proprieta

### Color

Serve per modificare il colore di un testo, possono essere usati vari formati, ad esempio si possono usare le **parole chiave** (red, green, blue,...). Si puo anche usare il valore **esadecimale** (#3636b5, riconoscibile per il cancelletto), un'altro formato è l'uso del valore **RGB** rgb(54, 54, 169).

### Font

Il font ha varie proprieta collegate, **font-family** cambia la famiglia di un font (es. sans-serif, serif (cambiano le "grazie")). **font-style** cambia lo stile di un font (italic, normal, oblique). **font-size** cambia la grandezza del font (font-size: 13px;). **font-weight** cambia il quanto "bold" è un font (font-size: 700; -> **Testo**)

#### Unita di misura per il font

|   **Unità**    |                 **px**                 |                             **em**                              |                        **%**                        |
| :------------: | :------------------------------------: | :-------------------------------------------------------------: | :-------------------------------------------------: |
| Caratteristica |                Assoluta                |                            Relativa                             |                      Relativa                       |
|      Base      |            Dimensione fissa            |                Dimensione dell'elemento corrente                |     Dimensione del font dell'elemento genitore      |
| Comportamento  |               Non scala                |         Scala in base alla dimensione del font corrente         | Scala in base alla dimensione del font del genitore |
|    Eredità     |            Non ereditabile             | Può causare un aumento esponenziale quando usato in annidamenti |    Mantiene un rapporto diretto con il genitore     |
|   Usabilità    | Maggiore precisione, meno flessibilità |               Maggiore flessibilità e scalabilità               |     Più intuitivo per dimensioni proporzionali      |

### Ereditarieta in CSS

Abbiamo detto che CSS sta per **C**ascading **S**tyle **S**heets, quindi alcuni sitli vengo trasmessi dagli elementi genitori ai loro figli. Questo vuol dire che, un elemento senza stile, ereditera (prendera) lo stile dal suo elemento genitore.
Cascading si riferisce che le regoloe sono applicate a "cascata", se scrivo in ordine che gli elementi \<p> hanno colore red e poi blu, verra applicata quest'ultima:

```css
p {
	color: red;
}

p{
	color: blue;
}
```

## Alcune proprieta per il testo

- **text-align**: Specifica l'alineamento orizonatle del testo in un elemento
- **text-decoration**: Specifica decorazione del testo (usato maggiormente per togliere la sottolinea dai link)
- **text-transform**: controlla la capitalizzazione del testo

## Background

Viene usato per gestire l'aspetto dello sfondo di un elemento, alcune sotto proprieta sono:

- **background-color**: per definire il colore dello sfondo di un elemento
- **background-image** (usata per immagini che non sono relative all'uso ed alla buona user experience): imposta invece un'immagine come sfondo
- **background-repeat**: definisce se e come l'immagine di sfondo si ripete
- **background-position**: definisce la posizione dell'immagine di sfondo
- **background-size**: definisce la grandezza dell'immagine di sfondo
	- cover: l'immagine copre tutto il contenitore
	- contain: l'immagine viene ridimensionata per adattarsi all'interno del contenitore
- background-attachment: definisce se l'immagine di sfondo si muove o resta fissa


Source: [[00 - Programmazione Web e Mobile]]

---
Created: 