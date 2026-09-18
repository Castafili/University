---
date: 20/04/26
tags:
  - UniPG
---
## Idee generali:

La bozza iniziale della domanda di ricerca era: **Esiste una correlazione tra strategia di pit stop e risultato finale?**" ma, vedendo Monaco come caso particolare (sorpassi minimi con posizioni della qualifica *quasi* invariate) sono passato alla domanda:
"**L’impatto della strategia di pit stop sul risultato varia in funzione delle caratteristiche del circuito?**" 

(la quale poi un giorno, si spera, diventi la mia tesi/ **“Dai big data alla strategia di gara: l’uso dell’intelligenza artificiale in Formula 1.”**)

### Addizioni/Modifiche da considerare:

Invece di usare la posizione finale come variabile principale si pensa di analizzare invece il **position delta** (ovvero il quantitativo di posizioni perse/guadagnate | Pilota inizia in P8, finisce in P4, Delta = +4). Questa prenderebbe la forma di -> **"Come incidono numero e timing dei pit stop sulle posizioni guadagnate o perse in gara?"**

---

>[!INFO] N.B. 
>Visto che la stagione del 2026, e di conseguenza i dati a riguardo, non sono ancora completi + l'incertezza di tali dati essendoci appena stato un cambio di regolamento. L'intenzione è di analizzare i dati della stagione 2025.

Essendo Monaco un caso particolare verrà trattato come "outlier". (Ovvero un caso con comportamento differente che può avere un impatto di maggiore importanza sull'analisi)

In aggiunta, verranno analizzati altri 3 GP per delle specifiche ragioni:
- Silverstone: Pista da benchmark, generale e bilanciato tra velocità e drag
- Monza: Pista ad alta velocità con poca downforce
- Bahrain: Caso più "estremo". Tyre degration alta, pit strategy ancora più importante

---
### Piloti

Per evitare eventuali bias, ma principalmente per avere un'analisi più completa, ho deciso di prendere i dati di tutti e 20 i piloti. A seguire una tabella per ogni GP, tutte con i vari dati


#### Bahrain

>[!INFO] Per il GP del Bahrain Jack Doohan sostituì Franco Colapinto

| Driver | Start Type | Start Pos |  Finish Pos  | Delta |  Status  | Stops |     Lap First Pit      |
| :----: | :--------: | :-------: | :----------: | :---: | :------: | :---: | :--------------------: |
|  PIA   |    Grid    |     1     |      1       |   0   | Finished |   2   |           14           |
|  LEC   |    Grid    |     2     |      4       |  -2   | Finished |   2   |           17           |
|  RUS   |    Grid    |  3 (PEN)  |      2       |  +1   | Finished |   2   |           13           |
|  GAS   |    Grid    |     4     |      7       |  -3   | Finished |   2   |           10           |
|  ANT   |    Grid    |  5 (PEN)  |      11      |  -6   | Finished |   3   |           12           |
|  NOR   |    Grid    |     6     |      3       |  +3   | Finished |   2   | 10 (5s penalty served) |
|  VER   |    Grid    |     7     |      6       |  +1   | Finished |   2   |           10           |
|  SAI   |    Grid    |     8     |   RITIRATO   |  NA   |   DNF    |   3   |    14 (44 to check)    |
|  HAM   |    Grid    |     9     |      5       |  +4   | Finished |   2   |           17           |
|  TSU   |    Grid    |    10     |      9       |  +1   | Finished |   2   |           11           |
|  DOO   |    Grid    |    11     |      14      |  -3   | Finished |   2   |           9            |
|  HAD   |    Grid    |    12     |      13      |  -1   | Finished |   2   |           6            |
|  ALO   |    Grid    |    13     |      15      |  -2   | Finished |   2   |           16           |
|  OCO   |    Grid    |    14     |      8       |  +6   | Finished |   2   |           8            |
|  ALB   |    Grid    |    15     |      12      |  +3   | Finished |   2   |           16           |
|  HUL   |    Grid    |    16     | SQUALIFICATO |  NA   |   DSQ    |   2   |           5            |
|  LAW   |    Grid    |    17     |      16      |  +1   | Finished |   2   |           14           |
|  BOR   |    Grid    |    18     |      18      |   0   | Finished |   2   |           13           |
|  STR   |    Grid    |    19     |      17      |  +2   | Finished |   2   |           12           |
|  BEA   |    Grid    |    20     |      10      |  +10  | Finished |   2   |           14           |

##### Maybe Important Team Radio

- Lap 4 Low grip for Hamilton
- Lap 7 Gasly mentions Leclerc struggling with medium tyres
- Lap 9 Inconsistent brakes for Leclerc
- Lap 10 Piastri starts struggling
- Lap 10 Soft tyres users start to struggle
- Lap 18 Low grip for Verstappen
- Lap 21 Overheating for Verstappen
- Lap 23 Verstappen struggles with breaking

#### Strategies


| Strategy | Count |
| :------: | :---: |
|  1-stop  |   0   |
|  2-stop  |  18   |
|  3-stop  |   2   |

>[!INFO] 
>- Sainz's 3-stop **was** taken in consideration since his retirement happened late enough in the race 44/52
>- Hulkenberg's 2-stop **was** taken in consideration since, despite his disqualification, he finished the race


---

#### Monza

| Driver | Start Type | Start Pos | Finish Pos  | Delta |  Status  | Stops | Lap First Pit |
| :----: | :--------: | :-------: | :---------: | :---: | :------: | :---: | :-----------: |
|  VER   |    Grid    |     1     |      1      |   0   | Finished |   1   |      37       |
|  NOR   |    Grid    |     2     |      2      |   0   | Finished |   1   |      46       |
|  PIA   |    Grid    |     3     |      3      |   0   | Finished |   1   |      45       |
|  LEC   |    Grid    |     4     |      4      |   0   | Finished |   1   |      33       |
|  RUS   |    Grid    |     5     |      5      |   0   | Finished |   1   |      27       |
|  ANT   |    Grid    |     6     |      9      |  -3   | Finished |   1   |      28       |
|  BOR   |    Grid    |     7     |      8      |  -1   | Finished |   1   |      20       |
|  ALO   |    Grid    |     8     |  RITIRATO   |  NA   |   DNF    |   1   |      20       |
|  TSU   |    Grid    |     9     |     13      |  -4   | Finished |   1   |      19       |
|  HAM   |    Grid    | 10 (PEN)  |      6      |  +4   | Finished |   1   |      38       |
|  BEA   |    Grid    |    11     |     12      |  -1   | Finished |   1   |      18       |
|  HUL   |    Grid    |    12     | NON PARTITO |  NA   |   DNS    |   -   |       -       |
|  SAI   |    Grid    |    13     |     11      |  +2   | Finished |   1   |      30       |
|  ALB   |    Grid    |    14     |      7      |  +7   | Finished |   1   |      41       |
|  OCO   |    Grid    |    15     |     15      |   0   | Finished |   1   |      51       |
|  STR   |    Grid    |    16     |     18      |  -2   | Finished |   1   |      49       |
|  COL   |    Grid    |    17     |     17      |   0   | Finished |   1   |      33       |
|  LAW   |    Grid    |    18     |     14      |  +4   | Finished |   1   |       9       |
|  GAS   |  Pit Lane  | PIT-LANE  |     16      |  +4   | Finished |   1   |      49       |
|  HAD   |  Pit Lane  | PIT-LANE  |     10      |  +10  | Finished |   1   |      32       |

#### Strategies


| Strategy | Count |
| :------: | :---: |
|  1-stop  |  19   |
|  2-stop  |   -   |
|  3-stop  |   -   |

>[!INFO] Hulkenberg's DNS made it impossible to take his strategy under account

---

#### Silverstone

| Driver | Start Type | Start Pos | Finish Pos  | Delta |  Status  | Stops | Lap First Pit |
| :----: | :--------: | :-------: | :---------: | :---: | :------: | :---: | :-----------: |
|  VER   |    Grid    |     1     |      5      |  -4   | Finished |   2   |      11       |
|  PIA   |    Grid    |     2     |      2      |   0   | Finished |   2   |      11       |
|  NOR   |    Grid    |     3     |      1      |  +2   | Finished |   2   |      11       |
|  RUS   |    Grid    |     4     |     10      |  -6   | Finished |   2   |      10       |
|  HAM   |    Grid    |     5     |      4      |  +1   | Finished |   2   |      11       |
|  LEC   |    Grid    |     6     |     16      |  -10  | Finished |   2   |      10       |
|  ALO   |    Grid    |     7     |      9      |  -2   | Finished |   2   |      11       |
|  GAS   |    Grid    |     8     |      6      |  +2   | Finished |   2   |      11       |
|  SAI   |    Grid    |     9     |     12      |  -3   | Finished |   2   |      11       |
|  ANT   |    Grid    | 10 (PEN)  |  RITIRATO   |  NA   |   DNF    |   3   |       2       |
|  TSU   |    Grid    |    11     |     15      |  -4   | Finished |   2   |      11       |
|  HAD   |    Grid    |    12     |  RITIRATO   |  NA   |   DNF    |   1   |      10       |
|  ALB   |    Grid    |    13     |      8      |  +5   | Finished |   2   |      12       |
|  OCO   |    Grid    |    14     |     13      |  +1   | Finished |   2   |      18       |
|  LAW   |    Grid    |    15     |  RITIRATO   |  NA   |   DNF    |   0   |       -       |
|  BOR   |    Grid    |    16     |  RITIRATO   |  NA   |   DNF    |   0   |       -       |
|  STR   |    Grid    |    17     |      7      |  +10  | Finished |   3   |       6       |
|  BEA   |    Grid    | 18 (PEN)  |     11      |  +7   | Finished |   2   |      10       |
|  HUL   |    Grid    |    19     |      3      |  +16  | Finished |   2   |       9       |
|  COL   |  Pit Lane  | PIT-LANE  | NON PARTITO |  (?)  |   DNS    |   0   |       -       |

>[!INFO] Quasi tutti i piloti sono partiti con intermediate

#### Strategies


| Strategy | Count |
| :------: | :---: |
|  1-stop  |   0   |
|  2-stop  |  14   |
|  3-stop  |   1   |


>[!INFO] 
>- Antonelli's 3-stop was not taken into account since he retired on Lap 23
>- Hadjar's 1-stop was not taken into account since he retired on Lap 17

---

#### Monaco

| Driver | Start Type | Start Pos | Finish Pos | Delta |  Status  | Stops | Lap First Pit |
| :----: | :--------: | :-------: | :--------: | :---: | :------: | :---: | :-----------: |
|  NOR   |    Grid    |     1     |     1      |   0   | Finished |   2   |      19       |
|  LEC   |    Grid    |     2     |     2      |   0   | Finished |   2   |      22       |
|  PIA   |    Grid    |     3     |     3      |   0   | Finished |   2   |      20       |
|  VER   |    Grid    |     4     |     4      |   0   | Finished |   2   |      28       |
|  HAD   |    Grid    |     5     |     6      |  -1   | Finished |   2   |      14       |
|  ALO   |    Grid    |     6     |  RITIRATO  |  NA   |   DNF    |   1   |      16       |
|  HAM   |    Grid    |  7 (PEN)  |     5      |  +2   | Finished |   2   |      18       |
|  OCO   |    Grid    |     8     |     7      |  +1   | Finished |   2   |      16       |
|  LAW   |    Grid    |     9     |     8      |  +1   | Finished |   2   |      31       |
|  ALB   |    Grid    |    10     |     9      |  +1   | Finished |   2   |      32       |
|  SAI   |    Grid    |    11     |     10     |  +1   | Finished |   2   |      48       |
|  TSU   |    Grid    |    12     |     17     |  -5   | Finished |   2   |       1       |
|  HUL   |    Grid    |    13     |     16     |  -3   | Finished |   2   |      12       |
|  RUS   |    Grid    |    14     |     11     |  +3   | Finished |   2   |      62       |
|  ANT   |    Grid    |    15     |     18     |  -3   | Finished |   2   |      69       |
|  BOR   |    Grid    |    16     |     14     |  +2   | Finished |   3   |       1       |
|  GAS   |    Grid    |    17     |  RITIRATO  |  NA   |   DNF    |   1   |       1       |
|  COL   |    Grid    |    18     |     13     |  +5   | Finished |   2   |      13       |
|  STR   |    Grid    | 19 (PEN)  |     15     |  +4   | Finished |   2   |      12       |
|  BEA   |    Grid    | 20 (PEN)  |     12     |  +8   | Finished |   2   |       1       |


#### Strategies


| Strategy | Count |
| :------: | :---: |
|  1-stop  |   1   |
|  2-stop  |  17   |
|  3-stop  |   3   |

>[!INFO] Gasly was not taken into account since he retired on Lap 7


---

>In questa analisi, i casi di ritiri, squalifiche e non partenze non verranno presi in considerazione ma saranno comunque mantenuti nel dataset come osservazioni annotate. Partenze da pit-lane invece sono incluse, ma trattate come condizione distinta


Source: [[UniPG]]

---
Created: 2026-04-20