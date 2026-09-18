---
date: 27/03/26
tags:
  - UniPG
  - sistemi
  - lab
---
Cosa usa bash per creare un collegamento tra output e input? Usa una **pipe**

>[!Info] IPC (Interprocess Communication)
>Esistono vari strumenti per questo comunicazione:
>- signal
>- socket
>- **pipe**
>- semafori (sincornizzazione)

Pipe, unidirezionali in GNU/Linux. Bidirezionali in certi sistemi (Windows). 
Connettono i processi tramite un canale di comunicazione.
Ha due estremità: *read end* per la lettura e *write end* per la scrittura
La comunicazione non è strutturata 

>[!warning] Pipes rimangono anche dopo il reboot di una macchina

Due tipi di Pipe (in linux)
1) Senza nome (unnamed)

2) Con nome (named/FIFO)
---
1) **_Unnamed_**: Create con pipe(), i processi comunicati condividono file descriptor per la lettura/scrittura (fork(2))

2) **_Named_**: File speciale (type p in)

---

```c
#include <unistd.h

int pipefd[2];
if (pipe(pipefd)) == -1) {
perror("pipe");
exit (EXIT_FAILURE)
}
```
- Crea la pipe e apre due estremità:
	- pipefd[0] *file descriptor* per la *read end* della pipe 
	- pipefd[1] *file descriptor* per la *write end* della pipe 
	- Ritorno: 0 se tutto ok. -1 per errore (*errno settata*)
- Creata la pipe e possibile leggere e scrivere dati, es.: con **read()** e **write()**

---
### Creazione named pipe

```c
int mkfifo (const char *pathname, mode_t mode)
```
- crea una *named pipe* di nome *pathname*
- visibile nel *filesystem* senza occupare spazio
- *mode* specifica permessi, in accordo con *umask* (*mode & ~umask*)
- **Persistenti**, rimangono anche dopo il *reboot*
- Utilizzabile de qualsiasi processo con il permesso 
### Apertura named pipe

```c
int open (const char *pathname, int flags);
```
- Una volta creata, *la named pipe* va aperta
- IN caso il lato opposto non sia stato aperto, **open** è bloccante (a meno che sia settato il flag **O_NONBLOCK**)
- In Linux è possibile aprire una *named pipe* in lettura e scrittura. Cio permette di raggiungere certi scopi, ma v usato con cautela


Source: [[00 - Sistemi Operativi|Sistemi Operativi]]

---
Created: 