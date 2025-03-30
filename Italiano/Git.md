E' un [[software di controllo di versione]] o ([[VCS]]) distribuito utilizzabile da [[interfaccia a riga di comando]]  (o [[CLI ]]). Permette di monitorare le modifiche apportate a un software e ripristinare versioni precedenti, coordinare il il lavoro tra più sviluppatori e operare sulla stessa base di codice senza necessariamente essere sullo stesso network.

Permette di caricare il codice su una [[Repository]] (archivio?) remota come [[GitHub]].

Tiene traccia della cronologia del codice facendo delle istantanee dei tuoi file. Queste istantanee (Snapshot) vengono fatte attraverso i [[Commit]] e puoi ripristinare versioni precedenti fatte con i Commit.

Contiene [[git bash]], una interfaccia a riga di comando (CLI) dal quale possiamo eseguire i comandi di Git
## Terminologia

Repository
Commit
Branch
Distribuito
Decentralizzato
Clonare
- In Git, "HEAD" is a reference to the current commit your working directory is based on. It plays a crucial role in Git's branching and commit structure. Here are the key points to understand about HEAD:
- **Current Branch Reference**:
    - HEAD points to the latest commit on the current branch you are working on. Essentially, it represents your "current position" in the repository history.
## [[Comandi Bash]]

Bash è lo [[Shell]] utilizzato da git. I comandi di Bash sono fondamentali per muoversi all'interno di un terminale e per l'utilizzo di git
## Comandi di Git

- `git init`: inizializza la Repository corrente
- `git add <file>` : aggiunge i file a un area di staging o all'indice, pronto per un Commit
- `git status`: mostra lo status della repository e della staging area pronti per il Commit
- `git rm --cached [filename]`: rimuove un file dalla staging area e non verrà incluso nel prossimo Commit
	- `git rm -r --cached .`: rimuove tutti i file dalla staging area (-r significa in modo ricorsivo)
- `git add *.html`: aggiunge tutti i file che finiscono con .html per esempio
	- `git add .`: aggiunge tutto alla staging area
### Git Commit

- `git commit`: prende lo snapshot dello staging e ne esegue il commit nella cronologia di progetto.
	- normalmente apre l'editor di testo Vim 
		- i : insert mode, ti permette di scrivere
		- esc : esce dalla insert mode
		- :wq : esce da Vim
	- `git commit -m "[comment]"`: non apre Vim e esegue il Commit con il commento specificato
### Git Log

- `git log`: mostra i commit passati
	- `git log -oneline`: mostra i commit passati in modo compatto
### Ripristino

- `git checkout [id]`: checkout mostra il codice così com'era nel commit specificato
- `git revert [id]`: revert ripristina il codice a com'era in un commit specificato senza eliminarlo
	- apre Vim, chiudere con :wq
- `git reset [id]`: reset ripristina il codice a com'era in un commit specificato eliminando i commit eseguiti successivamente 
	- `git reset [id] --hard` elimina anche i cambiamenti nei file correnti
### Git Ignore

- `touch .gitignore`: comando bash per creare un file di testo dove specifichiamo i file che non verranno mai inclusi nel Commit
- aggiungi i file con estensione o le directory (es: `/NomeDirectory`) ognuno in una nuova riga
- puoi anche aggiungere tutti i file con un estensione o un nome specifico con `*.txt` e simili
### Rami/Branches

 - `git branch [branchname]`: crea un "ramo", cioè una copia del codice dove poter lavorare senza modificare il ramo principale ("master" o "main")
	 - `git branch -d [branchname]`: elimina un ramo
	 - `git branch -a [branchname]`: mostra tutti i rami
 - `git checkout [branchname]`: cambia il branch in quello specificato
	 - `git checkout -b [branchname]`: crea un branch e cambia il branch in quello specificato
### Fusione/Merging

- `git merge [branchname]`: unisce il ramo corrente con quello principale
	- `git merge [branchname] -m "comment"`: ???
- recursive strategy?
- Merge Conflict: avviene quando c'è un conflitto tra due diversi rami durante una fusione
### Push/Clone

 - `git push`: carica in una remote repository il codice (usa dopo aver settato il branch upstream)
 - `git clone`: clona il codice da una remote repository nel sistema locale
 - `git remote add origin [URL]`: crea un alias chiamato "origin" per l'URL specificato
 - `git remote -v`: mostra le repository remote con il loro alias
 
---
## GitHub

Permette di ospitare delle repository in maniera remota in modo da rendere accessibile il codice attraverso una connessione internet.

- `git remote add origin (link)
### Git Clone

- `git clone [URL]`: clona una repository in una directory inizializzata con git
### Git Push

- `git push [URL]`: carica una repository su GitHub o simili
	- `git push [URL] [branchname]`: carica nel branch selezionato
	- `git push origin [branchname]`: carica una repository attraverso un suo alias per il suo URL (solitamente "origin")
	-  `git push origin --force`: forza il cambiamento della repository remota 
	- `git push -u origin [branchname]:` -u vuol dire upstream, non è necessario specificare il branch, userà quello con lo stesso nome
	- `git push --set-upstream origin [branchname]`: per specificare un upstream
	- `git push origin --delete [branchname]`:

---
## Git Flow/Workflow

`git log --graph --oneline --decorate --all`: Mostra il grafico dei commit nei diversi branch

![[Pasted image 20240620152445.png]]
### Develop
- `git flow init`: inizializzazione del git flow e creazione del ramo `develop` per lo sviluppo di nuove feature
	- `git push -u origin develop`: per creare il ramo upstream su GitHub
### Feature
- `git flow feature start [featurename]`: crea un nuovo branch chiamato `feature/[featurename]` a partire dal branch `develop` per lo sviluppo della feature specificata e cambia il ramo corrente con quello appena creato
	- `git push -u origin feature/[featurename]`: per creare il ramo upstream su GitHub
	- `git flow feature finish [featurename]`: finisce la feature ed esegue il merging con il branch `develop`
### Release
- `git flow release start 1.0.0`: crea il branch `release/1.0.0` a partire dal branch `develop`
	- `git push -u origin release/1.0.0`: per creare il ramo upstream su GitHub
	- `git flow release finish 1.0.0`: finisce la release ed esegue il merging con il branch `develop` e il branch `main`, infine elimina il branch `release/1.0.0`
### Hotfix
- `git flow hotfix start hotfix-1.0.1`: crea il branch `hotfix/hotfix-1.0.1` a partire dal ramo `main` 
	- `git push -u origin hotfix/hotfix-1.0.1`: per creare il ramo upstream su GitHub
	- `git flow hotfix finish hotfix-1.0.1`: finisce la hotfix ed esegue il merging con il branch `develop` e il branch `main`, infine elimina il branch `hotfix/hotfix-1.0.1`
### Tags
- `git tag -d <tagname>` eliminare una tag
- `git push origin :refs/tags/<tagname>` eliminare remoto
#### Key Concepts of Git Flow (GPT)

1. **Main Branches**:
    - **`main` (or `master`)**: The main branch where the source code of HEAD always reflects a production-ready state.
    - **`develop`**: The main development branch where the source code of HEAD always reflects a state with the latest delivered development changes for the next release.
2. **Supporting Branches**:
    - **Feature branches**: Used to develop new features for the upcoming or a distant future release. Typically exist only in developer repositories.
    - **Release branches**: Support preparation of a new production release. Allow for minor bug fixes and preparing meta-data for a release (version number, build dates, etc.).
    - **Hotfix branches**: Maintenance or “emergency” fixes for the production releases. Allow for quickly fixing a live production issue without disrupting ongoing work.
### Current Release

 git flow release start 0.0.2
 git push -u origin release/0.0.2
 modify readme
  git add .
  git commit -m "modified readme.md for release 0.0.2"
  git push
  git flow release finish 0.0.2
  git push
  git checkout main
  git push
  git checkout develop
  git push

---
## Configurazione Iniziale

dobbiamo configurare Nome, Email, Editor Predefinito e Terminazione di Riga

possiamo farlo su tre diversi livelli

- Livello di Sistema: tutti gli utenti
- Livello Globale: tutti i repository dell'utente corrente
- Livello Locale: il repository corrente

Nella Bash Shell:

``` 
git config --global user.name "Esempio"

git config --global user.email "esempio@gmail.com"

git config --global core.editor "code --wait" (per VS code)
```

per aprire l'editor predefinito per visualizzare e modificare il file di configurazione:

`git config --global -e`

le terminazioni di riga in Windows sono contrassegnate da due caratteri speciali:

1. \\\\r è il Carriage Return
2. \\\\n è il Line Feed

in Linux e MacOS è solo il Line Feed 

Windows: `git config --global core.autocrlf true`

Linux/MacOS: `git config --global core.autocrlf input`