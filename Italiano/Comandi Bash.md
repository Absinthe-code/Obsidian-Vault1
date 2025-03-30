## Comandi Bash

- `man [command]`: ottieni informazioni su altri comandi (man = manuale). Per uscire premere Q (quit)
- `[command] --help`: stessa cosa ma funziona anche per altri terminali oltre a Bash
- `whoami`: mostra l'utente che sta venendo utilizzato
- `date`: mostra la data attuale
- `clear`: pulisce il terminale
- `history`: mostra gli ultimi comandi utilizzati
	- `![id]`: esegue il comando contrassegnato dal suo numero di identificazione
- exit:
- exec: esegui il comando
- return	Exit a shell function
- eject: 
- file:
- ftp:
- jobs:
- Kill:
	- Killall:
- `start/open/xdg-open`: apre una directory nella GUI o un sito internet (controlla se è vero)
	- windows - `start [filename/website]`
	- mac - `open [filename/website]`
	- linux - `xdg-open [filename/website]`
- mount	Mount a file system
- passwd	Modify a user password
- shopt	Shell Options
- 	.	Run a command script in the current shell
-  	!!	Run the last command again
- 	###	Comment / Remark
- chmod: 
### Navigazione

- `pwd`: mostra la directory (o cartella) corrente, nel quale 
- stiamo lavorando. ~ denota la home
- `ls`: fa una lista di tutti i file all'interno di una cartella (directory comprese)
	- `ls [directory]`: fa una lista dei contenuti di quella specifica directory
	- `ls -a`: mostra anche i file nascosti
	- `ls -l`: mostra ulteriori informazioni sui file
	- `ls -a -l`: si possono unire più opzioni (flags)cd 
	- `ls -r`: mostra i file nell'ordine inverso
- `dir`: mostra i file nella directory corrente
	- `dir [directory]`: mostra i file nella directory selezionata
- `cd`: cambia la directory nel quale siamo, se scritto da solo ci porta alla Home directory così come   `cd ~`  
	- `cd [directory]`: ci porta alla directory specificata
	- `cd ..`: ci riporta alla directory al livello superiore
	- `cd /`: ci porta alla root directory della macchina
	- `cd -`: ci riporta all'ultima directory in cui siamo 
	- NB : se il nome della cartella ha uno spazio devi usare \\ prima dello spazio. Vale anche per le parentesi

### Creazione/Rimozione

- `mkdir [directory]`: crea una nuova directory
- `touch [filename]`: crea un nuovo file, anche multipli file se separati da uno spazio
	- `touch [filename]-{[n]..[m]}.extension`: crea multipli file numerati dall'n a m
- mkfile: 
- mktemp:
- `rm [filename]`: elimina il file specificato
	- `rm -r [directory]`: elimina una directory specificata
	- `rm -rf [directory]`: elimina tutto quello che c'è in una directory file compresi
- 	rmdir	Remove folder(s)
### Copia/Sposta

- `cp [filename] [directory/filename]`: copia il file nella directory selezionata con il nome selezionato
- `mv [filename] [directory/filename]`: muove il file nella directory selezionata con il nome selezionato
	- `mv [filename] [newFilename]`: cambia il nome del file
	-  `mv [directory/filename] [filename]`: spostare da una cartella interna a quella corrente
- mmv	Mass Move and rename (files)
- 	sort	Sort text files
### Mostra/Scrivi

- `cat [filename]`: concatena testo, mostra e scrive un testo
	- `cat > [filename]`: sovrascrive in un file (Ctrl+D per uscire)
	- `>`: sovrascrive il contenuto del file
	- `>>`: aggiunge al contenuto di un file una riga sotto
	- `cat -n [filename]`: mostra il contenuto con il numero di riga
- `less [filename]`: mostra il contenuto e permette di navigare su e giù con le frecce
- more:
- `head [filename]`: mostra le prime righe del file (default 10)
	- `head -n [lines] [filename]`: legge le prime n righe del file
- `tail [filename]`: mostra le ultime righe del file (default 10)
	- `tail -n [lines] [filename]`: legge le ultime n righe del file
- `nano [filename]`: semplice editor di testo preesitente in Bash
- `echo "[text]"`: stampa un testo nel terminale
	- `echo "[text]" > [filename]`: scrive a il testo all'inizio del file
- gawk:
- lpr:
- lsof: list open files
- more	Display output one screen at a time
- most	Browse or page through a text file
- nl	Number lines and write files
- notify-send	Send desktop notifications
- 	rcp	Copy files between two machines
- 	rename	Rename files
- 	vi	Text Editor
- 	watch	Execute/display a program periodically
### Ricerca/Piping

- `grep "[searchterm]" [filename]`: ricerca un termine all'interno di un file
- egrep:
- fgrep:
- locate:
- `find "[searchterm]" [filename]`: ricerca le posizioni dei file e directory sulla base delle condizioni che gli specifichiamo
	- `find . -name "[filename]"`: cerca nella directory corrente il file per nome
	- `find . -name "[file*]"`: cerca nella directory corrente tutti i file che che cominciano con "file"
	- `find . -empty`: cerca tutti i file vuoti
	- `find . -name "[filename]" -delete`: elimina il file con il nome specificato
- `> [filename/directory]`: se aggiunto dopo un comando esegue il "piping", reindirizza l'output del comando precedente all'output specificato
- 	tee	Redirect output to multiple files
### Scorciatoie/Compressione

- `ln -s [file/directory] [simlinkname] `: crea una sim link (scorciatoia) per un altro file o directory
- link: 
- `tar -czvf [filename.tar.gz] [filename]`: crea una Tarball, un file compresso simile a zip
	- `tar -tzvf [filename.tar.gz]`: mostra cosa c'è nel file compresso
	- `tar -xzvf [filename.tar.gz]`: estrae il file compresso
- gzip:
- 	rar	Archive files with compression
-  	unrar	Extract files from a rar archive
- 	xz	Compress or decompress .xz and .lzma files
- 	zip	Package and compress (archive) files
### Network/Connessione

- ifconfig:
- ifdown: Stop a network interface
- ifup: Start a network interface up
- 	mtr	Network diagnostics (traceroute/ping)
- 	nc	Netcat, read and write data across networks
- 	netstat	Networking connections/stats
- 	ping	Test a network connection
- 	popd	Restore the previous value of the current directory
- 	screen	Multiplex terminal, run remote shells via ssh
- 	scp	Secure copy (remote file copy)
### Processi/Performance

-  	pgrep	List processes by name
-  	pkill	Kill processes by name
- 	quota	Display disk usage and limits
- quotacheck	Scan a file system for disk usage
- 	ram	ram disk device

### Utenti/SSH

-  ssh	Secure Shell client (remote login program)
- 	users	List users currently logged in
-  	who	Print all usernames currently logged in
- 	useradd	Create new user account
- userdel	Delete a user account
- usermod	Modify user account
- 	w	Show who is logged on and what they are doing
- 	write	Send a message to another user

https://www.gnu.org/software/coreutils/manual/coreutils.html