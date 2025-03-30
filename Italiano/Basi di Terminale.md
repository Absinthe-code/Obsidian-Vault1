Un terminale è un [[interfaccia a riga di comando]] (o [[CLI]]).

Il più utilizzato è Bash, presente in tutti i sistemi operativi Linux e MacOS. In Windows è possibile usare Git Bash o usare lo standard PowerShell o cmd.

Utilizzi molto comuni sono l'accesso a server remoti tramite [[SSH]] (Secure Shell), l'utilizzo dei Command Line Tools come npm per l'installazione dei pacchetti Node e l'utilizzo di software per il controllo delle versioni come Git.

Esistono interi sistemi operativi che non hanno una [[GUI]] (Headless systems) come Ubuntu Server e funzionano completamente attraverso un Terminale.
## Terminologia

Terminale - strumento in cui vengono scritti comandi che vengono poi eseguiti dallo Shell.

Prompt dei Comandi - l'interfaccia del terminale, termine usato in maniera intercambiabile con Terminale. Più comune in Windows.

Shell - il programma che viene eseguito dal terminale che effettivamente esegue i comandi. Lo si può pensare come il sistema operativo del Terminale.
## Scorciatoie da Tastiera

- Freccia su e giù - scorre tra i comandi usati in precedenza
- `Tab` - auto completa i comandi, se ci sono più comandi con le stesse iniziali fa una lista dei comandi suggeriti 
- `Ctrl+L` - pulisce il terminale
- `Ctrl+C` - elimina il comando corrente
- `Ctrl+R` - cerca un comando tra quelli disponibili
- `Ctrl+D` - chiude il terminale/esce da `cat`
## Comandi Bash

- `man [command]`: ottieni informazioni su altri comandi (man = manuale). Per uscire premere Q (quit)
- `[command] --help`: stessa cosa ma funziona anche per altri terminali oltre a Bash
- `whoami`: mostra l'utente che sta venendo utilizzato
- `date`: mostra la data attuale
- `clear`: pulisce il terminale
- `history`: mostra gli ultimi comandi utilizzati
	- `![id]`: esegue il comando contrassegnato dal suo numero di identificazione
	  
---
### Navigazione

- `pwd`: mostra la directory (o cartella) corrente, nel quale stiamo lavorando. ~ denota la home
- `ls`: fa una lista di tutti i file all'interno di una cartella (directory comprese)
	- `ls [directory]`: fa una lista dei contenuti di quella specifica directory
	- `ls -a`: mostra anche i file nascosti
	- `ls -l`: mostra ulteriori informazioni sui file
	- `ls -a -l`: si possono unire più opzioni (flags)
	- `ls -r`: mostra i file nell'ordine inverso
- `cd`: cambia la directory nel quale siamo, se scritto da solo ci porta alla Home directory così come   `cd ~`  
	- `cd [directory]`: ci porta alla directory specificata
	- `cd ..`: ci riporta alla directory al livello superiore
	- `cd /`: ci porta alla root directory della macchina
	- `cd -`: ci riporta all'ultima directory in cui siamo 
### Creazione/Rimozione

- `mkdir [directory]`: crea una nuova directory
- `touch [filename]`: crea un nuovo file, anche multipli file se separati da uno spazio
	- `touch [filename]-{[n]..[m]}.extension`: crea multipli file numerati dall'n a m
- `rm [filename]`: elimina il file specificato
	- `rm -r [directory]`: elimina una directory specificata
	- `rm -rf [directory]`: elimina tutto quello che c'è in una directory file compresi
### Copia/Sposta

- `cp [filename] [directory/filename]`: copia il file nella directory selezionata con il nome selezionato
- `mv [filename] [directory/filename]`: muove il file nella directory selezionata con il nome selezionato
	- `mv [filename] [newFilename]`: cambia il nome del file
	-  `mv [directory/filename] [filename]`: spostare da una cartella interna a quella corrente
### Mostra/Scrivi

- `cat [filename]`: mostra e scrive il contenuto di un file. Ha anche altre funzioni
	- `cat > [filename]`: scrive in un file
	- `>`: sovrascrive il contenuto del file
	- `>>`: aggiunge al contenuto di un file una riga sotto
	- `cat -n [filename]`: mostra il contenuto con il numero di riga
- `less [filename]`: mostra il contenuto e permette di navigare su e giù con le frecce
- `head [filename]`: mostra le prime righe del file (default 10)
	- `head -n [lines] [filename]`: legge le prime n righe del file
- `tail [filename]`: mostra le ultime righe del file (default 10)
	- `tail -n [lines] [filename]`: legge le ultime n righe del file
- `start/open/xdg-open`: apre una directory nella GUI o un sito internet (controlla se è vero)
	- windows - `start [filename/website]`
	- mac - `open [filename/website]`
	- linux - `xdg-open [filename/website]`
- `nano [filename]`: semplice editor di testo presente in Bash
- `echo "[text]"`: stampa un testo nel terminale
	- `echo "[text]" > [filename]`: scrive a il testo all'inizio del file
### Ricerca/Piping

- `grep "[searchterm]" [filename]`: ricerca un termine all'interno di un file
- `find "[searchterm]" [filename]`: ricerca le posizioni dei file e directory sulla base delle condizioni che gli specifichiamo
	- `find . -name "[filename]"`: cerca nella directory corrente il file per nome
	- `find . -name "[file*]"`: cerca nella directory corrente tutti i file che che cominciano con "file"
	- `find . -empty`: cerca tutti i file vuoti
	- `find . -name "[filename]" -delete`: elimina il file con il nome specificato
- `> [filename/directory]`: se aggiunto dopo un comando esegue il "piping", reindirizza l'output del comando precedente all'output specificato
### Scorciatoie/Compressione

- `ln -s [file/directory] [simlinkname] `: crea una sim link (scorciatoia) per un altro file o directory
- `tar -czvf [filename.tar.gz] [filename]`: crea una Tarball, un file compresso simile a zip
	- `tar -tzvf [filename.tar.gz]`: mostra cosa c'è nel file compresso
	- `tar -xzvf [filename.tar.gz]`: estrae il file compresso






