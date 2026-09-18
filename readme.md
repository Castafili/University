# 🎓 University Notes & Projects — UniPG

Raccolta completa di appunti, sintesi teoriche, schemi, esercitazioni di laboratorio e progetti didattici per il corso di laurea triennale in **Informatica** presso l'**Università degli Studi di Perugia (UniPG)**.

## 📂 Architettura della Repository

La cartella principale coincide con la radice del vault Obsidian, strutturato per anno accademico e singoli insegnamenti:

```text
University/
├── Courses/
│   ├── 1° Anno/
│   ├── 2° Anno/
│   └── 3° Anno/
│       ├── Architettura Reti e Internet/
│       ├── Basi di Dati e Sistemi Informativi con Laboratorio/
│       ├── Introduzione all'Intelligenza Artificiale/
│       ├── Introduzione alla Sicurezza Informatica/
│       ├── Programmazione Web e Mobile con Lab/
│       ├── Human-Computer Interaction/
│       ├── Sistemi di Realtà Virtuale/
│       └── Tecniche di Acquisizione Dati 1/
├── .obsidian/               # Configurazione del vault, snippet e plugin
└── README.md
```

## 🛠️ Toolchain & Convenzioni

* **Editor Principale:** [Obsidian](https://obsidian.md/)
  * Formattazione tramite Markdown standard con sintassi LaTeX per la notazione matematica ($\LaTeX$).
  * Collegamenti bidirezionali (`[[wikilinks]]`) per creare grafi di connessione concettuale tra materie trasversali.
* **Diagrammi & Grafi:**
  * Schemi veloci a mano durante la spiegazione frontale in aula.
  * Rielaborazione vettoriale a casa mediante **Excalidraw** o blocchi **Mermaid** integrati.
* **Controllo Versione:** Git e GitHub per backup, cronologia delle modifiche e sincronizzazione tra dispositivi.

## ⚙️ Configurazione Git & Sincronizzazione

Il file `.gitignore` nella radice esclude automaticamente cache e file di stato temporaneo locali generati da Obsidian:

```gitignore
.obsidian/workspace.json
.obsidian/workspace-mobile.json
.obsidian/graph.json
.obsidian/backups/
.obsidian/cache/
.obsidian/indexeddb/
Thumbs.db
desktop.ini
.DS_Store
```