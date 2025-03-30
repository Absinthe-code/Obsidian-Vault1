Profondità di passata: Ap (mm)
Avanzamento al giro: fn (mm/giro)
Velocità di taglio: Vc (m/min) 

- Angolo di Registrazione Primario:
	- posizione del tagliente rispetto alla direzione di taglio, è l'angolo del tagliente rispetto alla direzione di taglio 
	- Esempio: 95°
	  ![[Pasted image 20240429181705.png]]
	  
- Angolo di attacco: 
	- angolo tra la superficie di attacco durante la tornitura e il tagliente principale dell'inserto ...
	  
	  ![[Pasted image 20240429181943.png]]
	  
- Angolo di registrazione secondario:
  
  ![[Pasted image 20240429182437.png]]
  se hai gli angoli di tornitura primaria e secondaria uguali puoi fare tornitura longitudinale e trasversale con lo stesso utensile
  ![[Pasted image 20240429182526.png]]
  
  Tornitura esterna?
  Intestatura?
  Inserto tipo C?

- Principalmente ci sono 4 geometrie degli utensili:
	- Angolo del tagliente
	- Angolo di registrazione primario
	- Dimensione inserto
	- Raggio di punta
	- + Direzione dell'angolo di taglio per identificare correttamente l'angolo di registrazione
	-  + Quadrante per definire l'orientamento della punta e dell'utensile
	  
	  ![[Pasted image 20240429183215.png]]
	  ![[Pasted image 20240429183345.png]]
	  
- lista utensili di un controllo numerico siemens
  ![[Pasted image 20240429183429.png]]

- Esempio Fanuc
  
  ![[Pasted image 20240429183535.png]]
  
- Esempio Fargor
  
  ![[Pasted image 20240429183606.png]]
  
- Angoli di registrazioni comuni
	- Inserto di forma C: Romboidale a 80 gradi 
	  ![[Pasted image 20240429184015.png]]
		- 1. Angolo di registrazione 95°
		- 2. Angolo di registrazione a 75° o C di recupero
		  ![[Pasted image 20240429183923.png]]
		  
	- Inserto a forma D: Romboidale a 55°
	  ![[Pasted image 20240429184038.png]]
	- Molto utilizzato nelle operazioni di finitura dato l'angolo di taglio molto piccolo che lo rende adatto a fare trafilature, scarichi e soprattutto riducendo la superficie di contatto tende a ridurre leggermente le vibrazioni

1. più diffuso è 93°
2. 107.5°
3. 62.5° o versione neutra
   
![[Pasted image 20240429184442.png]]

La scelta dipende dal tipo di lavorazione che vogliamo mettere in atto

### Inserto di forma S

Di forma quadrata, di geometria robusta, largamente utilizzato in operazioni di sgrossatura pesante

![[Pasted image 20240429184648.png]]

## Differenze

Spessore del truciolo
Potenza richiesta 
Forze generate

Per esempio nella forma C il primo punto di contatto con il pezzo sarà la punta, che può danneggiare la punta o sforzarla troppo in generale
Nella forma S a 45° sarà la parte rettilinea del tagliente a toccare per prima il pezzo e in generale un andamento delle intensità delle forze più graduale e anche dell' assorbimento di potenze

![[Pasted image 20240429185305.png]]

nel caso della forma S otterremmo un angolo di 45° sul bordo della tornitura e ci vuole una seconda passata con l'inserto di forma C per ottenere il profilo desiderato

### Spessore del Truciolo h(mm)

Quantità di materiale misurata in modo perpendicolare al tagliente principale o la quantità di materiale che impegna il petto del tagliente

![[Pasted image 20240429190206.png]]

La Sezione del Truciolo è la stessa: Avanzamento al giro * Profondità di passata

![[Pasted image 20240429190301.png]]

in millimetri quadrati

Lo Spessore del Truciolo è diverso:
- Nel caso dell'inserto di tipo C abbiamo h circa uguale alla profondità di passata cioè h = fn per l'approssimazione dei piccoli angoli
- Nel caso dell'inserto di tipo S, la misura è fatta in maniera perpendicolare al tagliente quindi lo spessore del truciolo sarà inferiore all'avanzamento al giro
	- h = fn * sin(45°) = 0.21mm

Meno spessore = meno carico, per avere le stesse condizioni di carico potremmo aumentare l'avanzamento di fn/sin(45°) aumentando la produttività del 42% = 1/sin(45°)%

## Velocità di Taglio (m/min) iso

La velocità periferica con cui il materiale da lavorare impatta sul petto del tagliente

![[Pasted image 20240429191753.png]]

Sappiamo il diametro del pezzo e il numero di giri impostato sulla macchina utensile

Lo spazio lo calcoli come diametro * pi

Il tempo lo calcoli come 1/n. di giri

Vc = (D * pi * n. di giri ) / 1000 perché espresso in metri al minuto 

n. giri = Vc * 1000 / (D * pi) 

G97 = giri fissi in linguaggio ISO

## Lavorazione a velocità di taglio costante

utilizzabile solo su macchine a controllo numerico (Preferibile)

Per i controlli su base iso utilizzando la funzione G96

**Come decidere la velocità di taglio?

Il materiale del pezzo ha un ruolo fondamentale, per un pezzo di alluminio potremmo usare velocità di taglio più alte? 

il materiale del tagliente è un altro fattore, un tagliente in HSS o acciaio super rapido è diverso da uno in metallo duro

Tenacità del tagliente?



## Lavorazione a numero di giri costanti

G97 = giri fissi in linguaggio ISO, usare con cautela

## Materiali: Classificazione ISO

Ci sono 6 famiglie di materiali: 

## Velocità di taglio e durata

Frederic Winslow Taylor

![[Pasted image 20240429193814.png]]

Esempio per metalli duri

Aumentando del 20% la velocità di taglio la durata del tagliente si dimezza

Labbro di usura e si misura in mm, le informazioni sono fornite dai costruttori degli utensili ma solo per le operazioni di tornitura

La durata economica di un tagliente è di circa 15-20 minuti, è il tempo medio in cui un tagliente si ripaga da solo

![[Pasted image 20240429194609.png]]

![[Pasted image 20240429194711.png]]

Esempio utensili in carburo

