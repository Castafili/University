---
date: 12/10/26
tags:
  - UniPG
  - cybersecurity
---
# Cookies

Windows (Chrome): %LocalAppData%\Google\Chrome\User Data\Profilo\Network\
MacOS (Chrome): ~/Library/Application Support/Google/Chrome/Profilo/Network/
Linux (Chrome): ~/.config/google-chrome/Profilo/Network/

---

## Protocolli livello trasporto Internet

- TCP (Affidabile, consegne nell'ordine consegnato):
	1) Controllo congestione
	2) COntrollo flusso
	3) Setup Connessione

- UDP (Inaffidabile, consegne senz'ordine):
	1) Estensione sneza fronzoli del servizio di consegna a massimo sforzo

+++

#### Demultiplexing:

Host riceve datagrammi IP -> 

---

## Approcci controllo congestione

Due principali approcci:
1) Controllo congestione punto-punto:
	- 

2) Controlllo assisistito dalla rete


---

Ip address: ogni interfaccia di hpost e rtouter ha un ip globalmente univco
Interfaccia: confine tra host e collegamento fisico.
- Router necessariamente connessi ad 2+ collegamenit
- Host, in genere ha una UI
- A ogni UI sono associati degli ip


Sottoreti:
`Rete isolata i cui punti terminali -> collegati all'interfacccia di un host o di un router`

Frammentazione datagrammi IP (P-34)
Unita massima trasmissione = massima quantita di dati che un frame a livello di collegamento puo trasportare:
- Differenti tipi di link, differenti MTU

Datagrammi IP grandi -> frammentati in datagrammi IP piccoli:
- Datagramma frammentato
- Frammenti riassemblati solo una volta a destinazione
- Bit intestazione IP -> Usati per identificare + ordinare frammenti

---

CAP 5

MAcchine hanno indirizzo ip e indirizzo di rete

## Topologia a stella

da meta degli anni 90 ha preso il posto della topologia a bus
Quasi tutte le reti ethernete sono progettate con questa topologia

---

Firewall
Protegge dall'esterno, non dall'interno

Firewall non sono piu componentui rete, ma un insieme di compotentnti che cooperano tra di loro:
- Firewall e IDS
- Email/web contennt sxanners per virus e malicious code
- Personal firewalls
- ... a plicy
NON la prima linea di difesa, ma l'ultima


Callout: Definizione: 
	- Network Firewalls are devices or systems that control the flow of network traffic between networks emplyoing different security postures

Previene l'accesso alla rete privata ed evita che i paccheti dall interno vadano all'esterno con info proprietarie

Callout: Cosa fa?
	- Shcerma alcune reti interene e le nasconde a terzi
	- BLocca alcuni accessi a servizi o ad utenti
	- Moonitorare
		- Log function importante
	- Crea VPN
		- Crittazione auto dei dati tra i siti
		- fornisce confidenzialita dei dati inviati tra due gateways
		- Le 2 reti appaiono come rete singola, oltre il firewall
		- Buono per reti che si localizzano su piu siti


Cons:
- Approccio sbagliato alla sicurezza (non risolvono il problemea)
- Ma cmq un responsabile di una rete interna non si sentirebbe sicuro senza

Non difende contro nuovi bachi non ancora documentati, filtri difficile da settare e da mantenere, puo degradare la performance della rete

---

Due filosofio:
- Default deny: Tutto cio non espressaemente ammesso is proibito
- Default permit: tutto npn espresssamento proibito is ammesso

Principio:
Difesa perimentrale
1) Protegge tutti i cammini di ingresso alla rete privata (singola porta d'accesso)
2) All'interno della rete gli host si fidano tra loro 


Servizi add-on per i firewall:
- NAT
	- Static translation
	- Hiding translation
- DHCP
- Encryption functionality (VPNs)
- Application content filtering


Tipi di firewall:
- Packet-filtering routers
- 


#### Esercizio: trovare dei "timecell?"


Source: [[00 - Introduzione alla Sicurezza Informatica]]

---
Created: 