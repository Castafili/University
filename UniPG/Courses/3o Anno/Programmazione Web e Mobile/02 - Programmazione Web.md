---
date: 24/09/26
tags:
  - UniPG
  - web
  - review
---
# HTML

Quando si parla di HTML si intende **HTML5**, sviluppato e mantenuto dal **W3C** (World Wide Web Consortium) e dal **WHATWG** (Web Hypertext Application Technology Working Group). Introduce nuovi tag semantici come `article`, `section`, `header`, `footer`, `nav`.

> [!INFO] Tag Semantici
> Elementi che descrivono chiaramente il loro significato sia al browser che allo sviluppatore. Google e i motori di ricerca analizzano questi tag: se nota che vengono utilizzati in modo scorretto può non indicizzare la pagina; l'uso corretto dei tag è fondamentale anche per consentire agli e-reader e screen reader di raggiungere molteplici utenti.

Offre inoltre supporto multimediale per video e audio senza ricorrere a plugin esterni ed è progettato per garantire piena compatibilità con dispositivi mobili e interfacce touch.

---

## Tag

### Tag Contenitori vs Tag Vuoti
- I tag **contenitori** hanno sia un tag di apertura che un tag di chiusura e racchiudono contenuti come testo, immagini o altri elementi HTML:

> [!EXAMPLE] Esempio
> - `<div>...</div>`
> - `<p>...</p>`
> - `<section>...</section>`

- I tag **vuoti** invece non racchiudono contenuti e non hanno un tag di chiusura:

> [!EXAMPLE] Esempio
> - `<img>`
> - `<input>`
> - `<hr>`

---

### Attributi dei Tag
I tag contengono "attributi", ovvero parole chiave che si trovano dentro i tag e forniscono dettagli aggiuntivi configurando e personalizzando il **comportamento** e l'**aspetto** degli elementi:

> [!EXAMPLE] Esempio attributi
> `<img src="fiore.jpg" alt="Girasole">`

> L'attributo `alt` può essere usato dagli e-reader per descrivere l'immagine all'utente.

Alcuni attributi modificano il **comportamento** (`src`, `alt`), mentre altri modificano puramente l'**aspetto** (`width`, `height`).

> [!ERROR] ERRORE
> VIETATO usare attributi che modificano SOLO l'aspetto, tutto quello che ha a che fare con lo stile va definito tramite CSS.  
> Chrome e i browser interpretano tag come `<strong>` rendendoli in grassetto per scelta stilistica/convenzione.

---

### Tag di Blocco vs Tag di Linea
Un'ulteriore divisione è quella in tag **di blocco** e tag **di linea**:

- I tag **di blocco** sono degli elementi che mandano a capo (occupano l'intera larghezza disponibile); all'interno possono anche contenere altri elementi, che siano di blocco o inline.

> [!EXAMPLE] Esempio
> - `<div>`
> - `<h1>` - `<h6>`
> - `<p>`

- I tag **di linea** non iniziano su una nuova riga e occupano solo lo spazio che necessitano per il loro contenuto.

> [!EXAMPLE] Esempio
> - `<span>`
> - `<a>`
> - `<img>`

---

## Struttura Base della Pagina

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

- `<!DOCTYPE html>`: Indica che il documento è scritto in HTML5.
- `<html lang="it">`: Radice e inizio del documento con specifica della lingua.
- `<head>`: Contiene metadati e informazioni invisibili all'utente finale.
  - `<title>`: Titolo mostrato nella scheda del browser.
  - `<meta charset="utf-8">`: Specifica la codifica dei caratteri.
- `<body>`: Contiene tutti gli elementi visibili della pagina.

---

## Liste

Utilizzate per organizzare e presentare informazioni in modo strutturato. Ne esistono di 3 tipologie:
- **Liste ordinate (`<ol>`):** ordered list.
- **Liste non ordinate (`<ul>`):** unordered list.
- **Elementi di lista (`<li>`):** list item, inseriti dentro le liste.
- **Liste di descrizione (`<dl>`):** con termini (`<dt>`) e descrizioni (`<dd>`) (non approfondite).

> [!INFO] Nesting
> Dentro alle liste esiste il concetto di **Nesting**, ovvero la possibilità di inserire (in questo caso) delle liste all'interno di altre liste per creare gerarchie.

---

## Citazioni

- Con il tag **`<q>`**, che è un tag di linea e viene utilizzato per delle citazioni brevi, aggiungendo automaticamente le virgolette.
- Con il tag **`<blockquote>`**, che è un tag di blocco e viene utilizzato per citazioni più lunghe o intere; solitamente rappresentato come rientro e può includere attribuzioni tramite l'attributo `cite`.

> [!ERROR] ERRORE
> `<br>` si usa SOLO se devo andare a capo nelle "poesie" (o comunque se DEVO andare a capo dopo una certa parola).  
> INVECE PER LASCIARE spazi si usa CSS.

---

# CSS

**CSS**, derivato da **C**ascading **S**tyle **S**heets (versione 3, uscita insieme a HTML 5), serve a migliorare la user experience, aiuta a ridurre lo sforzo necessario per la creazione di design complessi e facilita l'adattamento dei layout per diverse dimensioni di schermo.

## Scrittura di una Regola

Si usa un **Selettore** (l'equivalente di un tag in linguaggio HTML), con cui seleziono l'elemento del quale voglio cambiare lo stile.  
A seguito, dentro al selettore si usa un **Blocco di dichiarazione**, racchiuso tra parentesi graffe e contenente una o più dichiarazioni di stile, ognuna con una proprietà ed un valore. Ogni dichiarazione è separata da un punto e virgola:

```css
h1 {
	color: blue;
	font-size: 24px;
	text-align: center;
}
```

## Linking HTML - CSS

Per collegare un foglio di stile CSS ad una pagina HTML viene utilizzato il tag `<link>` all'interno della sezione `<head>`:

```html
<link rel="stylesheet" href="styles.css">
```

---

## Alcune Proprietà

### Color
Serve per modificare il colore di un testo, possono essere usati vari formati:
- **Parole chiave:** `red`, `green`, `blue`, ecc.
- **Valore esadecimale:** es. `#3636b5` (riconoscibile per il cancelletto).
- **Valore RGB:** es. `rgb(54, 54, 169)`.

### Font
Il font ha varie proprietà collegate:
- `font-family`: cambia la famiglia di un font (es. *sans-serif*, *serif* dove cambiano le "grazie", *monospace*).
- `font-style`: cambia lo stile di un font (`italic`, `normal`, `oblique`).
- `font-size`: cambia la grandezza del font (es. `font-size: 13px;`).
- `font-weight`: cambia il quanto "bold" è un font (es. `font-weight: 700;` per il grassetto).

#### Unità di Misura per il Font

| **Unità** | **px** | **em** | **%** |
| :---: | :---: | :---: | :---: |
| **Caratteristica** | Assoluta | Relativa | Relativa |
| **Base** | Dimensione fissa | Dimensione dell'elemento corrente | Dimensione del font dell'elemento genitore |
| **Comportamento** | Non scala | Scala in base alla dimensione del font corrente | Scala in base alla dimensione del font del genitore |
| **Eredità** | Non ereditabile | Può causare un aumento esponenziale quando usato in annidamenti | Mantiene un rapporto diretto con il genitore |
| **Usabilità** | Maggiore precisione, meno flessibilità | Maggiore flessibilità e scalabilità | Più intuitivo per dimensioni proporzionali |

### Ereditarietà in CSS
Abbiamo detto che CSS sta per **C**ascading **S**tyle **S**heets, quindi alcuni stili vengono trasmessi dagli elementi genitori ai loro figli. Questo vuol dire che un elemento senza stile erediterà (prenderà) lo stile dal suo elemento genitore.  
Cascading si riferisce anche al fatto che le regole sono applicate a "cascata": se scrivo in ordine che gli elementi `<p>` hanno colore red e poi blue, verrà applicata quest'ultima:

```css
p {
	color: red;
}

p {
	color: blue;
}
```

## Alcune Proprietà per il Testo
- `text-align`: Specifica l'allineamento orizzontale del testo in un elemento (`left`, `center`, `right`).
- `text-decoration`: Specifica la decorazione del testo (usato maggiormente con `none` per togliere la sottolineatura dai link).
- `text-transform`: Controlla la capitalizzazione del testo (`uppercase`, `lowercase`, `capitalize`).

---

## Background

Viene usato per gestire l'aspetto dello sfondo di un elemento, alcune sotto-proprietà sono:
- `background-color`: per definire il colore dello sfondo di un elemento.
- `background-image`: imposta invece un'immagine come sfondo tramite `url(...)` (usata per immagini che non sono relative all'uso e alla buona user experience).
- `background-repeat`: definisce se e come l'immagine di sfondo si ripete (`repeat`, `no-repeat`, `repeat-x`, `repeat-y`).
- `background-position`: definisce la posizione dell'immagine di sfondo.
- `background-size`: definisce la grandezza dell'immagine di sfondo:
  - `cover`: l'immagine copre tutto il contenitore.
  - `contain`: l'immagine viene ridimensionata per adattarsi all'interno del contenitore.
- `background-attachment`: definisce se l'immagine di sfondo si muove con la pagina o resta fissa (`fixed`).

> [!INFO] Differenza tra Tag `<img>` e `background-image`
> - **Tag `<img>` (HTML):** Parte del contenuto semantico, supporta il testo alternativo `alt`, accessibile e rilevante per i motori di ricerca (SEO).
> - **Proprietà `background-image` (CSS):** Ha scopo puramente decorativo, posizionata dietro al testo, non accessibile e non rilevante per la SEO.

---

Source: [[00 - Programmazione Web e Mobile]]

---
Created: