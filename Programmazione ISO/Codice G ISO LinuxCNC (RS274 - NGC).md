##  Tabella di Riferimento Lettere

| LETTERA | SIGNIFICATO                                                                                                     |
| ------- | --------------------------------------------------------------------------------------------------------------- |
| A       | Asse A della Macchina                                                                                           |
| B       | Asse B della Macchina                                                                                           |
| C       | Asse C della Macchina                                                                                           |
| D       | Numero di Compensazione del Raggio Utensile                                                                     |
| F       | Velocità di Avanzamento                                                                                         |
| G       | Funzione Generale (Vedi Tabella dei Gruppi Modali)                                                              |
| H       | Indice di Compensazione Lunghezza Utensile                                                                      |
| I       | Offset X per Archi e Cicli Preimpostati G87                                                                     |
| J       | Offset Y per Archi e Cicli Preimpostati G87                                                                     |
| K       | Offset Z per Archi e Cicli Preimpostati G87. Rapporto di Movimento del Mandrino per Movimenti G33 Sincronizzati |
| M       | Funzione Miscellanea (Vedi Tabella dei Gruppi Modali)                                                           |
| N       | Numero di Linea                                                                                                 |
| O       | Nome Programma/Sottoprogramma                                                                                   |
| P       | Tempo di Attesa nei Cicli Preimpostati e con G4. Chiave Usata con G10                                           |
| Q       | Incremento di Avanzamento nei Cicli Preimpostati G73, G83                                                       |
| R       | Raggio dell'Arco o Piano del Ciclo Preimpostato                                                                 |
| S       | Velocità del Mandrino                                                                                           |
| T       | Selezione Utensile                                                                                              |
| U       | Asse U della Macchina                                                                                           |
| V       | Asse V della Macchina                                                                                           |
| W       | Asse W della Macchina                                                                                           |
| X       | Asse X della Macchina                                                                                           |
| Y       | Asse Y della Macchina                                                                                           |
| Z       | Asse Z della Macchina                                                                                           |
##  Tabella di Riferimento Codici G

| CODICE          | DESCRIZIONE                                                                                                          |
| --------------- | -------------------------------------------------------------------------------------------------------------------- |
| G0              | Movimento Coordinato a Velocità Rapida                                                                               |
| G1              | Movimento Coordinato a Velocità di Avanzamento                                                                       |
| G2, G3          | Movimento Elicoidale Coordinato a Velocità di Avanzamento                                                            |
| G4              | Attesa                                                                                                               |
| G5              | ~~Spline Cubica~~                                                                                                    |
| G5.1            | ~~B-Spline Quadratica~~                                                                                              |
| G5.2            | ~~NURBS, Aggiungi Punto di Controllo~~                                                                               |
| G7              | Modalità Diametro (Torni)                                                                                            |
| G8              | Modalità Raggio (Torni)                                                                                              |
| G10 L0          | Ricarica Dati Tabella Utensili                                                                                       |
| G10 L1          | Imposta Voce Tabella Utensili                                                                                        |
| G10 L10         | Imposta Tabella Utensili, Calcolato, Pezzo                                                                           |
| G10 L11         | Imposta Tabella Utensili, Calcolato, Fixture                                                                         |
| G10 L2          | Impostazione Origine Sistema di Coordinate                                                                           |
| G10 L20         | Impostazione Origine Sistema di Coordinate Calcolata                                                                 |
| G17 - G19.1     | Selezione del Piano                                                                                                  |
| G20, G21        | Imposta Unità di Misura                                                                                              |
| G28 - G28.1     | Vai a Posizione Predefinita                                                                                          |
| G30 - G30.1     | Vai a Posizione Predefinita                                                                                          |
| *G33*           | *Movimento Sincronizzato con il Mandrino*                                                                            |
| *G33.1*         | *Filettatura Rigida*                                                                                                 |
| *G38.2 - G38.5* | *Sondaggio*                                                                                                          |
| G40             | Annulla Compensazione Utensile                                                                                       |
| G41, G42        | Compensazione Utensile                                                                                               |
| *G41.1, G42.1*  | *Compensazione Utensile Dinamica*                                                                                    |
| *G43*           | *Utilizza Compensazione Lunghezza Utensile dalla Tabella Utensili*                                                   |
| *G43.1*         | *Compensazione Lunghezza Utensile Dinamica*                                                                          |
| G43.2           | Applica Compensazione Lunghezza Utensile Addizionale (==controlla==)                                                 |
| G49             | Annulla Compensazione Lunghezza Utensile                                                                             |
| *G50*           | *Imposta Velocità Massima Mandrino* \*                                                                               |
| G52             | Offset Sistema di Coordinate Locale                                                                                  |
| G53             | Movimento in Coordinate Macchina                                                                                     |
| G54 - G59.3     | Selezione Sistema di Coordinate (1 - 9)                                                                              |
| G61             | Modalità Percorso Esatto                                                                                             |
| G61.1           | Modalità Arresto Esatto                                                                                              |
| G64             | Modalità Controllo Percorso con Tolleranza Opzionale                                                                 |
| G70             | Ciclo di Finitura per Tornitura                                                                                      |
| G71 - G72       | Ciclo di Sgrossatura per Tornitura                                                                                   |
| G73             | Ciclo di Foratura con Frantumazione Trucioli                                                                         |
| G74             | Ciclo di Filettatura Sinistra con Attesa                                                                             |
| *G76*           | *Ciclo di Filettatura Multipasso per Tornitura*                                                                      |
| G80             | Annulla Modalità di Movimento                                                                                        |
| G81             | Ciclo di Foratura                                                                                                    |
| G82             | Ciclo di Foratura con Attesa                                                                                         |
| G83             | Ciclo di Foratura con Percussione                                                                                    |
| G84             | Ciclo di Filettatura Destra con Attesa                                                                               |
| G85             | Ciclo di Alesatura, Senza Attesa, Avanzamento in Uscita                                                              |
| G86             | Ciclo di Alesatura, Arresto, Uscita Rapida                                                                           |
| G87             | Ciclo di Alesatura Inversa (Non Ancora Implementato)                                                                 |
| G88             | Ciclo di Alesatura, Arresto, Uscita Manuale (Non Ancora Implementato)                                                |
| G89             | Ciclo di Alesatura, Attesa, Avanzamento in Uscita                                                                    |
| G90, G91        | Modalità Distanza                                                                                                    |
| G90.1, G91.1    | Modalità Distanza per Archi                                                                                          |
| G92             | Offset del Sistema di Coordinate                                                                                     |
| G92.1, G92.2    | Annulla Offset G92                                                                                                   |
| G92.3           | Ripristina Offset G92                                                                                                |
| G93, G94, G95   | Modalità Avanzamento                                                                                                 |
| G96, G97        | Modalità di Controllo del Mandrino, Velocità Superficiale Costante Vs Velocità di Rotazione (==IPM O M/Min Vs RPM==) |
| G98, G99        | Modalità di Ritrazione Z per Ciclo Preimpostato                                                                      |
## Tabella di Riferimento Codici M

| Code      | Description                                                 |
| --------- | ----------------------------------------------------------- |
| M0 M1     | Pausa Programma                                             |
| M2 M30    | Fine Programma                                              |
| M60       | Pausa per Cambio Pallet                                     |
| M3 M4 M5  | Controllo Mandrino                                          |
| M6        | Cambio Utensile                                             |
| M7 M8 M9  | Controllo Refrigerante                                      |
| M19       | Orientamento Mandrino                                       |
| *M40-M45* | *Cambio Gamma* \*                                           |
| M48 M49   | Abilita/Disabilita Sovrascritture di Avanzamento e Mandrino |
| *M50*     | *Controllo Sovrascrittura Avanzamento*                      |
| *M51*     | *Controllo Sovrascrittura Mandrino*                         |
| *M52*     | *Controllo Adattivo di Avanzamento*                         |
| *M53*     | *Controllo Arresto Avanzamento*                             |
| *M61*     | *Imposta Numero Utensile Corrente*                          |
| *M62-M65* | *Controllo Uscita*                                          |
| *M66*     | *Controllo Ingresso*                                        |
| M67       | Controllo Uscita Analogica                                  |
| M68       | Controllo Uscita Analogica                                  |
| M70       | Salva Stato Modale                                          |
| M71       | Annulla Stato Modale Memorizzato                            |
| M72       | Ripristina Stato Modale                                     |
| M73       | Salva Stato Modale di Auto-Ripristino                       |
| M98 M99   | Chiamata e Ritorno dal Sottoprogramma                       |
| M100-M199 | Codici M Definiti dall'Utente                               |
Nota
- I Codici in *Italics* non sono codici Standard ISO ma sono specifici di LinuxCNC
- I Codici con Asterisco \* sono codici comuni ma non presenti in LinuxCNC
## Codici G e Parametri

####  Convenzioni

- Nei prototipi di G-code la parola axes `assi` si riferisce a uno o più degli assi **X**,**Y**,**Z**,**A**,**B**,**C** ed eventualmente **U**,**V**,**W** per i controller che li supportano
- Nei prototipi di G-code, il trattino (`-`) rappresenta un valore reale e (`<>`) indica un elemento opzionale.
- Se in un prototipo viene scritto L-, il trattino verrà spesso indicato come il numero L, e analogamente per qualsiasi altra lettera.
- Un valore opzionale sarà scritto in questo modo: `<L- >.`
- Un valore reale può essere:
	- Un numero esplicito, ad esempio 4
	- Un'espressione, ad esempio \[2+2]
	- Un valore di parametro, ad esempio #88
	- Un valore di funzione unaria, ad esempio acos\[0]
- I numeri degli assi sono riferiti al sistema di coordinate attualmente attivo, a meno che non sia esplicitamente indicato che appartengono al sistema di coordinate assoluto.
- Quando le parole asse sono opzionali, eventuali assi omessi manterranno il loro valore originale.
- Qualsiasi elemento nei prototipi di G-code non espressamente descritto come opzionale è obbligatorio.
- I valori che seguono le lettere sono spesso forniti come numeri espliciti. Salvo diversamente specificato, i numeri espliciti possono essere valori reali. Ad esempio, G10 L2 potrebbe essere altrettanto ben scritto come G\[2*5] L\[1+1]. Se il valore del parametro 100 fosse 2, G10 L#100 significherebbe lo stesso.
- Se in un prototipo viene scritto L-, il trattino verrà spesso indicato come il numero L, e analogamente per qualsiasi altra lettera.
- I commenti nello standard ISO sono racchiusi tra parentesi `(commento)` , in LinuxCNC sono accettati sia parentesi che il punto e virgola `;commento`

**Abbreviazioni**
- CW = ClockWise = Senso Orario
- CCW = CounterClockWise = Senso Antirorario
- CSS = Constant Surface Speed = Velocità Superficiale (o di Taglio) Costante
- TLO = Tool Length Offset = Compensazione Lunghezza Utensile

---
####  G0 Movimento Rapido

```gcode
G0 <axes>
```

Per il movimento rapido. Il **G0** è opzionale se la modalità di movimento corrente è già **G0**. Ciò produrrà un movimento coordinato verso il punto di destinazione alla massima velocità rapida (o a una velocità inferiore). Il **G0** è tipicamente utilizzato come movimento di posizionamento.

**Esempio G0**

```gcode
G90 (imposta la modalità di distanza assoluta)
G0 X1 Y-2.3 (movimento rapido dalla posizione attuale a X1 Y-2.3)
M2 (fine programma)
```
Avvertenza: I movimenti in rapido non sono necessariamente rettilinei (interpolazione lineare), per evitare collisioni eseguire sempre due movimenti, uno in **Z** e uno in **X**/**Y**

---
####  G1 Movimento di Lavoro/Lineare

```gcode
G1 axes
```

Per il movimento lineare (in linea retta) a velocità di avanzamento programmata (sia per lavorazioni di taglio che non), programmare gli assi con **G1**, dove tutte le parole degli assi sono facoltative. Il **G1** è opzionale se la modalità di movimento corrente è già **G1**. Questo comporterà un movimento coordinato verso il punto di destinazione alla velocità di avanzamento corrente (o inferiore).

**Esempio G1**

```gcode
G90 (imposta la modalità di distanza assoluta)
G1 X1.2 Y-3 F10 (movimento lineare con velocità di avanzamento 10 dalla posizione corrente a X1.2 Y-3.)
Z-2.3 (movimento lineare con stesso avanzamento dalla posizione corrente a Z-2.3.)
Z1 F25 (movimento lineare con velocità di avanzamento 25 dalla posizione corrente a Z1)
M2 (fine programma)
```

Se la compensazione utensile è attiva, il movimento differirà da quanto descritto sopra; consultare la sezione [[Compensazione Utensile]] per maggiori informazioni.

Se **G53** è programmato sulla stessa riga, il movimento subirà ulteriori variazioni; consultare la sezione "G53" per ulteriori dettagli.

Il percorso di un movimento rapido **G0** può essere arrotondato nei cambi di direzione e dipende dalle impostazioni di controllo della traiettoria e dall'accelerazione massima degli assi.

Si genera un errore se:
- Una lettera di asse è presente senza un valore reale.
- Viene utilizzata una lettera di asse non configurata.

___
####  G2/G3 Movimento ad Arco

```gcode
G2 or G3 assi offset (formato centro, offset si riferisce ai parametri I-,J-,K-)
G2 or G3 assi R- (formato raggio)
G2 or G3 offset|R- <P-> (cerchi completi)
```

Un arco circolare o elicoidale viene specificato utilizzando **G2** (arco in senso orario) oppure **G3** (arco in senso antiorario) alla velocità di avanzamento corrente. La direzione (CW, CCW) è quella osservata dal lato positivo dell’asse attorno al quale avviene il movimento circolare.

L’asse del cerchio o dell’elica deve essere parallelo all’asse **X**, **Y** o **Z** del sistema di coordinate della macchina. L’asse (o, in modo equivalente, il piano perpendicolare all’asse) viene selezionato con **G17** (asse **Z**, piano **XY**), **G18** (asse **Y**, piano **XZ**) o G19 (asse **X**, piano **YZ**). Se l’arco è circolare, esso giace in un piano parallelo al piano selezionato.

Il centro dell’arco è assoluto o relativo, come impostato rispettivamente da **G90.1** o **G91.1**.

Sono ammessi due formati per specificare un arco: il formato per il centro e il formato per il raggio.

`offset` si riferisce ai parametri **I-**,**J-** e **K-** ovvero la distanza relativa dal punto di inizio dell'arco al centro del cerchio:
- **I** indica l'offset lungo l'asse X.
- **J** indica l'offset lungo l'asse Y.
- **K** indica l'offset lungo l'asse Z.
Questi valori permettono al controllo di calcolare il centro dell'arco per generare la traiettoria circolare o elicoidale. Ad esempio, in un arco nel piano XY (con G17 selezionato) vengono utilizzati solo I e J.

Per programmare un’elica, includere la parola asse perpendicolare al piano dell’arco; ad esempio, se si lavora nel piano **G17**, includere una parola **Z**. In questo modo, l’asse **Z** si muoverà fino al valore programmato durante il movimento circolare in **XY**.

Per programmare un arco che copra più di una rotazione completa, utilizzare la parola **P** specificando il numero di giri completi aggiuntivi oltre all’arco programmato. La parola **P** deve essere un valore intero. Se **P** non viene specificato, il comportamento è come se fosse stato indicato **P1**, ovvero si otterrà solamente una rotazione completa o parziale. Ad esempio, se viene programmato un arco di 180° con **P2**, il movimento risultante sarà di 1 giro e mezzo. Per ogni incremento di P oltre 1, viene aggiunto un giro completo in più all’arco programmato. Gli archi elicoidali a più giri sono supportati e permettono movimenti utili per fresatura di fori o filettature.
######  Archi in Formato Centro

Gli archi in formato centro sono più precisi rispetto agli archi in formato raggio e rappresentano il formato preferito da utilizzare.

```gcode
G17          (seleziona il piano XY)
G91.1        (modalità distanza incrementale per archi (impostazione predefinita))
G0 X0 Y0     (posiziona la testa all'origine)
G2 X20 Y0 I10 J0 F100  (esegue l'arco in senso orario con velocità di avanz. 100)
```

- **Archi parziali (meno di un cerchio completo)**  
    Il punto finale dell'arco, insieme all'offset rispetto al centro dell'arco dalla posizione corrente, viene utilizzato per programmare archi che coprono meno di un cerchio completo. È consentito che il punto finale dell'arco coincida con la posizione corrente.
    
- **Cerchi completi**  
    L'offset dal centro dell'arco rispetto alla posizione corrente ed, opzionalmente, il numero di giri, vengono utilizzati per programmare cerchi completi. (Niente **X,Y,Z**)
    
- **Precisione**  
    Durante la programmazione degli archi, un errore dovuto all'arrotondamento può verificarsi se si utilizza una precisione inferiore a 4 cifre decimali (0.0000) per le misure in pollici e inferiore a 3 cifre decimali (0.000) per i millimetri.
    
######  Modalità Distanza Incrementale per Archi

Gli offset del centro dell'arco sono una distanza relativa dal punto di inizio dell'arco. La Modalità Distanza Incrementale per Archi è impostazione predefinita.

In questa modalità gli offset del centro dell’arco (**I**, **J**) sono specificati in modo incrementale, cioè relativi alla posizione di partenza dell’arco.

Ad esempio, per programmare un arco in senso orario (**G2**) che parte da (0,0), con centro a 10 unità sull’asse **X** (offset I10) e 0 sull’asse **Y** (J0), e con punto finale a (20,0):

```gcode
G17          (seleziona il piano XY)
G91.1        (modalità distanza incrementale per archi (impostazione predefinita))
G0 X0 Y0     (posiziona la testa all'origine)
G2 X20 Y0 I10 J0 F100  (esegue l'arco in senso orario con velocità di avanz. 100)
```
- **Archi parziali (meno di 360°)**  
    Devono essere programmati una o più parole asse e uno o più offset.
    
- **Cerchi completi**  
    Non devono essere programmate parole asse; devono essere forniti uno o più offset. La parola P assume per impostazione predefinita il valore 1 ed è facoltativa.
    

Per ulteriori informazioni sulla "Modalità Distanza Incrementale per Archi", consultare la sezione **G91.1**.
######  Modalità Distanza Assoluta per Archi

Gli offset del centro dell'arco rappresentano la distanza assoluta dalla posizione zero corrente dell'asse.

In questa modalità gli offset del centro (**I**, **J**) sono interpretati come distanze assolute rispetto alla posizione zero corrente degli assi. Per ottenere lo stesso arco descritto sopra, è necessario impostare la modalità con **G90.1**.

```gcode
G17          (seleziona il piano XY)
G90          (modalità assoluta per i movimenti)
G90.1        (modalità distanza assoluta per archi)
G0 X0 Y0     (posiziona la testa all'origine (0,0))
G2 X20 Y0 I10 J0 F100  (esegue l'arco in senso orario: qui il centro è a (10,0) in coordinate assolute)
```

- **Archi parziali (meno di 360°)**  
    Devono essere programmati una o più parole asse e entrambi gli offset.
    
- **Cerchi completi**  
    Non devono essere programmate parole asse; devono essere forniti entrambi gli offset. La parola P assume per impostazione predefinita il valore 1 ed è facoltativa.
    

Per ulteriori informazioni sulla "Modalità Distanza Assoluta per Archi", consultare la sezione **G90.1**.
######  Specifiche per Piano

**Piano XY (G17)**

```
G2 o G3 <X- Y- Z- I- J- P->
```

- **Z** - elica
- **I** - offset X
- **J** - offset Y
- **P** - numero di giri

**Piano XZ (G18)**

```
G2 o G3 <X- Z- Y- I- K- P->
```

- **Y** - elica
- **I** - offset X
- **K** - offset Z
- **P** - numero di giri

**Piano YZ (G19)**

```
G2 o G3 <Y- Z- X- J- K- P->
```

- **X** - elica
- **J** - offset Y
- **K** - offset Z
- **P** - numero di giri

######  Esempio Arco Formato Centro

**Esempio G2**

```gcode
G0 X0 Y0
G2 X1 Y1 I1 F10 (arco in senso orario nel piano XY)
```

![[g2_en.svg]]

**Esempio G2/G3**

```gcode
G0 X0 Y0
G2 X0 Y1 I1 J0.5 F25 (arco in senso orario nel piano XY)
G3 X0 Y0 I1 J-0.5 F25 (arco in senso antiorario nel piano XY)
```

![[g2-3_en.svg]]

**Esempio Elicoidale**

```gcode
G0 X0 Y0 Z0
G17 G2 X10 Y16 I3 J4 Z-1 (arco elicoidale con aggiunta di Z)
```

**Esempio Giri Multipli (parametro P)**

```gcode
G0 X0 Y0 Z0
G2 X0 Y1 Z-1 I1 J0.5 P2 F25 (arco elicoidale con due giri)
```

#####  Archi in Formato Raggio

```
G2 <coordinate punto finale arco> R- <P->
```

- **R** – raggio dalla posizione corrente

Non è una buona prassi programmare archi in formato raggio che siano quasi cerchi completi o quasi semicerchi, poiché una piccola variazione nella posizione del punto finale comporta una variazione molto maggiore nella posizione del centro del cerchio (e, di conseguenza, nella parte centrale dell'arco). L'effetto di ingrandimento è tale che un errore di arrotondamento su un numero può generare lavorazioni fuori tolleranza. Altri archi (nell'intervallo da molto piccoli fino a 165° oppure da 195° a 345°) sono accettabili.

Nel formato raggio, le coordinate del punto finale dell'arco nel piano selezionato sono specificate assieme al raggio dell'arco. Si programma con **G2** (oppure si usa **G3** al posto di **G2**) e la parola **R** rappresenta il raggio. Le parole asse sono tutte facoltative, ad eccezione del fatto che almeno una delle due parole relative agli assi nel piano selezionato deve essere utilizzata. Il valore numerico associato a **R** indica il raggio: un raggio positivo indica che l'arco copre un angolo inferiore a 180°, mentre un raggio negativo indica una rotazione superiore a 180°. Se l'arco è elicoidale, viene specificato anche il valore del punto finale dell'arco sull'asse di coordinate parallelo all'asse dell'elica.

**Esempio G2

```gcode
G17 G2 X10 Y15 R20 Z5
```

L'esempio sopra esegue un arco circolare o elicoidale in senso orario (come visto dall'asse Z positivo) il cui asse è parallelo all'asse Z, terminando dove X=10, Y=15 e Z=5, con un raggio di 20. Se il valore iniziale di Z è 5, l'arco appartiene a un cerchio parallelo al piano XY; altrimenti, si tratta di un arco elicoidale.

##### Formule di Trasformazione Formato Arco/Formato Centro

$X_c = \frac{X_0 + X_1}{2} \pm h \cdot \frac{(Y_1 - Y_0)}{d}​$

$Y_c = \frac{Y_0 + Y_1}{2} \pm h \cdot \frac{(X_1 - X_0)}{d}​$

dove:

- $X_0, Y_0$ sono le coordinate del punto di partenza,
- $X_1, Y_1$ quelle del punto finale,
- $d = \sqrt{(X_1-X_0)^2+(Y_1-Y_0)^2}$ è la lunghezza della corda,
- $h = \sqrt{R^2 - \left(\frac{d}{2}\right)^2}​$ è l'altezza (ovvero la distanza perpendicolare dal punto medio della corda al centro del cerchio),
- Il segno ± va scelto in funzione del lato della corda su cui si trova il centro, determinando così il senso di rotazione (CW o CCW).
- Scegli il segno positivo o negativo in modo che il centro $C$ si trovi nel lato desiderato della corda per ottenere il verso corretto dell’arco. (Stesso segno per $X_c$ e $Y_c$ )

Gli offset sono la differenza tra il centro $C$ e il punto di partenza $P_0$​:

$I = X_c - X_0​$ 
$J = Y_c - Y_0​$

---
####  G4 Pausa

```gcode
G4 P-
```  

**P** - tempo di pausa in secondi (numero in virgola mobile)

Il valore **P** rappresenta il tempo, in secondi, durante il quale tutti gli assi della macchina resteranno fermi. Il valore di **P** è un numero in virgola mobile, quindi è possibile specificare frazioni di secondo.

**G4** non influisce sul mandrino, sul refrigerante o su eventuali ingressi/uscite (I/O).

---
####  G7 Modalità Diametro Tornio

```gcode
G7
```

Il comando **G7** imposta la modalità diametro per l'asse **X** su un tornio. In questa modalità, gli spostamenti dell'asse **X** sono calcolati in riferimento al diametro del pezzo, quindi ogni movimento corrisponde alla metà della distanza dal centro del tornio.

**Esempio**  
Un comando **X1** posizionerà l'utensile a 0.500" dal centro del tornio, ottenendo un pezzo con 1" di diametro.

---
#### G8 Modalità Raggio Tornio

```gcode
G8
```  

Il comando **G8** imposta la modalità raggio per l'asse **X** su un tornio. In questa modalità, gli spostamenti dell'asse **X** sono calcolati come distanza diretta dal centro del tornio.

**Esempio**  
Un comando **X1** posizionerà l'utensile a 1" dal centro, ottenendo un pezzo con 2" di diametro.

La modalità **G8** (raggio) è quella predefinita all'accensione della macchina.

---
#### G10 Modifica Dati Programmabili

Il comando **G10** permette di impostare, aggiornare o ricaricare dati preimpostati, come gli offset degli utensili e le tabelle degli utensili, nonché gli offset dei sistemi di coordinate. 

##### G10 L0 Ricarica Dati Tabella Utensili

```gcode
G10 L0
```

**G10 L0** ricarica tutti i dati della tabella utensili. È richiesto che non sia caricato alcun utensile nel mandrino. I parametri vengono aggiornati immediatamente e qualsiasi diametro utensile modificato sarà utilizzato per i successivi comandi di compensazione del raggio utensile **G41**, **G42**. I valori esistenti della compensazione della lunghezza utensile **G43** rimarranno in vigore fino a quando non verranno aggiornati da nuovi comandi **G43**.

##### G10 L1 Imposta Tabella Utensili

```gcode
G10 L1 P- assi <R- I- J- Q->
```

- **P** - numero utensile
- **R** - raggio utensile
- **I** - angolo frontale (tornio)
- **J** - angolo posteriore (tornio)
- **Q** - orientamento (tornio)

**G10 L1** imposta la tabella utensili per il numero utensile **P** con i valori specificati nei parametri. Un comando **G10 L1** valido sovrascrive e ricarica la tabella utensili per l'utensile specificato. Il comando non è valido se la compensazione utensile **G41/G42** è attiva.

**Esempio G10 L1:**

```gcode
G10 L1 P1 Z1.5  (imposta l’offset Z dell’utensile 1 a 1.5 rispetto all'origine macchina)  
G10 L1 P2 R0.015 Q3  (esempio per tornio: imposta il raggio dell’utensile 2 a 0.015 e l’orientamento a 3)  
```

Si genera un errore se:
-  La compensazione dell'utensile è attiva.

Per ulteriori informazioni sull'orientamento dell'utensile utilizzato dalla parola **Q**, consulta il diagramma dell'[[Orientamento Utensile]] del tornio.

##### G10 L2 Imposta Sistema di Coordinate

```gcode
G10 L2 P- <assi R->
```

- **P** - sistema di coordinate da modificare (da 0 a 9)
- **R** - rotazione attorno all’asse **Z**

Il comando **G10 L2** imposta l’origine degli assi nel sistema di coordinate specificato **P** ai valori definiti nelle parole asse. L’offset è calcolato rispetto all’origine macchina stabilita durante l’operazione di homing.

L’offset impostato sostituirà qualsiasi altro offset attivo per il sistema di coordinate selezionato. Le coordinate non specificate non verranno modificate.

Per selezionare il sistema di coordinate da modificare, specificare un valore **P** compreso tra **0 e 9**.

| Valore P | Sistema di Coordinate | G-code |
| :------: | :-------------------: | :----: |
|    0     |        Attivo         |  n/a   |
|    1     |           1           |  G54   |
|    2     |           2           |  G55   |
|    3     |           3           |  G56   |
|    4     |           4           |  G57   |
|    5     |           5           |  G58   |
|    6     |           6           |  G59   |
|    7     |           7           | G59.1  |
|    8     |           8           | G59.2  |
|    9     |           9           | G59.3  |
Facoltativamente, programma R per indicare la rotazione dell'asse **XY** attorno all'asse **Z**. La direzione di rotazione è in senso antiorario (CCW) vista dall'estremità positiva dell'asse **Z**.

Tutte le parole asse sono facoltative.

Essere in modalità di distanza incrementale (**G91**) non ha effetto su **G10 L2**.

- **G10 L2 P-** non cambia dal sistema di coordinate attuale a quello specificato da **P**, è necessario usare **G54-59.3** per selezionare un sistema di coordinate.
    
- Quando una rotazione è in atto, spostare un asse muoverà solo quell'asse in direzione positiva o negativa, e non lungo l'asse ruotato.
    
- Se un offset locale **G52** o un offset origine **G92** erano attivi prima di **G10 L2**, continueranno a essere attivi anche dopo **G10 L2**.
    
- Quando si programma un sistema di coordinate con **R**, qualsiasi **G52** o **G92** verrà applicato dopo la rotazione.
    
- Il sistema di coordinate il cui l'origine è impostata dal comando **G10** può essere attivo o inattivo al momento dell'esecuzione del **G10**. Se è attualmente attivo, le nuove coordinate entreranno in vigore immediatamente.

**Esempio: G10 L2:**

```gcode
G10 L2 P1 X3.5 Y17.2
```

Nell'esempio sopra, l'origine del primo sistema di coordinate (quello selezionato da **G54**) è impostata su **X**=3.5 e **Y**=17.2. Poiché vengono specificati solo **X** e **Y**, il punto di origine viene spostato solo lungo gli assi **X** e **Y**; gli altri coordinate non vengono modificate.

```gcode
G10 L2 P1 X0 Y0 Z0 (azzeramento degli Offset per gli Assi X, Y e Z nel Sistema di Coordinate 1)
```

L'esempio sopra imposta le coordinate **XYZ** del sistema di coordinate 1 sull'origine della macchina.

Il sistema di coordinate è descritto nella sezione [[Sistema di Coordinate]].

##### G10 L10 Imposta Tabella Utensili

```gcode
G10 L10 P- assi <R- I- J- Q->
```

- **P** - numero utensile
- **R** - raggio utensile
- **I** - angolo anteriore (tornio)
- **J** - angolo posteriore (tornio)
- **Q** - orientamento (tornio)

**Esempio G10 L10:

```gcode
T1 M6 G43 (carica l'utensile 1 e gli offset di lunghezza utensile)  
G10 L10 P1 Z1.5 (imposta la posizione attuale per Z a 1.5)  
G43 (ricarica gli offset di lunghezza utensile dalla tabella utensili modificata)  
M2 (fine programma)
```

Per maggiori informazioni, consulta le sezioni **T** & **M6**, e **G43**/**G43.1**.

Si genera un errore se:
- La compensazione utensile è attiva

##### G10 L11 Imposta Tabella Utensili

```gcode
G10 L11 P- assi <R- I- J- Q->
```

- **P** - numero utensile
- **R** - raggio utensile
- **I** - angolo anteriore (tornio)
- **J** - angolo posteriore (tornio)
- **Q** - orientamento (tornio)

**G10 L11** è simile a **G10 L10**, tranne che invece di impostare l'entrata in base agli offset correnti, viene impostato in modo che le coordinate correnti diventino i valori forniti se il nuovo offset utensile viene ricaricato e la macchina viene posizionata nel sistema di coordinate **G59.3** senza alcun offset **G52/G92** attivo.

Questo consente all'utente di impostare il sistema di coordinate G59.3 in base a un punto fisso sulla macchina, e quindi utilizzare quella configurazione per misurare gli utensili senza dover tenere conto di altri offset attivi al momento.

##### G10 L20 Imposta Sistema di Coordinate

```gcode
G10 L20 P- assi
```

- **P** - sistema di coordinate (0-9)

**G10 L20** è simile a **G10 L2**, tranne che invece di impostare l'offset/entrata al valore dato, viene impostato a un valore calcolato che fa sì che le coordinate correnti diventino il valore fornito.

**Esempio G10 L20:**
```gcode
G10 L20 P1 X1.5 (imposta la posizione attuale dell'asse X nel sistema di coordinate 1 a 1.5)
```

---
#### G17 - G19.1 Selezione del Piano

Questi codici impostano il piano corrente come segue:

- **G17** - **XY** (predefinito)  
- **G18** - **ZX**  
- **G19** - **YZ**  
- **G17.1** - **UV**  
- **G18.1** - **WU**  
- **G19.1** - **VW**

I piani **UV**, **WU** e **VW** non supportano gli archi.

È una buona pratica includere una selezione del piano nel preambolo di ogni file G-code.

Gli effetti della selezione di un piano sono trattati nelle sezioni **G2 G3** Archi e **G81 G89**.

---
#### G20, G21 Unità

- **G20** - per usare pollici come unità di misura della lunghezza.
- **G21** - per usare millimetri come unità di misura della lunghezza.

È una buona pratica includere le unità nel preambolo di ogni file G-code.

---
#### G28, G28.1 Vai/Imposta Posizione Predefinita

*Avvertenza:*
*Utilizzare G28 solo quando la macchina ha eseguito l'homing in una posizione ripetibile e la posizione desiderata per G28 è stata memorizzata con G28.1.*

**G28** utilizza i valori memorizzati nei parametri 5161-5169 come punto finale (per **X, Y, Z, A, B, C, U, V, W**) verso il quale muoversi. I valori dei parametri sono coordinate assolute della macchina nelle unità native specificate nel file INI. Tutti gli assi definiti nel file INI verranno spostati quando viene emesso un comando **G28**. Se non sono state memorizzate posizioni con **G28.1**, allora tutti gli assi torneranno all'origine macchina.
- `G28` – Effettua un movimento rapido dalla posizione corrente alla posizione assoluta indicata dai valori nei parametri 5161-5166.
- `G28 assi` – Effettua un movimento rapido verso la posizione specificata dalle parole asse (inclusi eventuali offset), quindi esegue un movimento rapido verso la posizione assoluta indicata dai valori nei parametri 5161-5166 per tutti gli assi specificati. Qualsiasi asse non specificato non si muoverà.
- `G28.1` – Memorizza la posizione assoluta corrente nei parametri 5161-5166.

**Esempio G28:**

```gcode
G28 Z2.5 (movimento rapido fino a Z2.5, poi al valore Z specificato in #5163)
```

Si genera un errore se:
- La compensazione utensile è attiva

---

#### G30, G30.1 Vai/Imposta Posizione Predefinita  

*Avvertenza:*  
*Utilizzare G30 solo quando la macchina ha eseguito l'homing in una posizione ripetibile e la posizione desiderata per G30 è stata memorizzata con G30.1.*  

**G30** funziona in modo analogo a **G28**, ma utilizza i valori memorizzati nei parametri 5181-5189 come punto finale (per **X, Y, Z, A, B, C, U, V, W**) verso il quale muoversi. I valori dei parametri sono coordinate assolute della macchina nelle unità native specificate nel file INI. Tutti gli assi definiti nel file INI verranno spostati quando viene emesso un comando **G30**. Se non sono state memorizzate posizioni con **G30.1**, allora tutti gli assi torneranno all'origine macchina.

- `G30` – Effettua un movimento rapido dalla posizione corrente alla posizione assoluta indicata dai valori nei parametri 5181-5189.
- `G30` assi – Effettua un movimento rapido verso la posizione specificata dalle parole asse (inclusi eventuali offset), quindi esegue un movimento rapido verso la posizione assoluta indicata dai valori nei parametri 5181-5189 per tutti gli assi specificati. Qualsiasi asse non specificato non si muoverà.
- `G30.1` – Memorizza la posizione assoluta corrente nei parametri 5181-5186.

**Esempio G30:** 

```gcode
G30 Z2.5 (movimento rapido fino a Z2.5, poi al valore Z specificato in #5183)  
```

Si genera un errore se:
- la compensazione utensile è attiva

---
#### G33 Movimento Sincronizzato del Mandrino  

```gcode
G33 X– Y– Z– K– $–  
```

- **K** – distanza per rivoluzione
- **$** – selettore opzionale del mandrino

Per un movimento sincronizzato con il mandrino in una direzione, si utilizza il codice **G33 X– Y– Z– K–**, dove **K** indica la distanza percorsa negli assi **XYZ** per ogni rivoluzione del mandrino. Ad esempio, se si parte da Z=0, `G33 Z–1 K0.0625` produce un movimento di 1 pollice lungo **Z** in 16 rivoluzioni del mandrino. Questo comando potrebbe far parte di un programma per realizzare una filettatura a 16 TPI. Un altro esempio in sistema metrico: `G33 Z–15 K1.5` produce uno spostamento di 15 mm mentre il mandrino compie 10 rivoluzioni, per una filettatura di 1,5 mm.

L'argomento opzionale **$** imposta a quale mandrino il movimento è sincronizzato (il valore predefinito è zero).

Il movimento sincronizzato con il mandrino attende il segnale di indice del mandrino e i pin che indicano il raggiungimento della velocità, in modo che più passate si allineino. **G33** termina il movimento nel punto finale programmato. **G33** può essere utilizzato per tagliare filettature coniche o per realizzare una fusee.

*Nota:*
*L'indice del mandrino è un segnale di riferimento, generalmente generato da un sensore, che si attiva una volta per ogni rivoluzione del mandrino per indicare una posizione fissa (solitamente l'inizio o una posizione prestabilita della rotazione).*

Tutte le parole asse sono facoltative, a condizione che venga utilizzata almeno una.

*Nota*  
*K segue la linea di movimento definita da X– Y– Z–. K non è parallelo all'asse Z se vengono utilizzati endpoint X o Y, ad esempio durante la lavorazione di filettature coniche.*

**Esempio G33:**  

```gcode
G90 (modalità di distanza assoluta)  
G0 X1 Z0.1 (movimento rapido alla posizione)  
S100 M3 (avvia la rotazione del mandrino)  
G33 Z–2 K0.125 (muove l'asse Z fino a –2 a una velocità pari a 0.125 per rivoluzione)  
G0 X1.25 (movimento rapido per allontanare l'utensile dal pezzo)  
Z0.1 (movimento rapido alla posizione Z iniziale)  
M2 (fine programma)  
```

Consultare le sezioni relative a **G90**, **G0** e **M2** per ulteriori informazioni.

---
#### G33.1 Filettatura Rigida

```gcode
G33.1 X– Y– Z– K– I– $–  
```

- **K** – distanza per rivoluzione
- **I** – moltiplicatore opzionale della velocità del mandrino per un ritorno più rapido
- **$** – selettore opzionale del mandrino

*Avvertenza:*  
*Per una filettatura solo sull'asse Z, è necessario preimpostare la posizione XY prima di richiamare G33.1 e utilizzare esclusivamente una parola Z nel comando G33.1. Se le coordinate specificate non corrispondono a quelle correnti al momento del richiamo di G33.1 per la filettatura, il movimento non avverrà lungo l'asse Z, bensì sarà un movimento coordinato, sincronizzato con il mandrino, dalla posizione corrente a quella specificata e ritorno.*  
*Per la filettatura rigida (movimento sincronizzato con il mandrino con ritorno), utilizzare il codice G33.1 X– Y– Z– K–, dove K indica la distanza percorsa per ogni rivoluzione del mandrino.*

**Un movimento di filettatura rigida consiste nella seguente sequenza:**

- Un movimento dalla coordinata corrente alla coordinata specificata, sincronizzato con il mandrino selezionato al rapporto indicato, a partire dalla posizione corrente con un impulso di indice del mandrino.
- Al raggiungimento del punto finale, viene emesso un comando per invertire il senso di rotazione del mandrino e accelerarlo di un fattore definito dal moltiplicatore (ad es., da senso orario a senso antiorario).
- Proseguimento del movimento sincronizzato oltre la coordinata finale specificata fino a quando il mandrino non si ferma effettivamente e inverte il senso.
- Movimento sincronizzato di ritorno alla coordinata originale.
- Al raggiungimento della coordinata originale, viene emesso un comando per invertire nuovamente il mandrino (ad es., da senso antiorario a senso orario).
- Proseguimento del movimento sincronizzato oltre la coordinata originale fino a quando il mandrino non si ferma effettivamente e inverte il senso.
- Un movimento ***non sincronizzato*** di ritorno alla coordinata originale.

I movimenti sincronizzati con il mandrino attendono l'indice del mandrino, in modo che più passate si allineino. I movimenti **G33.1** terminano alla coordinata originale.

Tutte le parole asse sono opzionali, purché ne venga specificata almeno una.

**Esempio G33.1** 

```gcode
G90 (imposta modalità assoluta)  
G0 X1.000 Y1.000 Z0.100 (movimento rapido alla posizione di partenza)  
S100 M3 (avvia il mandrino, 100 RPM)  
G33.1 Z–0.750 K0.05 (filettatura rigida: filettatura a 20 TPI, profondità 0,750)  
M2 (fine programma)  
``` 

Consultare le sezioni **G90**, **G0** e **M2** per ulteriori informazioni.

---
####  G38.n Probing/Sondaggio Lineare

```gcode
G38.n assi
```

- **G38.2** - la sonda si muove verso il pezzo, si ferma al contatto, genera un errore se fallisce
- **G38.3** - la sonda si muove verso il pezzo, si ferma al contatto
- **G38.4** - la sonda si allontana dal pezzo, si ferma alla perdita di contatto, genera un errore se fallisce
- **G38.5** - la sonda si allontana dal pezzo, si ferma alla perdita di contatto

Eseguire `G38.n assi` per effettuare un’operazione di probing lineare. Le parole asse sono opzionali, ma almeno una deve essere usata. Le parole asse definiscono il punto di destinazione verso cui la sonda si muoverà, partendo dalla posizione attuale. Se la sonda non viene attivata prima di raggiungere la destinazione, **G38.2** e **G38.4** generano un errore.

L'utensile nel mandrino deve essere una sonda o un interruttore a contatto.

In risposta a questo comando, la macchina sposta il punto controllato (che dovrebbe essere al centro della sfera della sonda) in **linea retta** alla velocità di avanzamento corrente verso il punto programmato.

- Se la modalità di avanzamento a tempo inverso è attiva, il feed rate sarà impostato in modo che l'intero movimento dal punto attuale al punto programmato avvenga nel tempo specificato.
- Il movimento si ferma (nei limiti di accelerazione della macchina) quando viene raggiunto il punto programmato o quando il cambiamento richiesto nello stato della sonda si verifica, a seconda di quale evento accade per primo.

| **Codice** | **Stato Target** | **Orientamento Movimento** | **Segnale di Errore** |
| ---------- | ---------------- | -------------------------- | --------------------- |
| **G38.2**  | Contattato       | Verso il pezzo             | Sì                    |
| **G38.3**  | Contattato       | Verso il pezzo             | No                    |
| **G38.4**  | Non contattato   | Lontano dal pezzo          | Sì                    |
| **G38.5**  | Non contattato   | Lontano dal pezzo          | No                    |

**Esempio G38**

Questo esempio esegue una misura dell'altezza utensile con conversione delle coordinate locali in coordinate macchina. L'offset altezza utensile viene aggiornato nella tabella utensili.

```gcode
G49                  (Disattiva compensazione altezza utensile)
G38.2 Z-100 F100     (Muove la sonda in Z fino al contatto con il pezzo)
#<zworkoffset> = [#[5203 + #5220 * 20] + #5213 * #5210]  (Calcola l'offset altezza utensile)
G10 L1 P#5400 Z#<zworkoffset>  (Memorizza il nuovo offset utensile)
G43                  (Riattiva compensazione altezza utensile)
```

Si genera un errore se:
- Il punto di partenza è identico a quello di destinazione.
- Non viene specificato alcun asse.
- La compensazione del raggio utensile è attivata.
- L'avanzamento è impostato a zero.
- La sonda è già nello stato target.

---
####  G40 Disattivazione della Compensazione

**G40** - disattiva la compensazione dell'utensile. Se la compensazione dell'utensile era attiva, il movimento successivo deve essere un movimento lineare e più lungo del diametro dell'utensile. È possibile disattivare la compensazione anche quando è già disattivata.

 **Esempio di G40**

```gcode
; la posizione attuale è X1 dopo aver completato un movimento con compensazione utensile  
G40 (disattiva la compensazione)  
G0 X1.6 (movimento lineare più lungo del diametro dell'utensile attuale)  
M2 (fine programma)  
```

Vedere le sezioni **G0 & M2** per maggiori informazioni.

 Si genera un errore se:
- Un movimento ad arco **G2/G3** è programmato immediatamente dopo un **G40**.
- Il movimento lineare dopo la disattivazione della compensazione è inferiore al diametro dell'utensile.

---
####  G41, G42 Compensazione Utensile

```gcode
G41 (compensazione a sinistra del percorso programmato)  
G42 (compensazione a destra del percorso programmato)
```

- **D** - numero utensile

Il valore **D** è opzionale; se non specificato, verrà utilizzato il raggio dell'utensile attualmente caricato (se nessun utensile è caricato e non viene fornito un valore D, verrà utilizzato un raggio di 0).

Se fornito, il valore **D** rappresenta il numero dell'utensile da utilizzare. Normalmente, questo sarebbe il numero dell'utensile nel mandrino (nel qual caso il valore D è ridondante e non necessario), ma può essere qualsiasi numero utensile valido.

 *Nota*:
- *G41/G42 D0 ha un comportamento speciale. Il suo funzionamento è differente tra macchine con cambio utensile casuale e senza cambio utensile casuale (vedi sezione Cambio Utensile).*
- *Sulle macchine senza cambio utensile casuale, **G41/G42 D0** applica la Compensazione Lunghezza Utensile (TLO) dell'utensile attualmente nel mandrino, o un TLO di 0 se nessun utensile è nel mandrino.
- *Sulle macchine con cambio utensile casuale, **G41/G42 D0** applica il TLO dell'utensile **T0** definito nella tabella utensili, oppure genera un errore se **T0** non è definito.*

Per attivare la compensazione utensile a sinistra del profilo del pezzo, utilizzare **G41**.
- G41 attiva la compensazione a sinistra della linea programmata, vista dall'estremità positiva dell'asse perpendicolare al piano.
- 
Per attivare la compensazione utensile a destra del profilo del pezzo, utilizzare **G42**.
- G42 attiva la compensazione a destra della linea programmata, vista dall'estremità positiva dell'asse perpendicolare al piano.

Il movimento di ingresso deve essere almeno lungo quanto il raggio dell'utensile. Il movimento di ingresso può essere un movimento rapido.

La compensazione utensile può essere eseguita se il piano **XY** o **XZ** è attivo.

I comandi **M100-M199** sono consentiti quando la compensazione utensile è attiva.

Il comportamento del centro di lavoro quando la compensazione utensile è attiva è descritto nella sezione[ Compensazione Utensile](), insieme ad esempi di codice.

 Si genera un errore se:
- Il numero **D** non è un numero utensile valido o è 0.
- Il piano **YZ** è attivo.
- La compensazione utensile è già attiva e viene richiesto di attivarla nuovamente.

---
####  G41.1, G42.1 Compensazione Utensile Dinamica

```gcode
G41.1 D- (compensazione a sinistra del percorso programmato)  
G42.1 D- (compensazione a destra del percorso programmato)
```

- **D** - diametro utensile
- **L** - orientamento utensile (vedi orientamento utensili tornio)

I codici **G41.1** e **G42.1** funzionano allo stesso modo di **G41** e **G42**, con l'ulteriore possibilità di programmare direttamente il diametro dell'utensile.

Il valore **L** predefinito è 0 se non specificato.

 Si genera un errore se:
- Il piano **YZ** è attivo.
- Il numero **L** non è compreso tra 0 e 9 (inclusi).
- Il numero **L** viene utilizzato quando il piano **XZ** non è attivo.
- La compensazione utensile è già attiva e viene richiesto di attivarla nuovamente.

---
#### G43 Compensazione Lunghezza Utensile  

```gcode
G43 <H->
```

- **H** - numero utensile (opzionale)
- **G43** abilita la compensazione della lunghezza utensile. **G43** modifica i movimenti successivi compensando le coordinate degli assi con la lunghezza dell'offset. **G43** non provoca alcun movimento. Alla successiva movimentazione di un asse compensato, il punto finale sarà la posizione compensata.

**G43** senza un valore **H** utilizza l'utensile attualmente caricato dall'ultimo **Tn M6**.

**G43** **Hn** utilizza l'offset per l'utensile **n**.

*Nota*: 
***G43 H0** ha un comportamento particolare. Il suo funzionamento differisce tra le macchine con cambio utensile random e quelle con cambio utensile non random (vedi la sezione Tool Changers). Sulle macchine con cambio utensile non random, **G43 H0** applica la compensazione della lunghezza dell'utensile attualmente nel mandrino, oppure una compensazione di 0 se nessun utensile è presente. Sulle macchine con cambio utensile random, **G43 H0** applica la compensazione della lunghezza dell'utensile **T0** definito nella tabella utensili (o genera un errore se **T0** non è definito).*

**Esempio G43 H-**

```gcode
G43 H1 (applica la compensazione dell'utensile 1 dalla tabella utensili)
```

Si genera un errore se:
- il numero **H** non è un intero
- il numero **H** è negativo
- il numero **H** non è un numero utensile valido (nota che **0** è valido sulle macchine con cambio utensile non random e indica "l'utensile attualmente nel mandrino")

---
####  G43.1 Compensazione Dinamica della Lunghezza Utensile  

```gcode
G43.1 assi
```


**G43.1** assi modifica i movimenti successivi sostituendo l'offset attuale degli assi. **G43**.1 non provoca alcun movimento. Alla successiva movimentazione di un asse compensato, il punto finale sarà la posizione compensata.

**Esempio G43.1**

```gcode
G90 (imposta la modalità assoluta)
T1 M6 G43 (carica l'utensile 1 e le compensazioni di lunghezza, Z è a 0 macchina e il DRO mostra Z1.500)
G43.1 Z0.250 (compensa l'offset dell'utensile attuale di 0.250, il DRO ora mostra Z1.250)
M2 (fine programma)
```

Vedi le sezioni **G90**, **T** e **M6** per maggiori informazioni.

Si genera un errore se:
- viene comandato un movimento sulla stessa riga di **G43.1**

*Nota*:  
*G43.1 non scrive nella tabella utensili.*

---
#### G43.2 Applica Compensazione Aggiuntiva della Lunghezza Utensile

```gcode
G43.2 H- assi- 
```

- **H** - numero utensile
- **G43**.**2** applica un offset utensile aggiuntivo simultaneo.

**Esempio G43.2**

```gcode
G90 (imposta la modalità assoluta)
T1 M6 (carica l'utensile 1)
G43 (o G43 H1 - sostituisce tutti gli offset con quello dell'utensile T1)
G43.2 H10 (aggiunge anche l'offset dell'utensile T10)
M2 (fine programma)
```

Puoi sommare un numero arbitrario di offset chiamando G43.2 più volte. Non ci sono assunzioni predefinite su quali numeri siano offset di geometria e quali siano offset di usura, né sull'obbligo di avere un solo offset per ciascun tipo.

Come gli altri comandi **G43**, **G43.2** non provoca alcun movimento. La prossima volta che un asse compensato viene mosso, il punto finale sarà la posizione compensata.

Si genera un errore se:
- Il parametro H non è specificato e non sono indicati offset per gli assi.
- Il parametro H è specificato, ma il numero utensile indicato non esiste nella tabella utensili.
- Il parametro H è specificato e vengono anche specificati degli assi.

*Nota*  
*G43.2 non scrive nella tabella utensili.*

---
#### G49 Annulla la Compensazione della Lunghezza Utensile 

```gcode
G49
```

- **G49** - annulla la compensazione della lunghezza utensile

È consentito programmare utilizzando lo stesso offset già in uso. È inoltre consentito programmare senza offset di lunghezza utensile se al momento non se ne sta utilizzando alcuno.

---
#### G52 Offset del Sistema di Coordinate Locale

```gcode
G52 assi
```

**G52** viene utilizzato in un programma di lavorazione come un "offset temporaneo del sistema di coordinate locale" all'interno del sistema di coordinate del pezzo. Maggiori informazioni su G52 sono nella sezione [[Offset Locali e Globali.]]

---
#### G53 Movimento in Coordinate Macchina 

```gcode
G53 assi
```

Per muoversi nel sistema di coordinate macchina, programmare **G53** sulla stessa riga di un movimento lineare. **G53** non è modale e deve essere programmato in ogni riga. Non è necessario programmare **G0** o **G1** sulla stessa riga se uno di essi è già attivo.

Ad esempio, **G53** **G0** **X0** **Y0** **Z0** muoverà gli assi verso la posizione di home anche se il sistema di coordinate attualmente selezionato ha degli offset in vigore.

**Esempio G53** 

```gcode
G53 G0 X0 Y0 Z0 (movimento lineare rapido verso l'origine macchina)
G53 X2 (movimento lineare rapido verso la coordinata assoluta X2)
```

Vedere la sezione **G0** per maggiori informazioni.

Si genera un errore se:  
- **G53** viene utilizzato senza che **G0** o **G1** siano attivi,  
- oppure se **G53** viene utilizzato mentre la compensazione utensile è attiva.

---
####  G54-G59.3 Selezione del Sistema di Coordinate 

- **G54** - seleziona il sistema di coordinate 1  
- **G55** - seleziona il sistema di coordinate 2  
- **G56** - seleziona il sistema di coordinate 3  
- **G57** - seleziona il sistema di coordinate 4  
- **G58** - seleziona il sistema di coordinate 5  
- **G59** - seleziona il sistema di coordinate 6  
- **G59.1** - seleziona il sistema di coordinate 7  
- **G59.2** - seleziona il sistema di coordinate 8  
- **G59.3** - seleziona il sistema di coordinate 9

Si genera un errore se:  
- si seleziona un sistema di coordinate mentre la compensazione utensile è attiva.
- Vedere la sezione [Sistema di Coordinate]() per una panoramica dei sistemi di coordinate.

---
#### G61 Modalità Percorso Esatto

**G61** - modalità percorso esatto, movimento esattamente come programmato. I movimenti rallenteranno o si fermeranno se necessario per raggiungere ogni punto programmato. Se due movimenti sequenziali sono esattamente collineari, il movimento non si fermerà.

---
#### G61.1 Modalità Arresto Esatto

**G61.1** - modalità arresto esatto, il movimento si fermerà alla fine di ogni segmento programmato.

---
#### G64 Fusione del Movimento - Path Blending

```gcode
G64 <P- <Q->>
```

- **P** - tolleranza di fusione del movimento
- **Q** - tolleranza naive cam
- **G64** - velocità migliore possibile. Senza P significa mantenere la velocità migliore possibile, indipendentemente da quanto ci si discosti dal punto programmato.
- **G64** **P-** - fusione tra velocità ottimale e tolleranza di deviazione
- **G64 P-**  **\<Q->** -blending con tolleranza. È un modo per mettere a punto il sistema per il miglior compromesso tra velocità e precisione. La tolleranza P- significa che il percorso effettivo non sarà mai più distante di P- dal punto finale programmato. La velocità verrà ridotta se necessario per mantenere il percorso. Se si imposta Q a un valore diverso da zero, si attiva il Naive CAM Detector: quando ci sono una serie di movimenti lineari in XYZ a stesso feed rate che sono a meno di Q- dalla collinearità, questi vengono compressi in un unico movimento lineare. Nei movimenti G2/G3 nel piano G17 (XY), quando la deviazione massima di un arco da una linea retta è inferiore alla tolleranza G64 P-, l'arco viene suddiviso in due linee (dall'inizio dell'arco al punto medio, e dal punto medio alla fine). Queste linee sono poi soggette all'algoritmo naive cam per le linee. Così, i casi linea-arco, arco-arco e arco-linea, oltre a linea-linea, beneficiano del Naive CAM Detector. Ciò migliora le prestazioni di contornatura semplificando il percorso. È consentito programmare per la modalità già attiva. Vedi anche la sezione [[Controllo della Traiettoria]] per ulteriori informazioni su queste modalità. Se Q non è specificato, avrà lo stesso comportamento di prima e utilizzerà il valore di P-. Impostare Q a zero per disattivare il Naive CAM Detector.

**Esempio di G64 P-**

```gcode
G64 P0.015 (imposta il seguimento del percorso per essere entro 0.015 dal percorso effettivo)
```

È buona norma includere una specifica di controllo del percorso nel preambolo di ogni file G-code.

---
#### G70 Ciclo di Finitura per Tornitura

```gcode
G70 Q- <X-> <Z-> <D-> <E-> <P-> 
```

- **Q** - Il numero della sottoprocedura.  
- **X** - La posizione iniziale dell'asse X, predefinita alla posizione iniziale.  
- **Z** - La posizione iniziale dell'asse Z, predefinita alla posizione iniziale.  
- **D** - La distanza iniziale del profilo, predefinita a 0.  
- **E** - La distanza finale del profilo, predefinita a 0.  
- **P** - Il numero di passate da utilizzare, predefinito a 1.

Il ciclo G70 è concepito per essere utilizzato dopo che la forma del profilo, definita nella sottoprocedura con il numero **Q**, è stata tagliata con G71 o G72.
- Movimento preliminare. 
	- Se vengono utilizzati **Z** o **X**, viene effettuato un movimento rapido verso quella posizione. Tale posizione viene utilizzata anche tra ogni passata di finitura.  
	- Successivamente, viene eseguito un movimento rapido verso l'inizio del profilo.  
	- Il percorso indicato in **Q-** viene seguito utilizzando i comandi **G1** e **[gcode:g2-g3]**.  
	- Se è necessaria una passata successiva, viene eseguito un ulteriore rapido verso la posizione intermedia, prima di eseguire un rapido verso l'inizio del profilo.  
	- Dopo l'ultima passata, l'utensile viene lasciato alla fine del profilo, inclusa la distanza specificata in **E-**.
- Passate multiple. La distanza tra la passata e il profilo finale è calcolata come  (pass-1) * (D-E) / P + E,  dove "pass" è il numero della passata e **D**, **E** e **P** sono i valori corrispondenti.  
- La distanza viene calcolata utilizzando la posizione iniziale del ciclo, con una distanza positiva verso questo punto.
- Raccordi e smussi nel profilo.  È possibile aggiungere raccordi o smussi nel profilo; vedere \[gcode:g71-g72] per maggiori dettagli.

Si genera un errore se:
- Non è definita nessuna sottoprocedura con il numero indicato in **Q**.
- Il percorso indicato nel profilo non è monotono in **Z** o **X**.
- Non è stato utilizzato \[gcode:g17-g19.1] per selezionare il piano ZX.

---
#### G71-G72 Cicli di Sgrossatura per Tornitura  

```gcode
G71   Q- <X-> <Z-> <D-> <I-> <R->
G71.1 Q- <X-> <Z-> <D-> <I-> <R->
G71.2 Q- <X-> <Z-> <D-> <I-> <R->
G72   Q- <X-> <Z-> <D-> <I-> <R->
G72.1 Q- <X-> <Z-> <D-> <I-> <R->
G72.2 Q- <X-> <Z-> <D-> <I-> <R->
```

- **Q** - Il numero della sottoprocedura.  
- **X** - La posizione iniziale dell'asse X, predefinita alla posizione iniziale.  
- **Z** - La posizione iniziale dell'asse Z, predefinita alla posizione iniziale.  
- **D** - La distanza residua fino al profilo, predefinita a 0.  
- **I** - L'incremento di taglio, predefinito a 1.  
- **R** - La distanza di retrazione, predefinita a 0,5.

Il ciclo **G71/G72** è concepito per sgrossare un profilo su un tornio.  
I cicli **G71** rimuovono strati di materiale mentre si procede lungo l'asse **Z**.  
I cicli **G72** rimuovono materiale mentre si procede lungo l'asse **X** (ciclo di fronteggiatura).  
La direzione di avanzamento è la stessa del percorso indicato nella sottoprocedura.  
Per il ciclo G71 la coordinata **Z** deve variare in modo monotono; per il ciclo **G72** ciò è richiesto per l'asse **X**.

Il profilo è definito in una sottoprocedura con il numero **Q-**.  
Questa sottoprocedura può contenere comandi di movimento **G0**, **G1**, **G2** e **G3**.  
Tutti gli altri comandi vengono ignorati, comprese le impostazioni di feed e velocità.  
I comandi \[gcode:g0] sono interpretati come **G1**.  
Ogni comando di movimento può includere anche un numero opzionale **A-** o **C-**.  
Se viene aggiunto il numero **A-**, verrà inserito un raccordo con il raggio indicato da **A** al punto finale del movimento; se questo raggio è troppo grande, l'algoritmo fallirà con un errore di percorso non monotono.  
È inoltre possibile utilizzare il numero **C-**, che permette di inserire uno smusso.  
Questo smusso avrà gli stessi punti finali che avrebbe un raccordo della stessa dimensione, ma verrà inserita una linea retta anziché un arco.

Quando si è in modalità assoluta, **U** (per **X**) e **W** (per **Z**) possono essere utilizzati come spostamenti incrementali.

I cicli **G7x.1** non lavorano tasche/pozzetti.  
I cicli **G7x.2** tagliano solo dopo il primo pozzetto e continuano da dove si era interrotto il ciclo **G7x.1**.  
È consigliabile lasciare materiale aggiuntivo da tagliare prima del ciclo **G7x.2**, in modo che, se il **G7x.1** ha utilizzato un **D1.0**, il **G7x.2** possa utilizzare un **D0.5** e vengano rimossi 0,5 mm durante il passaggio da un pozzetto all'altro.

I normali cicli **G7x** tagliano l'intero profilo in un unico ciclo.
1. Movimento preliminare.  
	- Se vengono utilizzati **Z** o **X**, viene effettuato un movimento rapido verso quella posizione.  
	- Dopo che il profilo è stato tagliato, l'utensile si ferma alla fine del profilo, inclusa la distanza specificata in **D**.  
2. Il numero **D** viene utilizzato per mantenere una distanza dal profilo finale, in modo da lasciare materiale per la finitura.

Si genera un errore se:
- Non è definita nessuna sottoprocedura con il numero indicato in **Q**.
- Il percorso indicato nel profilo non è monotono in **Z** o **X**.
- Non è stato utilizzato \[gcode:g17-g19.1] per selezionare il piano ZX.
- È attiva la compensazione utensile \[gcode:g41-g42].

---
#### G73 Ciclo di Foratura con Frantumazione Trucioli

```gcode
G73 X- Y- Z- R- Q- <L->
```

- **R** - Posizione di retrazione lungo l'asse **Z**.  
- **Q** - Incremento delta lungo l'asse **Z**.  
- **L** - Ripetizione

Il ciclo **G73** è per foratura o fresatura con frantumazione dei trucioli.  
Questo ciclo prevede un numero **Q** che rappresenta un incremento delta lungo l'asse **Z**.
- Movimento preliminare.  
	- Se la posizione attuale di **Z** è inferiore alla posizione **R**, l'asse **Z** esegue un movimento rapido verso la posizione **R**.  
	- Muoversi verso le coordinate **X** e **Y**.  
- Muovere l'asse **Z**, solo alla velocità di avanzamento attuale, in senso discendente di un delta o fino alla posizione **Z**, a seconda di quale sia meno profondo.  
- Movimento rapido verso l'alto di 0,010 pollici o 0,254 mm.  
- Ripetere i passaggi 2 e 3 fino a quando, nel passaggio 2, viene raggiunta la posizione **Z**.  
- L'asse **Z** esegue un movimento rapido verso la posizione **R**.

Si genera un errore se:
- Il numero **Q** è negativo o zero.
- Il numero **R** non è specificato.

---
#### G74 Ciclo di Filettatura Sinistrorsa con Pausa 

```gcode
G74 (**X- Y- Z-**) oppure (**U- V- W-**) **R- L- P- $- F-**  
```

- **R-** - Posizione di retrazione lungo l'asse **Z**.  
- **L-** - Utilizzato in modalità incrementale; numero di volte da ripetere il ciclo. Vedere G81 per esempi.  
- **P-** - Tempo di pausa (secondi).  
- **$-** - Mandrino selezionato.  
- **F-** - Velocità di avanzamento (velocità del mandrino moltiplicata per la distanza percorsa per rivoluzione, cioè il passo della filettatura).

*Avvertenza*  
***G74** non utilizza il movimento sincronizzato.*  

Il ciclo **G74** è concepito per la filettatura con mandrino flottante e con pausa al fondo del foro.
3. Movimento preliminare, come descritto nella sezione Movimento Preliminare e Intermedio.  
4. Disabilitare le sovrascritture di avanzamento e velocità.  
5. Muovere l'asse **Z** alla velocità di avanzamento attuale fino alla posizione **Z**.  
6. Fermare il mandrino selezionato (scelto tramite il parametro **$**).  
7. Avviare la rotazione del mandrino in senso orario.  
8. Pausa per il numero di secondi indicato da **P**.  
9. Muovere l'asse **Z** alla velocità di avanzamento attuale per liberare **Z**.  
10. Ripristinare le sovrascritture di avanzamento e velocità allo stato precedente.

La durata della pausa è specificata da una parola **P** nel blocco **G74**.  
La velocità di avanzamento **F-** è data dalla velocità del mandrino moltiplicata per la distanza percorsa per rivoluzione (passo della filettatura).  
Ad esempio, **S100** con un passo della filettatura di 1,25 mm per rivoluzione fornisce un avanzamento di **F125**.

---
#### G76 Ciclo di Filettatura  

```gcode
G76 P- Z- I- J- R- K- Q- H- E- L- $- 
```

![[Pasted image 20250213160359.png]]
 
- Drive Line - Una linea che passa per la posizione iniziale di **X** parallela a **Z**.
- **P-** Il passo della filettatura in distanza per rivoluzione.  
- **Z-** La posizione finale delle filettature. Al termine del ciclo, l'utensile si troverà in questa posizione **Z**.

*Nota*  
*Quando è in vigore la modalità diametro tornitura (**G7**), i valori per **I**, **J** e **K** sono misurazioni in diametro. Quando è in vigore la modalità raggio tornitura (**G8**), i valori per **I**, **J** e **K** sono misurazioni in raggio.*  

- **I-** L'offset del picco della filettatura dalla Drive Line. Valori di **I** negativi indicano filettature esterne, mentre valori positivi indicano filettature interne. Generalmente il materiale viene tornito a questa dimensione prima del ciclo **G76**.  
- **J-** Un valore positivo che specifica la profondità iniziale di taglio. Il primo taglio di filettatura avverrà **J** oltre la posizione del picco della filettatura.  
- **K-** Un valore positivo che specifica la profondità completa della filettatura. L'ultimo taglio di filettatura avverrà **K** oltre la posizione del picco della filettatura.

**Impostazioni opzionali**
- **$-** Il numero del mandrino a cui il movimento sarà sincronizzato (predefinito 0). Ad esempio, se viene programmato **$1**, il movimento inizierà solitamente sul contromandrino.  
- **R-** La degressione della profondità. **R1.0** seleziona una profondità costante nelle passate di filettatura successive. **R2.0** seleziona un'area costante. Valori compresi tra 1.0 e 2.0 selezionano una profondità decrescente ma un'area crescente. Valori superiori a 2.0 selezionano un'area decrescente. Attenzione: valori di degressione eccessivamente alti comporteranno un numero elevato di passate. (degressione = una discesa per fasi o gradini.)

*Avvertenza*  
*Valori di degressione eccessivamente alti produrranno un numero inutilmente elevato di passate. (degressing = discesa a fasi)*

- **Q-** L'angolo di scorrimento composto è l'angolo (in gradi) che descrive in quale misura le passate successive devono essere sfasate lungo la Drive Line. Questo viene utilizzato per fare in modo che un lato dell'utensile rimuova più materiale dell'altro. Un valore **Q** positivo fa sì che il bordo anteriore dell'utensile tagli più aggressivamente. I valori tipici sono 29, 29.5 o 30.  
- **H-** Il numero di passate di rimbalzo. Le passate di rimbalzo sono passate aggiuntive a piena profondità di filettatura. Se non si desiderano passate aggiuntive, programmare **H0**.

Le entrate e le uscite della filettatura possono essere programmate con smussi tramite i valori **E** e **L**.  
- **E-** Specifica la distanza lungo la Drive Line utilizzata per lo smusso. L'angolo dello smusso sarà tale che l'ultima passata si smussa fino alla cresta della filettatura sulla distanza specificata con **E**. **E0.2** darà uno smusso per i primi/ultimi 0,2 unità di lunghezza lungo la filettatura. Per uno smusso di 45 gradi, programmare **E** uguale a **K**.  
- **L-** Specifica quali estremità della filettatura ricevono lo smusso. Programmare **L0** per nessuno smusso (predefinito), **L1** per smusso in entrata, **L2** per smusso in uscita, o **L3** per smusso sia in entrata che in uscita. Gli smussi in entrata faranno una pausa alla Drive Line per sincronizzarsi con l'impulso di indice, quindi si muoveranno alla velocità di avanzamento verso l'inizio dello smusso. Se non è previsto uno smusso in entrata, l'utensile si sposterà rapidamente alla profondità di taglio, si sincronizzerà e inizierà il taglio.

L'utensile viene spostato nelle posizioni iniziali di **X** e **Z** prima dell'emissione del **G76**. La posizione **X** è la Drive Line e la posizione **Z** è l'inizio delle filettature.  
L'utensile farà una breve pausa per la sincronizzazione prima di ogni passata di filettatura, pertanto sarà necessario un solco di rilievo all'entrata, a meno che l'inizio della filettatura non si trovi oltre il limite del materiale o venga utilizzato uno smusso in entrata.

A meno che non si utilizzi uno smusso in uscita, il movimento di uscita non è sincronizzato con la velocità del mandrino e sarà un movimento rapido. Con un mandrino lento, il movimento di uscita potrebbe richiedere solo una piccola frazione di rivoluzione. Se la velocità del mandrino aumenta dopo che sono state completate diverse passate, i movimenti di uscita successivi richiederanno una porzione maggiore di una rivoluzione, comportando un taglio molto aggressivo durante il movimento di uscita. Questo può essere evitato fornendo un solco di rilievo all'uscita o mantenendo costante la velocità del mandrino durante la filettatura.

La posizione finale dell'utensile sarà alla fine della Drive Line. Per una filettatura interna sarà necessario un movimento **Z** di sicurezza per rimuovere l'utensile dal foro.

Si genera un errore se:
- Il piano attivo non è il piano **ZX**.
- Sono specificate altre parole asse, come **X-** o **Y-**.
- Il valore di degressione **R-** è inferiore a 1.0.
- Non sono specificate tutte le parole richieste.
- **P-**, **J-**, **K-** o **H-** sono negativi.
- **E-** è maggiore della metà della lunghezza della Drive Line.

Informazioni Tecniche  
Il ciclo preimpostato **G76** si basa sul movimento sincronizzato del mandrino **G33**. Per ulteriori informazioni, vedere la sezione Technical Info di **G33**.

**Esempio di G76**

```gcode
G0 Z-0.5 X0.2
G76 P0.05 Z-1 I-.075 J0.008 K0.045 Q29.5 L2 E0.045
```

Nella figura, l'utensile si trova nella posizione finale al termine del ciclo **G76**. Si può vedere il percorso di ingresso a destra derivante da Q29.5 e il percorso di uscita a sinistra derivante da L2 E0.045. Le linee bianche rappresentano i movimenti di taglio.

![[Pasted image 20250213161957.png]]

---
#### G80-G89 Cicli Preimpostati  

I cicli preimpostati **G81** fino a **G89** e l'arresto dei cicli preimpostati **G80** sono descritti in questa sezione.

Tutti i cicli preimpostati vengono eseguiti rispetto al piano attualmente selezionato. È possibile selezionare uno qualsiasi dei nove piani. In questa sezione la maggior parte delle descrizioni presuppone che sia stato selezionato il piano XY. Il comportamento è analogo se viene selezionato un altro piano, e devono essere usate le parole corrette. Ad esempio, nel piano **G17.1** l'azione del ciclo preimpostato avviene lungo **W**, e le posizioni o gli incrementi sono espressi con **U** e **V**. In questo caso sostituire **U,V,W** a **X,Y,Z** nelle istruzioni sottostanti.

Le parole asse rotanti non sono permesse nei cicli preimpostati. Quando il piano attivo appartiene alla famiglia **XYZ**, le parole asse **UVW** non sono permesse. Analogamente, quando il piano attivo appartiene alla famiglia **UVW**, le parole asse **XYZ** non sono permesse.

###### Parole Comuni  
Tutti i cicli preimpostati utilizzano gruppi di parole **X, Y, Z** o **U, V, W** a seconda del piano selezionato e le parole **R**. La posizione **R** (che solitamente indica retrazione) è lungo l'asse perpendicolare al piano attualmente selezionato (asse **Z** per il piano **XY**, ecc.). Alcuni cicli preimpostati utilizzano argomenti aggiuntivi.

###### Numeri "Sticky"  
Per i cicli preimpostati, definiremo un numero "sticky" se, quando lo stesso ciclo viene utilizzato su più righe di codice consecutive, il numero deve essere usato la prima volta, ma è opzionale nelle righe successive. I numeri "sticky" mantengono il loro valore nelle righe successive se non vengono esplicitamente programmati per essere diversi. Il numero **R** è sempre "sticky".

In modalità di distanza incrementale i numeri **X, Y** e **R** sono trattati come incrementi rispetto alla posizione corrente e **Z** come un incremento dalla posizione dell'asse **Z** prima che avvenga il movimento che lo coinvolge. In modalità di distanza assoluta, i numeri **X, Y, R** e **Z** sono posizioni assolute nel sistema di coordinate corrente.

###### Ciclo di Ripetizione  
Il numero **L** è opzionale e rappresenta il numero di ripetizioni. **L=0** non è consentito. Se la funzione di ripetizione viene utilizzata, solitamente viene usata in modalità di distanza incrementale, in modo che la stessa sequenza di movimenti venga ripetuta in più punti equidistanti lungo una linea retta. Quando **L-** è maggiore di 1 in modalità incrementale con il piano **XY** selezionato, le posizioni **X** e **Y** sono determinate aggiungendo i numeri **X** e **Y** dati, rispettivamente, o alla posizione corrente **X** e **Y** (al primo giro) o alla posizione **X** e **Y** al termine del giro precedente (nelle ripetizioni). Così, se si programma **L10** si otterranno 10 cicli. Il primo ciclo sarà a una distanza **X,Y** dalla posizione originale. Le posizioni **R** e **Z** non cambiano durante le ripetizioni. Il numero **L** non è "sticky". In modalità di distanza assoluta, **L>1** significa eseguire lo stesso ciclo nello stesso punto più volte; omettere la parola **L** equivale a specificare **L=1**.

###### Modalità di Retrazione  
L'altezza del movimento di retrazione al termine di ogni ripetizione (chiamato "clear **Z**" nelle descrizioni sottostanti) è determinata dall'impostazione della modalità di retrazione, ovvero alla posizione **Z** originale (se essa è superiore alla posizione **R** e la modalità di retrazione è **G98, OLD_Z**), oppure alla posizione **R** altrimenti. Vedere la sezione **G98 G99**.

###### Errori nei Cicli Preimpostati  
Si genera un errore se:
- mancano tutte le parole asse durante un ciclo preimpostato,
- vengono utilizzate insieme parole asse appartenenti a gruppi diversi (**XYZ** e **UVW**),
- è richiesto un numero **P** e viene usato un numero **P** negativo,
- viene utilizzato un numero **L** che non valuta a un intero positivo,
- viene usato un movimento di un asse rotante durante un ciclo preimpostato,
- è attivo un feed rate a tempo inverso durante un ciclo preimpostato,
- oppure è attiva la compensazione utensile durante un ciclo preimpostato.

Se il piano **XY** è attivo, il numero **Z** è "sticky", ed è un errore se:
- il numero **Z** manca e lo stesso ciclo preimpostato non era già attivo,
- oppure se il numero **R** è inferiore al numero **Z**.

Se sono attivi altri piani, le condizioni d'errore sono analoghe a quelle sopra per il piano **XY**.

###### Movimento Preliminare e Intermedio  
Il movimento preliminare è un insieme di movimenti comune a tutti i cicli preimpostati di fresatura. Se la posizione corrente **Z** è inferiore alla posizione **R**, l'asse **Z** esegue un movimento rapido verso la posizione **R**. Questo avviene una sola volta, indipendentemente dal valore di **L**.

Inoltre, all'inizio del primo ciclo e di ogni ripetizione, vengono eseguiti uno o due movimenti:
- Un movimento rapido parallelo al piano **XY** verso la posizione **XY** indicata.
- L'asse **Z** esegue un movimento rapido verso la posizione **R**, se non è già in tale posizione.

Se è attivo un altro piano, i movimenti preliminari e intermedi sono analoghi.

###### Perché utilizzare un ciclo preimpostato?  
Esistono almeno due ragioni per utilizzare i cicli preimpostati. La prima è l'economia di codice. Un singolo foro richiederebbe diverse righe di codice per essere eseguito.

L'Esempio **G81 Example 1** dimostra come un ciclo preimpostato possa essere utilizzato per produrre 8 fori con dieci righe di codice all'interno della modalità di ciclo preimpostato. Il programma sottostante produrrà lo stesso insieme di 8 fori utilizzando cinque righe per il ciclo preimpostato. Non segue esattamente lo stesso percorso né fora nello stesso ordine dell'esempio precedente. Tuttavia, l'economia di scrittura del codice di un buon ciclo preimpostato dovrebbe essere evidente.

*Nota*  
*I numeri di linea non sono necessari ma aiutano a chiarire questi esempi.*

**Otto Fori**

```
N100 G90 G0 X0 Y0 Z0 (muovi l'origine delle coordinate)
N110 G1 F10 X0 G4 P0.1
N120 G91 G81 X1 Y0 Z-1 R1 L4 (ciclo di foratura preimpostato)
N130 G90 G0 X0 Y1
N140 Z0
N150 G91 G81 X1 Y0 Z-0.5 R1 L4 (ciclo di foratura preimpostato)
N160 G80 (disattiva il ciclo preimpostato)
N170 M2 (fine programma)
```

Il **G98** nella seconda riga significa che il movimento di ritorno sarà alla posizione **Z** della prima riga, poiché essa è superiore al valore **R** specificato.

![[Pasted image 20250213162514.png]]

**Dodici Fori in Serie Quadrata**  
Questo esempio dimostra l'uso della parola **L** per ripetere un insieme di cicli di foratura incrementali per blocchi successivi di codice all'interno della stessa modalità di movimento **G81**. Qui si producono 12 fori utilizzando cinque righe di codice nella modalità di movimento preimpostato.

```
N1000 G90 G0 X0 Y0 Z0 (muovi l'origine delle coordinate)
N1010 G1 F50 X0 G4 P0.1
N1020 G91 G81 X1 Y0 Z-0.5 R1 L4 (ciclo di foratura preimpostato)
N1030 X0 Y1 R0 L3 (ripeti)
N1040 X-1 Y0 L3 (ripeti)
N1050 X0 Y-1 L2 (ripeti)
N1060 G80 (disattiva il ciclo preimpostato)
N1070 G90 G0 X0 (movimento rapido all'origine)
N1080 Y0
N1090 Z0
N1100 M2 (fine programma)
```

![[Pasted image 20250213162531.png]]

La seconda ragione per utilizzare un ciclo preimpostato è che tutti essi producono movimenti preliminari e di ritorno che è possibile anticipare e controllare indipendentemente dal punto di partenza del ciclo preimpostato.

---
#### G80 Annulla il Ciclo Preimpostato

G80 - annulla il movimento modale del ciclo preimpostato. G80 fa parte del gruppo modale 1, quindi la programmazione di qualsiasi altro codice G del gruppo modale 1 annullerà anche il ciclo preimpostato.

Si genera un errore se:
- Vengono programmate parole asse quando **G80** è attivo.

**Esempio G80**

```gcode
G90 G81 X1 Y1 Z1.5 R2.8 (ciclo preimpostato in modalità assoluta)
G80 (disattiva il ciclo preimpostato)
G0 X0 Y0 Z0 (movimento rapido verso l'origine delle coordinate)
```

Il seguente codice produce la stessa posizione finale e lo stesso stato macchina del codice precedente.

**Esempio G0**

```gcode
G90 G81 X1 Y1 Z1.5 R2.8 (ciclo preimpostato in modalità assoluta)
G0 X0 Y0 Z0 (movimento rapido verso l'origine delle coordinate)
```

Il vantaggio del primo insieme è che la riga con **G80** disattiva chiaramente il ciclo preimpostato **G81**. Con il primo insieme di blocchi, il programmatore deve riattivare il movimento con **G0**, come fatto nella riga successiva, o con qualsiasi altro codice **G** di movimento.

Se un ciclo preimpostato non viene disattivato con G80 o un altro codice di movimento, il ciclo preimpostato tenterà di ripetersi utilizzando il blocco di codice successivo che contiene una parola **X**, **Y** o **Z**. Il seguente file foratura (**G81**) esegue un insieme di otto fori come mostrato nella didascalia seguente.

**Esempio G80**

```gcode
N100 G90 G0 X0 Y0 Z0 (origine delle coordinate)
N110 G1 X0 G4 P0.1
N120 G81 X1 Y0 Z0 R1 (ciclo preimpostato di foratura)
N130 X2
N140 X3
N150 X4
N160 Y1 Z0.5
N170 X3
N180 X2
N190 X1
N200 G80 (disattiva il ciclo preimpostato)
N210 G0 X0 (movimento rapido verso l'origine)
N220 Y0
N230 Z0
N240 M2 (fine programma)
```

*Nota*  
*Si noti il cambiamento della posizione Z dopo i primi quattro fori. Inoltre, questo è uno dei pochi casi in cui i numeri di linea hanno un certo valore, in quanto permettono di indicare al lettore una specifica riga di codice.*

L'uso di **G80** nella riga N200 è opzionale perché il **G0** sulla riga successiva disattiverà il ciclo **G81**. Tuttavia, utilizzare **G80** come mostrato nell'Esempio 1 rende il ciclo preimpostato più leggibile; senza di esso, non è così evidente che tutti i blocchi tra N120 e N200 appartengono al ciclo preimpostato.

---
#### G81 Ciclo di Foratura

```gcode
G81 (X- Y- Z-) oppure (U- V- W-) R- L-  
```

Il ciclo **G81** è concepito per la foratura.

Il ciclo funziona come segue:
1. Movimento preliminare, come descritto nella sezione Movimento Preliminare e Intermedio.
2. Muovi l'asse **Z** alla [[Velocità di Avanzamento]] attuale fino alla posizione **Z**.
3. L'asse **Z** esegue un [[Movimento Rapido]] verso la posizione di "clear **Z**".

![[Pasted image 20250213163603.png]]

**Esempio 1 - G81 in Posizione Assoluta**

```gcode
G90 G98 G81 X4 Y5 Z1.5 R2.8
```

Supponiamo che la posizione corrente sia (**X**1, **Y**2, **Z**3) e che la riga di codice NC precedente sia interpretata.

Questo imposta la modalità di distanza assoluta (**G90**) e la modalità di retrazione OLD_Z (**G98**) e richiede che il ciclo di foratura **G81** venga eseguito una volta.
- Il valore **X** e la posizione **X** saranno 4.  
- Il valore **Y** e la posizione **Y** saranno 5.  
- Il valore **Z** e la posizione **Z** saranno 1.5.  
- Il valore **R** e la posizione di "clear Z" saranno 2.8. OLD_Z è 3.

Avvengono i seguenti movimenti:
- Un movimento rapido parallelo al piano **XY** fino a (X4, Y5).
- Un movimento rapido parallelo all'asse **Z** fino a (Z2.8).
- Un movimento parallelo all'asse **Z** alla velocità di avanzamento fino a (Z1.5).
- Un movimento rapido parallelo all'asse **Z** fino a (Z3).

![[Pasted image 20250213163622.png]]

**Esempio 2 - G81 in Posizione Relativa**

```gcode
G91 G98 G81 X4 Y5 Z-0.6 R1.8 L3
```

Supponiamo che la posizione corrente sia (X1, Y2, Z3) e che la riga di codice NC precedente sia interpretata.

Questo imposta la modalità di distanza incrementale (**G91**) e la modalità di retrazione OLD_Z (**G98**). Viene richiesto anche che il ciclo di foratura **G81** venga ripetuto tre volte.  
Il valore X è 4, il valore Y è 5, il valore Z è -0.6 e il valore R è 1.8.  
La posizione iniziale X sarà 5 (= 1 + 4), la posizione iniziale Y sarà 7 (= 2 + 5), la posizione di "clear Z" sarà 4.8 (= 1.8 + 3) e la posizione Z sarà 4.2 (= 4.8 - 0.6). OLD_Z è 3.

Il primo movimento preliminare consiste in un movimento rapido massimo lungo l'asse **Z** fino a (X1, Y2, Z4.8), poiché OLD_Z < "clear Z".

La prima ripetizione consiste di 3 movimenti:
- Un movimento rapido parallelo al piano **XY** fino a (X5, Y7).
- Un movimento parallelo all'asse **Z** alla velocità di avanzamento fino a (Z4.2).
- Un movimento rapido parallelo all'asse **Z** fino a (X5, Y7, Z4.8).

![[Pasted image 20250213163643.png]]

La seconda ripetizione consiste di 3 movimenti. La posizione **X** viene resettata a 9 (= 5 + 4) e la posizione **Y** a 12 (= 7 + 5):
- Un movimento parallelo all'asse **Z** alla velocità di avanzamento fino a (X9, Y12, Z4.2).
- Un movimento rapido parallelo all'asse **Z** fino a (X9, Y12, Z4.8).

La terza ripetizione consiste di 3 movimenti. La posizione **X** viene resettata a 13 (= 9 + 4) e la posizione **Y** a 17 (= 12 + 5):
- Un movimento rapido parallelo al piano **XY** fino a (X13, Y17, Z4.8).
- Un movimento parallelo all'asse **Z** alla velocità di avanzamento fino a (X13, Y17, Z4.2).
- Un movimento rapido parallelo all'asse **Z** fino a (X13, Y17, Z4.8).

**Esempio 3 - G81 in Posizione Assoluta**

```gcode
G90 G98 G81 X4 Y5 Z1.5 R2.8
```

Supponiamo ora che venga eseguito il primo blocco G81 ma partendo da (X0, Y0, Z0) invece che da (X1, Y2, Z3).

Poiché OLD_Z è inferiore al valore **R**, non viene aggiunto nulla al movimento, ma poiché il valore iniziale di Z è inferiore al valore specificato in **R**, vi sarà un movimento iniziale dell'asse **Z** durante i movimenti preliminari.

![[Pasted image 20250213163716.png]]

**Esempio 4 - G81 R > Z**  
Questo è un grafico del percorso di movimento per il secondo blocco **G81**.

```gcode
G91 G98 G81 X4 Y5 Z-0.6 R1.8 L3
```

Poiché questo grafico parte da (**X**0, **Y**0, **Z**0), l'interprete aggiunge il valore iniziale **Z**0 e **R**1.8 e muove rapidamente verso quella posizione. Dopo tale movimento iniziale in Z, la funzione di ripetizione opera come nell'esempio 3, con la profondità finale **Z** che è 0.6 inferiore al valore **R**.

![[Pasted image 20250213163740.png]]

**Esempio 5 - G81 in Posizione Relativa con R > Z**

```gcode
G90 G98 G81 X4 Y5 Z-0.6 R1.8
```

Poiché questo grafico parte da (**X**0, **Y**0, **Z**0), l'interprete aggiunge il valore iniziale **Z**0 e **R**1.8 e muove rapidamente verso quella posizione, come nell'Esempio 4. Dopo tale movimento iniziale in **Z**, viene eseguito un movimento rapido verso (**X**4, **Y**5), quindi la profondità finale in **Z** sarà 0.6 inferiore al valore **R**. La funzione di ripetizione farebbe ripetere il movimento **Z** nello stesso punto.

---
#### G82 Ciclo di Foratura, Pausa

```gcode
G82 (X- Y- Z-) oppure (U- V- W-) R- L- P-  
```

Il ciclo **G82** è concepito per la foratura con una pausa (dwell) sul fondo del foro.
4. Movimento preliminare, come descritto nella sezione Movimento Preliminare e Intermedio.
5. Muovi l'asse **Z** alla velocità di avanzamento attuale fino alla posizione **Z**.
6. Pausa per il numero di secondi indicato da **P**.
7. L'asse **Z** esegue un movimento rapido verso la posizione di "clear Z".

Il movimento di un ciclo preimpostato **G82** è identico a quello di **G81**, con l'aggiunta di una pausa sul fondo del movimento in **Z**. La durata della pausa è specificata da una parola **P** nel blocco **G82**.

```gcode
G90 G82 G98 X4 Y5 Z1.5 R2.8 P2
```

Questo sarà simile all'Esempio 3 sopra, con l'aggiunta di una pausa di 2 secondi sul fondo del foro.

---
#### G83 Ciclo di Foratura a Piccoli Passi

```gcode
G83 (X- Y- Z-) oppure (U- V- W-) R- L- Q- 
``` 

Il ciclo **G83** (spesso chiamato "peck drilling") è concepito per foratura profonda o fresatura con frantumazione dei trucioli. Le retrazioni in questo ciclo eliminano i trucioli dal foro e tagliano eventuali filamenti lunghi (comuni quando si fora in alluminio). Questo ciclo richiede un numero Q che rappresenta un incremento delta lungo l'asse **Z**. La retrazione prima della profondità finale sarà sempre fino al piano di retrazione, anche se è in vigore il **G98**. L'ultima retrazione rispetterà il **G98/99** in vigore. **G83** funziona allo stesso modo di **G81** con l'aggiunta di retrazioni durante l'operazione di foratura.
8. Movimento preliminare, come descritto nella sezione [[Movimento Preliminare e Intermedio.]]
9. Muovere l'asse **Z** alla velocità di avanzamento attuale in discesa di delta o fino alla posizione **Z**, a seconda di quale sia meno profondo.
10. Movimento rapido in uscita fino al piano di retrazione specificato dalla parola **R**.
11. Movimento rapido in discesa fino al fondo attuale del foro, ridotto di 0,010 pollici o 0,254 mm.
12. Ripetere i passaggi 2, 3 e 4 fino a raggiungere la posizione **Z** al passaggio 2.
13. L'asse **Z** esegue un movimento rapido per liberare **Z**.

Si genera un errore se:
- il numero **Q** è negativo o zero.

---
#### G84 Ciclo di Filettatura Destrorsa con Pausa  

```gcode
G84 (X- Y- Z-) oppure (U- V- W-) R- L- P- $- F-  
```

- **R-** - Posizione di retrazione lungo l'asse Z. 
- **L-** - Utilizzato in modalità incrementale; numero di volte in cui ripetere il ciclo. Vedere G81 per esempi.  
- **P-** - Tempo di pausa (secondi). 
- **$-** - Mandrino selezionato.  
- **F-** - Velocità di avanzamento (velocità del mandrino moltiplicata per la distanza percorsa per rivoluzione, cioè il passo della filettatura).

*Avvertenza*  
***G84** non utilizza il movimento sincronizzato.*  

Il ciclo G84 è concepito per la filettatura con mandrino flottante e una pausa sul fondo del foro.
14. Movimento preliminare, come descritto nella sezione [[Movimento Preliminare e Intermedio.]]
15. Disabilitare le sovrascritture di avanzamento e velocità.
16. Muovere l'asse Z alla velocità di avanzamento attuale fino alla posizione **Z**.
17. Fermare il mandrino selezionato (scelto tramite il parametro **$**).
18. Avviare la rotazione del mandrino in senso antiorario.
19. Pausa per il numero di secondi indicato da **P**.
20. Muovere l'asse Z alla velocità di avanzamento attuale per liberare **Z**.
21. Ripristinare le sovrascritture di avanzamento e velocità allo stato precedente.

La durata della pausa è specificata da una parola **P** nel blocco **G84**. La velocità di avanzamento **F-** è data dalla velocità del mandrino moltiplicata per la distanza percorsa per rivoluzione (passo della filettatura). Ad esempio, con **S100** e un passo della filettatura di **1,25 MM** per rivoluzione si ottiene un avanzamento di **F125**.

---
#### G85 Ciclo di Alesatura, Avanzamento in Uscita  

```gcode
G85 (X- Y- Z-) oppure (U- V- W-) R- L-
``` 

Il ciclo **G85** è concepito per alesatura o maschiatura, ma può essere utilizzato anche per foratura o fresatura.
22. Movimento preliminare, come descritto nella sezione [[Movimento Preliminare e Intermedio.]]
23. Muovere l'asse **Z** solamente alla velocità di avanzamento attuale fino alla posizione **Z**.
24. Retrarre l'asse **Z** alla velocità di avanzamento attuale fino al piano **R**, se questo è inferiore alla **Z** iniziale.
25. Retrarre a velocità di traversata per liberare **Z**.

---
#### G86 Ciclo di Alesatura, Arresto del Mandrino, Movimento Rapido in Uscita 

```gcode
G86 (X- Y- Z-) oppure (U- V- W-) R- L- P- $-  
```

Il ciclo **G86** è concepito per alesatura. Questo ciclo utilizza un numero **P** che indica il numero di secondi di pausa.
26. Movimento preliminare, come descritto nella sezione [[Movimento Preliminare e Intermedio.]]
27. Muovere l'asse **Z** solamente alla velocità di avanzamento attuale fino alla posizione **Z**.
28. Pausa per il numero di secondi indicato da **P**.
29. Fermare la rotazione del mandrino selezionato (scelto tramite il parametro **$**).
30. L'asse Z esegue un movimento rapido per liberare **Z**.
31. Riavviare il mandrino nella direzione in cui stava ruotando.

Si genera un errore se:
- Il mandrino non sta ruotando prima che questo ciclo venga eseguito.

---
#### G87 Ciclo di Alesatura Posteriore  

Questo codice è attualmente non implementato in LinuxCNC. Viene accettato, ma il comportamento è indefinito.

---

#### G88 Ciclo di Alesatura, Arresto del mandrino, Uscita manuale  

Questo codice è attualmente non implementato in LinuxCNC. Viene accettato, ma il comportamento è indefinito.

---
#### G89 Ciclo di Alesatura, Pausa, Avanzamento in Uscita  

```gcode
G89 (X- Y- Z-) oppure (U- V- W-) R- L- P-  
```

Il ciclo **G89** è concepito per alesatura. Questo ciclo utilizza un numero **P**, dove **P** specifica il numero di secondi di pausa.
32. Movimento preliminare, come descritto nella sezione [[Movimento Preliminare e Intermedio.]]
33. Muovere l'asse **Z** solamente alla [[Velocità di Avanzamento]] attuale fino alla posizione Z.
34. Pausa per il numero di secondi indicato da **P**.
35. Retrarre l'asse **Z** alla velocità di avanzamento attuale per liberare **Z**.

---
#### G90, G91 Modalità Distanza  

- **G90** - **Modalità di distanza assoluta**  
	- In modalità di distanza assoluta, i numeri degli assi (X, Y, Z, A, B, C, U, V, W) solitamente rappresentano posizioni in termini del sistema di coordinate attualmente attivo. Qualsiasi eccezione a questa regola è descritta esplicitamente nella sezione G80 G89.

- **G91** - **Modalità di distanza incrementale**  
	- In modalità di distanza incrementale, i numeri degli assi solitamente rappresentano incrementi rispetto alla coordinata corrente.

**Esempio G90**

```gcode
G90 (imposta la modalità di distanza assoluta)
G0 X2.5 (movimento rapido verso la coordinata X2.5, includendo eventuali offset in vigore)
```

**Esempio G91**

```gcode
G91 (imposta la modalità di distanza incrementale)
G0 X2.5 (movimento rapido di 2.5 dalla posizione corrente lungo l'asse X)
```

Vedi la sezione **G0** per maggiori informazioni.

---
#### G90.1, G91.1 Modalità Distanza per Archi  

- `G90.1` - Modalità di Distanza Assoluta per gli Offset **I**, **J** & **K**.  
	- Quando **G90.1** è in vigore, **I** e **J** devono essere specificati con **G2/3** per il piano **XY** o **J** e **K** per il piano **XZ**, altrimenti si genera un errore.

- `G91.1` - Modalità di Distanza Incrementale per gli Offset **I**, **J** & **K**.  
	- **G91.1** ripristina il comportamento predefinito per **I**, **J** & **K**.

---
#### G92 Offset del Sistema di Coordinate  

```gcode
G92 assi  
```

*Avvertenza*  
*Utilizzare **G92** solo dopo che la macchina è stata posizionata nel punto desiderato.*

**G92** fa in modo che il punto corrente abbia le coordinate desiderate (senza movimento), dove le parole asse contengono i numeri degli assi desiderati.  
Tutte le parole asse sono opzionali, tranne che almeno una deve essere usata.  
Se una parola asse non viene usata per un dato asse, l'offset per quell'asse sarà zero.

Quando viene eseguito **G92**, le origini di tutti i sistemi di coordinate si spostano.  
Si spostano in modo tale che il valore del punto controllato corrente, nel sistema di coordinate attualmente attivo, diventi il valore specificato.  
Tutte le origini del sistema di coordinate (**G53**-**G59.3**) vengono offsettate di questa stessa distanza.

Essere in modalità di distanza incrementale (**G91** anziché **G90**) non ha alcun effetto sull'azione di **G92**.

Gli offset **G92** possono già essere in vigore quando viene eseguito **G92**.  
In tal caso, l'offset viene sostituito con un nuovo offset che fa sì che il punto corrente diventi il valore specificato.

Si genera un errore se mancano tutte le parole asse.

LinuxCNC memorizza gli offset **G92** e li riutilizza alla successiva esecuzione di un programma.  
Per evitare ciò, è possibile programmare un **G92.1** (per cancellarli) o programmare un **G92.2** (per rimuoverli - essi vengono comunque memorizzati).

*Nota*  
*Il comando **G52** può essere usato anche per cambiare questo offset; vedi la sezione Offsets per maggiori dettagli su **G92** e **G52** e su come interagiscono.*

Vedi la sezione [Sistema di Coordinate]() per una panoramica dei sistemi di coordinate.
Vedi la sezione [Parametri]() per maggiori informazioni.

---
#### G92.1, G92.2 Reimposta gli Offset G92

- `G92.1` - annulla gli offset **G92** e reimposta i parametri a zero.
- `G92.2` - annulla gli offset **G92** ma mantiene disponibili i parametri preselezionati.

*Nota*  
***G92.1** cancella solo gli offset **G92**; per modificare gli offset del sistema di coordinate **G53-G59.3** nel G-code usare **G10 L2** o **G10 L20**.*

---
#### G93, G94, G95 Modalità di Velocità di Avanzamento

###### G93 - Modalità a tempo inverso. 
In modalità a tempo inverso, una parola **F** indica che il movimento deve essere completato in \[uno diviso per il numero F] minuti. Ad esempio, se il numero **F** è 2.0, il movimento deve essere completato in mezzo minuto.

Quando la modalità a tempo inverso è attiva, una parola F deve apparire su ogni riga che contiene un movimento **G1**, **G2** o **G3**, e una parola **F** su una riga che non contiene **G1**, **G2** o **G3** viene ignorata. Essere in modalità a tempo inverso non influisce sui movimenti **G0** (movimento rapido).

###### G94 - Modalità in unità per minuto. 
In modalità in unità per minuto, una parola F viene interpretata nel senso che il punto controllato deve muoversi a un certo numero di pollici al minuto, millimetri al minuto o gradi al minuto, a seconda delle unità di lunghezza usate e degli assi in movimento.

###### G95 - Modalità in Unità per Rivoluzione. 
In modalità in unità per rivoluzione, una parola F viene interpretata nel senso che il punto controllato deve muoversi di un certo numero di pollici per rivoluzione del mandrino, a seconda delle unità di lunghezza usate e degli assi in movimento. **G95** non è adatto per la filettatura; per la filettatura usare **G33** o **G76**. **G95** richiede che spindle.N.speed-in sia collegato. Il mandrino effettivo a cui il feed è sincronizzato viene scelto tramite il parametro ****$.

Si genera un errore se:
- Inverse time feed mode è attiva e una riga con **G1**, **G2** o **G3** (esplicitamente o implicitamente) non contiene una parola **F**.
- Non viene specificato un nuovo feed rate dopo il passaggio a **G94** o **G95**.

---
#### G96, G97 Modalità di Controllo del Mandrino

```gcode
G96 <D-> S- <$-> (Constant Surface Speed Mode)  
G97 S- <$-> (RPM Mode)  
```

- **D** - velocità massima di rotazione (RPM), opzionale
- **S** - velocità del mandrino
- **$** - il mandrino di cui verrà variata la velocità, opzionale.
	- **G96 S- \<D->** - seleziona una velocità superficiale costante pari a S:
		- in piedi al minuto se è in vigore G20,
		- oppure in metri al minuto se è in vigore G21.

Quando si usa **G96**, assicurarsi che **X**0 nel sistema di coordinate corrente (inclusi offset e lunghezze utensile) sia il centro di rotazione, altrimenti LinuxCNC non fornirà la velocità superficiale desiderata. **G96** non è influenzato dalla modalità raggio o diametro.

Per ottenere la modalità CSS sui mandrini selezionati, programmare successive istruzioni **G96** per ciascun mandrino prima di emettere **M3**.
- **G97** seleziona la modalità in RPM.

**Esempio G96**  

```gcode
G96 D2500 S250 (imposta CSS con un rpm massimo di 2500 e una velocità superficiale di 250)
```

Si genera un errore se:
- **S** non è specificato con **G96**
- Viene specificato un movimento di feed in modalità **G96** mentre il mandrino non sta ruotando

---
#### G98, G99 Livello di Ritorno del Ciclo Preimpostato

Quando il mandrino si ritrae durante i cicli preimpostati, ci sono due opzioni per il modo in cui avviene la retrazione:

- **G98** - ritrae fino alla posizione in cui l'asse si trovava appena prima che iniziasse questa serie di uno o più cicli preimpostati contigui.
- **G99** - ritrae fino alla posizione specificata dalla parola R del ciclo preimpostato.

Programmare un **G98** e il ciclo preimpostato userà la posizione **Z** precedente al ciclo preimpostato come posizione di ritorno **Z** se essa è superiore al valore **R** specificato nel ciclo. Se è inferiore, verrà usato il valore **R**. La parola **R** ha significati differenti in modalità di distanza assoluta e in modalità di distanza incrementale.

**Esempio G98**

```gcode
G0 X1 Y2 Z3  
G90 G98 G81 X4 Y5 Z-0.6 R1.8 F10  
```

Il **G98** della seconda riga sopra significa che il movimento di ritorno sarà al valore di **Z** indicato nella prima riga, poiché esso è superiore al valore R specificato.

Il piano iniziale (**G98**) viene resettato ogni volta che la modalità di movimento a ciclo viene abbandonata, sia esplicitamente (**G80**) sia implicitamente (qualsiasi codice di movimento che non sia un ciclo). Il passaggio da una modalità di ciclo all'altra (ad esempio da **G81** a **G83**) NON resetta il piano iniziale. È possibile passare tra **G98** e **G99** durante una serie di cicli.

---
---
## Codici O e Parametri

#### Utilizzo dei Codici O  

I codici O forniscono il controllo del flusso nei programmi NC. Ogni blocco ha un numero associato, che è il numero usato dopo la lettera O. È necessario prestare attenzione ad abbinare correttamente i numeri O. I codici O utilizzano la lettera O, e non il numero zero, come primo carattere del numero, ad esempio O100 o o100.

---
#### Commenti  

I commenti sulla stessa riga della parola O non dovrebbero essere usati, poiché il comportamento potrebbe cambiare in futuro.

Il comportamento è indefinito se:

- Lo stesso numero viene usato per più di un blocco.
- Altre parole vengono usate su una riga con una parola O.
- I commenti vengono usati su una riga con una parola O.

*Nota*  
*Utilizzare la "o" minuscola rende più facile distinguerla da uno 0 che potrebbe essere stato digitato erroneamente. Ad esempio, o100 è più facile da riconoscere rispetto a O100, che potrebbe essere confuso con 0.*

---
#### Sottoprogrammi  

I sottoprogrammi iniziano con `Onnn sub` e terminano con `Onnn endsub`. Le righe tra `Onnn sub` e `Onnn endsub` non vengono eseguite fino a quando il sottoprogramma non viene chiamato con `Onnn call`. Ogni sottoprogramma deve utilizzare un numero univoco.

**Esempio di Sottoprogramma**

```gcode
o100 sub
  G53 G0 X0 Y0 Z0 (rapid move to machine home)
o100 endsub
```

(il sottoprogramma viene chiamato)

```gcode
o100 call
M2
```

Consulta le sezioni G53, G0 e M2 per maggiori informazioni.

---
#### O- Return

All'interno di un sottoprogramma, può essere eseguito `O- return.` Questo ritorna immediatamente al codice chiamante, come se fosse stato incontrato `O- endsub.`

**Esempio di O- Return**

```gcode
o100 sub
  (test if parameter #2 is greater than 5)
  o110 if [#2 GT 5]
    (return to top of subroutine if test is true)
    o100 return
  o110 endif
    (this only gets executed if parameter #2 is not greater than 5)
    (DEBUG, parameter 1 is [#1])
o100 endsub
```

Consulta le sezioni [[Operatori Binari]] e [[Parametri]] per maggiori informazioni.

---
#### O- Call  

`O- Call` accetta fino a 30 argomenti opzionali, che vengono passati al sottoprogramma come #1, #2, …, \#N. I parametri da \#N+1 a #30 assumono lo stesso valore del contesto chiamante. Al ritorno dal sottoprogramma, i valori dei parametri da #1 a #30 (indipendentemente dal numero di argomenti) verranno ripristinati ai valori precedenti alla chiamata. I parametri #1 - #30 sono locali al sottoprogramma.

Poiché "1 2 3" viene interpretato come il numero 123, i parametri devono essere racchiusi tra parentesi quadre. Il seguente esempio chiama un sottoprogramma con 3 argomenti:

**Esempio di O- Call**

```
o100 sub
  (test if parameter #2 is greater than 5)
  o110 if [#2 GT 5]
    (return to top of subroutine if test is true)
    o100 return
  o110 endif
    (this only gets executed if parameter #2 is not greater than 5)
    (DEBUG, parameter 1 is [#1])
    (DEBUG, parameter 3 is [#3])
o100 endsub

o100 call [100] [2] [325]
```

I corpi dei sottoprogrammi non possono essere annidati. Possono essere chiamati solo dopo essere stati definiti. Possono essere chiamati da altre funzioni e possono richiamare se stessi in maniera ricorsiva, se ciò ha senso. Il livello massimo di annidamento dei sottoprogrammi è 10.

I sottoprogrammi possono modificare il valore dei parametri superiori a #30 e tali modifiche saranno visibili al codice chiamante. I sottoprogrammi possono anche modificare il valore dei parametri globali con nome (cioè, i parametri i cui nomi iniziano con il carattere underscore "_").

---
#### Numerazione  

I codici O numerati devono avere un numero univoco per ogni sottoprogramma.

**Esempio di Numerazione**  

```gcode
(la parte iniziale di o100)
o100 sub
(nota che il blocco if-endif utilizza un numero diverso)  
	(la parte iniziale di o110)
	o110 if [#2 GT 5]
	(some code here)
(la fine di o110)
o110 endif
	(altro codice)  
(la fine di o100)
o100 endsub
```

---
#### Programmi Numerati in Stile Fanuc  

I programmi numerati (sia principali che sottoprogrammi), il codice M98 per la chiamata e M99 per il ritorno, e le rispettive differenze semantiche sono un'alternativa alle sottoprocedure RS274/NGC descritte sopra, fornita per la compatibilità con Fanuc e altri controllori macchina.

*Nota*  
*Le definizioni e le chiamate dei programmi principali e dei sottoprogrammi numerati differiscono dallo stile tradizionale rs274ngc sia nella sintassi che nell'esecuzione. Per ridurre la possibilità di confusione, l'interprete genererà un errore se le definizioni di uno stile vengono mescolate con le chiamate di un altro.*

**Programma Sottoprogramma Numerato – Esempio Semplice** 
```gcode
o1 (Example 1)    ; Programma Principale 1, "Example 1"
M98 P100          ; Chiamata del Sottoprogramma 100
M30               ; Fine del Programma Principale
o100              ; Inizio del Sottoprogramma 100
  G53 G0 X0 Y0 Z0 ; Movimento Rapido verso l'Origine Macchina
M99               ; Ritorno dal Sottoprogramma 100
```

**o1 (Title)**
Il blocco opzionale all'inizio del programma principale assegna al programma principale il numero 1. Alcuni controllori trattano un commento opzionale tra parentesi subito dopo come titolo del programma, “Example 1” in questo esempio, ma ciò non ha un significato speciale nell'interprete RS274NGC.

**M98 P- \<L->**
Chiamata di un sottoprogramma numerato. Il blocco `M98 P100` è analogo alla tradizionale sintassi di chiamata `o100`, ma può essere usato solo per chiamare un sottoprogramma numerato definito successivamente con `o100…M99`. Una parola L opzionale specifica il numero di ripetizioni del ciclo.

**M30**
Il programma principale deve essere terminato con `M02` o `M30` (o `M99`; vedi sotto).

**O- Inizio Definizione del Sottoprogramma**  
Marca l'inizio di una definizione di sottoprogramma numerato. Il blocco `O100` è simile a `o100 sub`, tranne che deve essere posizionato nel file dopo il blocco di chiamata `M98 P100`.

**M99 Ritorno dal Sottoprogramma Numerato**  
Il blocco `M99` è analogo alla tradizionale sintassi `o100 endsub`, ma può terminare solo un programma numerato (ad esempio, `o100` in questo esempio), e non può terminare un sottoprogramma che inizia con la sintassi `o100 sub`.

La chiamata al sottoprogramma con `M98` differisce dalla chiamata O in RS274NGC nei seguenti modi:

- Il sottoprogramma numerato deve seguire la chiamata `M98` nel file di programma. L'interprete genererà un errore se il sottoprogramma precede il blocco di chiamata.
- I parametri `#1, #2, …, #30` sono globali e accessibili nei sottoprogrammi numerati, analogamente ai parametri di numero superiore nelle chiamate in stile tradizionale. Le modifiche a questi parametri all'interno di un sottoprogramma sono modifiche globali e persisteranno dopo il ritorno dal sottoprogramma.
- Le chiamate ai sottoprogrammi `M98` non hanno un valore di ritorno.
- I blocchi di chiamata `M98` possono contenere una parola L opzionale che specifica il conteggio delle ripetizioni. Senza la parola L, il sottoprogramma verrà eseguito una sola volta (equivalente a `M98 L1`). Un blocco `M98` L0 non eseguirà il sottoprogramma.

In rari casi, il codice `M99` può essere usato per terminare il programma principale, dove indica un programma infinito. Quando l'interprete raggiunge un `M99` nel programma principale, salta all'inizio del file e riprende l'esecuzione dalla prima riga. Un esempio di uso di un programma infinito è in un ciclo di riscaldamento della macchina; un blocco di eliminazione alla fine del programma/`M30 `può essere usato per fermare il ciclo in un punto definito quando l'operatore è pronto.

**Programma Sottoprogramma Numerato – Esempio Completo**

```
O1                             ; Programma Principale 1
  #1 = 0
  (PRINT,X MAIN BEGIN:  1=#1)
  M98 P100 L5                  ; Chiamata del Sottoprogramma 100
  (PRINT,X MAIN END:  1=#1)
M30                            ; Fine del Programma Principale

O100                           ; Sottoprogramma 100
  #1 = [#1 + 1]
  M98 P200 L5                  ; Chiamata del Sottoprogramma 200
  (PRINT,>> O100:  #1)
M99                            ; Ritorno dal Sottoprogramma 100

O200                           ; Sottoprogramma 200
  #1 = [#1 + 0.01]
  (PRINT,>>>> O200:  #1)
M99                            ; Ritorno dal Sottoprogramma 200
```

In questo esempio, il parametro #1 viene inizializzato a 0. Il sottoprogramma `O100` viene chiamato cinque volte in un loop. Annidato all'interno di ogni chiamata a `O100`, il sottoprogramma `O200` viene chiamato cinque volte in un loop, per un totale di 25 volte.

Nota che il parametro #1 è globale. Alla fine del programma principale, dopo gli aggiornamenti all'interno di `O100` e `O200`, il suo valore sarà pari a 5.25.

---
#### Cicli While  

Il ciclo "while" ha due strutture: while/endwhile e do/while. In entrambi i casi, il ciclo viene interrotto quando la condizione while valuta falso. La differenza risiede nel momento in cui viene eseguito il test. Il ciclo do/while esegue il codice all'interno del ciclo e poi controlla la condizione di test. Il ciclo while/endwhile esegue prima il test.

**Esempio While Endwhile**  
(disegna una forma a dente di sega)

```gcode
G0 X1 Y0          (muovi alla posizione di partenza)
#1 = 0            (assegna al parametro #1 il valore 0)
F25               (imposta un feed rate)
o101 while [#1 LT 10]
  G1 X0
  G1 Y[#1/10] X1
  #1 = [#1+1]    (incrementa il contatore di test)
o101 endwhile
M2                (fine programma)
```

**Esempio Do While**

```gcode
#1 = 0            (assegna al parametro #1 il valore 0)
o100 do
  (debug, parameter 1 = #1)
  o110 if [#1 EQ 2]
    #1 = 3        (assegna il valore 3 al parametro #1)
    (msg, #1 has been assigned the value of 3)
    o100 continue (salta all'inizio del ciclo)
  o110 endif
  (some code here)
  #1 = [#1 + 1]   (incrementa il contatore di test)
o100 while [#1 LT 3]
(msg, Loop Done!)
M2
```

All'interno di un ciclo while, `O- break` esce immediatamente dal ciclo, e `O- continue` salta immediatamente alla successiva valutazione della condizione while. Se la condizione è ancora vera, il ciclo riprende dall'inizio.

---
#### Cicli If  

La struttura condizionale "if" consiste in un gruppo di istruzioni con lo stesso numero O che inizia con "if" e termina con "endif". Possono essere presenti condizioni opzionali "elseif" ed "else" tra l'inizio "if" e la fine "endif".

Se la condizione "if" risulta vera, il gruppo di istruzioni che segue l'if fino alla linea condizionale successiva viene eseguito.

Se la condizione "if" risulta falsa, le condizioni "elseif" vengono valutate in ordine fino a quando una risulta vera. Se una condizione "elseif" è vera, vengono eseguite le istruzioni successive all'"elseif" fino alla linea condizionale successiva. Se nessuna delle condizioni "if" o "elseif" risulta vera, vengono eseguite le istruzioni successive all'"else". Quando una condizione viene valutata come vera, nessuna condizione successiva viene valutata nel gruppo.

**Esempio If Endif**  
(se il parametro #31 è uguale a 3, imposta S2000)

```gcode
o101 if [#31 EQ 3]
  S2000
o101 endif
```

**Esempio If ElseIf Else EndIf**  
(se il parametro #2 è maggiore di 5, imposta F100)

```gcode
o102 if [#2 GT 5]
  F100
o102 elseif [#2 LT 2]
  (else if, se il parametro #2 è minore di 2, imposta F200)
  F200
  (se il parametro #2 è tra 2 e 5, imposta F150)
o102 else
  F150
o102 endif
```

È possibile testare più condizioni tramite le istruzioni "elseif" fino a quando il percorso "else" viene eseguito se tutte le condizioni precedenti sono false:

**Esempio If Elseif Else Endif**  
(se il parametro #2 è maggiore di 5, imposta F100)

```gcode
O102 if [#2 GT 5]
  F100
  (altrimenti, se il parametro #2 è minore di 2, imposta F200)
O102 elseif [#2 LT 2]
  F20
  (se il parametro #2 è tra 2 e 5)
O102 else
  F200
O102 endif
```

---
#### Repeat  

Il comando "repeat" esegue le istruzioni all'interno del blocco repeat/endrepeat per il numero specificato di volte. L'esempio mostra come si potrebbe fresare una serie di forme diagonali a partire dalla posizione corrente.

**Esempio con repeat**  
(Fresatura di 5 forme diagonali)

```gcode
G91                (Modalità Incrementale)
o103 repeat [5]
... (inserire codice di fresatura qui)
G0 X1 Y1          (movimento diagonale verso la posizione successiva)
o103 endrepeat
G90                (Modalità Assoluta)
```

4. Indirection  
    Il numero O può essere dato da un parametro e/o da un calcolo.

**Esempio di Indirection**

```gcode
o[#101+2] call
```

Computare valori nelle parole O  
Per maggiori informazioni sul calcolo dei valori, vedere le seguenti sezioni:

- Parametri
- Espressioni
- Operatori Binari
- Funzioni

---
#### Calling Files  

Per chiamare un file separato contenente un sottoprogramma, denominare il file come la chiamata e includere "sub" ed "endsub" nel file. Il file deve trovarsi nella directory indicata da PROGRAM_PREFIX o SUBROUTINE_PATH nel file INI. Il nome del file può includere solo lettere minuscole, numeri, trattini e underscore. Un file di sottoprogramma nominato può contenere una sola definizione di sottoprogramma.

**Esempio di File Nominato**

```gcode
o<myfile> call
```

**Esempio di File Numerato**

```gcode
o123 call
```

Nel file chiamato, è necessario includere "oxxx sub" ed "oxxx endsub" e il file deve essere valido.

**Esempio di File Chiamato**  
(nome del file myfile.ngc)

```gcode
o<myfile> sub
  (code here)
o<myfile> endsub
M2
```

**Nota**  
I nomi dei file sono composti solo da lettere minuscole, quindi o viene convertito in o dall'interprete. Per ulteriori informazioni sul percorso di ricerca e sulle opzioni per il percorso di ricerca, consultare la sezione di configurazione del file INI.

---
#### Valori di Ritorno delle Sottoprocedure  

Le sottoprocedure possono, facoltativamente, restituire un valore mediante un'espressione opzionale in una dichiarazione "endsub" o "return".

**Esempio di Valore di Ritorno**

```gcode
o123 return [#2 *5]
...
o123 endsub [3 * 4]
```

Il valore di ritorno di una sottoprocedura viene memorizzato nel parametro predefinito nominato `<_value>`, e il parametro predefinito `<_value_returned>` viene impostato a 1 per indicare che è stato restituito un valore. Entrambi i parametri sono globali e vengono azzerati appena prima della prossima chiamata di sottoprocedura.

---
#### Errori  

Le seguenti istruzioni causano un messaggio di errore e l'arresto dell'interprete:

- un "return" o "endsub" non all'interno di una definizione di sottoprogramma
- un'etichetta su "repeat" definita altrove
- un'etichetta su "while" definita altrove e non riferita a un "do"
- un'etichetta su "if" definita altrove
- un'etichetta indefinita su "else" o "elseif"
- un'etichetta su "else", "elseif" o "endif" che non punta a un "if" corrispondente
- un'etichetta su "break" o "continue" che non punta a un "while" o "do" corrispondente
- un'etichetta su "endrepeat" o "endwhile" che non punta a un "repeat" o "while" corrispondente

Per rendere questi errori dei warning non fatali su stderr, impostare il bit 0x20 nell'opzione mask [RS274NGC]FEATURE= nel file ini.

## Codici M e Parametri

#### M0, M1 Pausa del Programma

- `M0` - interrompe temporaneamente l'esecuzione di un programma in corso. LinuxCNC rimane in Modalità Auto, quindi MDI e altre azioni manuali non sono abilitate. Premendo il pulsante di ripresa, il programma riprenderà dalla linea successiva.
    
- `M1` - interrompe temporaneamente l'esecuzione di un programma in corso se l'interruttore di stop opzionale è attivo. LinuxCNC rimane in Modalità Auto, quindi MDI e altre azioni manuali non sono abilitate. Premendo il pulsante di ripresa, il programma riprenderà dalla linea successiva.
    

*Nota*  
*È possibile programmare M0 e M1 in modalità MDI, ma l'effetto probabilmente non sarà visibile, poiché il comportamento normale in modalità MDI è di fermarsi dopo ogni linea di input.*

---
#### M2, M30 Fine del Programma

- `M2` - termina il programma. Premendo "Cycle Start", il programma riprenderà dall'inizio del file.
    
- `M30` - scambia i carrelli del pallet e termina il programma. Premendo "Cycle Start", il programma riprenderà dall'inizio del file.
    

Entrambi questi comandi hanno i seguenti effetti:
- Cambio dalla modalità Auto alla modalità MDI.
- Gli offset di origine vengono impostati al valore predefinito (come **G54**).
- Il piano selezionato è impostato sul piano XY (come **G17**).
- La modalità di distanza è impostata in modalità assoluta (come **G90**).
- La modalità di velocità di avanzamento è impostata su unità per minuto (come **G94**).
- Gli override di avanzamento e velocità sono impostati su ON (come **M48**).
- La compensazione utensile è disattivata (come **G40**).
- Il mandrino viene fermato (come **M5**).
- La modalità di movimento corrente è impostata su avanzamento (come **G1**).
- Il raffreddamento è disattivato (come **M9**).

*Nota*  
*Le righe di codice successive a M2/M30 non verranno eseguite. Premendo "Cycle Start", il programma riprenderà dall'inizio del file.*

*Avviso*  
*L'utilizzo di % per racchiudere il codice G non ha lo stesso effetto della fine del programma. Consulta la sezione sui Requisiti del File per maggiori informazioni su ciò che l'uso di % non fa.*

---
#### M60 Pausa Cambio Pallet

- `M60` - scambia i carrelli del pallet e poi interrompe temporaneamente l'esecuzione del programma (indipendentemente dall'impostazione dell'interruttore di stop opzionale). Premendo il pulsante di avvio ciclo, il programma riprenderà dalla linea successiva.

---
#### M3, M4, M5 Controllo Mandrino

- `M3 <$-> `- avvia il mandrino selezionato in senso orario alla velocità S.
- `M4 <$-> `- avvia il mandrino selezionato in senso antiorario alla velocità S.
- `M5 <$->` - ferma il mandrino selezionato.

Utilizzare **\$** per operare su mandrini specifici. Se **$** è omesso, i comandi si riferiranno al mandrino 0. Usa **\$**-1 per operare su tutti i mandrini attivi.

```gcode
S100 $0
S200 $1
S300 $2
M3 $-1
```

Questo avvierà i mandrini 0, 1 e 2 simultaneamente a velocità diverse.

```gcode
M4 $1
```

Inverterà il mandrino 1, lasciando gli altri in rotazione normale.

```gcode
M5 $2
```

Questo fermerà il mandrino 2, lasciando gli altri in rotazione.

Se **$** è omesso, il comportamento è come per una macchina a mandrino singolo.

---
#### M6 Cambio Utensile

###### Cambio Utensile Manuale

Se la modalità di cambio utensile manuale è attiva, **M6** fermerà il mandrino e chiederà all'utente di cambiare l'utensile in base all'ultimo numero **T** programmato. Per maggiori informazioni, vedi la sezione **Cambio Utensile Manuale**.

###### Cambio Utensile Automatico

Per cambiare un utensile nel mandrino da quello attualmente montato a quello selezionato più recentemente (tramite una parola **T** - vedi sezione [[Selezione Utensile]]), programma **M6**. Quando il cambio utensile è completato:
- Il mandrino verrà fermato.
- L'utensile selezionato (da una parola **T** sulla stessa riga o in qualsiasi riga dopo l'ultimo cambio utensile) sarà nel mandrino.
- Se l'utensile selezionato non era già nel mandrino, l'utensile precedente (se presente) sarà rimesso nel caricatore utensili.

---
#### **M7, M8, M9 Controllo Raffreddamento**

- `M7` - attiva il raffreddamento a nebbia.
- `M8` - attiva il raffreddamento a pioggia.
- `M9` - disattiva sia M7 che M8.

---
#### **M19 Orientamento Mandrino**

```gcode
M19 R- Q- [P-] [$-]  
```
- **R**: Posizione di rotazione da raggiungere (0°-360°)  
- **Q**: Numero di secondi da attendere finché l'orientamento non è completato. Se **spindle.N.is-oriented** non diventa vero entro il tempo di attesa **Q**, si verifica un errore.  
- **P**: Direzione in cui ruotare per raggiungere la posizione.
	- 0: Ruotare per il movimento angolare più piccolo (default)
	- 1: Ruotare sempre in senso orario (come M3)
	- 2: Ruotare sempre in senso antiorario (come M4)  
- **$**: Il mandrino da orientare

---
#### **M48, M49 Controllo Override di Velocità e Avanzamento**

- `M48` - abilita i controlli di override della velocità del mandrino e della velocità di avanzamento.
- `M49` - disabilita entrambi i controlli.

Questi comandi accettano anche un parametro opzionale **$** per determinare su quale mandrino operare.

---
#### **M50 Controllo Override di Avanzamento**

- `M50 \<P1>` - abilita il controllo dell'override di avanzamento. Il parametro **P1** è opzionale.
- `M50 P0` - disabilita il controllo dell'override di avanzamento.

---
#### **M51 Controllo Override di Velocità Mandrino**

- `M51 <P1> <$->` - abilita il controllo dell'override della velocità del mandrino per il mandrino selezionato. Il parametro **P1** è opzionale.
- `M51 P0 <$->` - disabilita il controllo dell'override di velocità del mandrino.

Mentre è disabilitato, l'override della velocità del mandrino non avrà alcuna influenza, e la velocità del mandrino sarà esattamente quella specificata nel valore del codice S (come descritto nella sezione [[Velocità del Mandrino]]).

---
#### **M52 Controllo Avanzamento Adattivo**

- `M52 <P1>` - attiva un avanzamento adattivo. Il parametro **P1** è opzionale.
- `M52 P0` - disattiva l'avanzamento adattivo.

---
#### **M53 Controllo Stop Avanzamento**

- `M53 <P1>` - abilita l'interruttore di stop avanzamento. Il parametro **P1** è opzionale. Quando attivo, l'avanzamento viene interrotto tramite il controllo di stop avanzamento.
- `M53 P0` - disabilita l'interruttore di stop avanzamento. Il pin **motion.feed-hold** non influenzerà l'avanzamento quando M53 non è attivo.

---
#### M61 Impostare lo Strumento Corrente  

- `M61 Q-` - cambia il numero dello strumento corrente mentre si è in modalità MDI o Manuale senza cambio di utensile. Un esempio d'uso è quando si accende LinuxCNC con uno strumento già presente nel mandrino, e si può impostare il numero di tale utensile senza fare un cambio di utensile.

*Avviso*  
*L'offset della lunghezza utensile non viene modificato da **M61**, utilizzare **G43** dopo **M61** per cambiare l'offset della lunghezza utensile.*  

Si genera un errore se:
- Q- non è maggiore o uguale a 0

---
#### M62 - M65 Controllo Uscita Digitale  

- `M62 P-` - accende l'uscita digitale sincronizzata con il movimento.
- `M63 P-` - spegne l'uscita digitale sincronizzata con il movimento.
- `M64 P-` - accende l'uscita digitale immediatamente.
- `M65 P-` - spegne l'uscita digitale immediatamente.

La parola **P-** specifica il numero dell'uscita digitale. Il valore di **P-** va da 0 al valore predefinito di 3. Consulta la sezione [[Movimento]] per ulteriori dettagli.

I comandi **M62** e **M63** vengono messi in coda. I comandi successivi che si riferiscono allo stesso numero di uscita sovrascriveranno i settaggi precedenti. Più modifiche dell'uscita possono essere specificate emettendo più comandi **M62**/**M63**.

La modifica effettiva delle uscite specificate avviene all'inizio del comando di movimento successivo. Se non c'è alcun comando di movimento successivo, le modifiche in coda non avranno effetto. È meglio programmare sempre un comando di movimento **G** (**G0**, **G1**, ecc.) subito dopo **M62**/**M63**.

**M64** e **M65** avvengono immediatamente appena ricevuti dal controller di movimento. Non sono sincronizzati con il movimento e interromperanno la fusione dei movimenti.

---
#### M66 Attendere un Input 

```gcode
M66 P- | E- <L->
```

- **P-** - specifica il numero dell'input digitale da 0 a 3 
- **E-** - specifica il numero dell'input analogico da 0 a 3 
- **L-** - specifica il tipo di modalità di attesa.
	- Modalità 0: IMMEDIATO - nessuna attesa, ritorna immediatamente. Il valore corrente dell'input viene memorizzato nel parametro #5399
	- Modalità 1: RIALZO - attende che l'input selezionato generi un evento di rialzo.
	- Modalità 2: CALO - attende che l'input selezionato generi un evento di calo.
	- Modalità 3: ALTO - attende che l'input selezionato raggiunga lo stato ALTO.
	- Modalità 4: BASSO - attende che l'input selezionato raggiunga lo stato BASSO.
- Q- - specifica il timeout in secondi per l'attesa. Se il timeout viene superato, l'attesa viene interrotta e la variabile #5399 conterrà il valore -1. Il valore Q viene ignorato se la parola L è zero (IMMEDIATO). Un valore Q di zero è un errore se la parola L è diversa da zero.
- La modalità 0 è l'unica consentita per un input analogico.

**Esempio M66**  

```gcode
M66 P0 L3 Q5 (attende fino a 5 secondi che l'input digitale 0 venga attivato)
``` 

**M66** - Attendere un input ferma l'esecuzione del programma finché non si verifica l'evento selezionato (o il timeout programmato).

È un errore programmare **M66** con sia una parola **P** che **E** (selezionando sia un input analogico che uno digitale). In LinuxCNC questi input non sono monitorati in tempo reale e pertanto non devono essere usati in applicazioni dove il tempo è critico.

---
#### M67 Uscita Analogica, Sincronizzata  

```gcode
M67 E- Q-  
```

- **M67** - imposta un'uscita analogica sincronizzata con il movimento.
- **E-** - numero dell'uscita, da 0 a 3 (regolabile tramite il parametro motmod num_aio)
- **Q-** - valore da impostare (impostare su 0 per spegnere).

Il cambiamento effettivo delle uscite specificate avverrà all'inizio del comando di movimento successivo. Se non c'è un comando di movimento successivo, le modifiche in coda non avverranno. È meglio programmare un comando di movimento G (G0, G1, ecc.) subito dopo M67. M67 funziona allo stesso modo di M62-M63.

---
#### M68 Uscita Analogica, Immediata 

```gcode
M68 E- Q-  
```

- **M68** - imposta un'uscita analogica immediatamente.
- **E-** - numero dell'uscita, da 0 a 3 (regolabile tramite il parametro motmod num_aio)
- **Q-** - valore da impostare (impostare su 0 per spegnere).

L'uscita M68 avviene immediatamente appena ricevuta dal controller di movimento. Non è sincronizzata con il movimento e interromperà la fusione dei movimenti. M68 funziona allo stesso modo di M64-M65.

---
#### M70 Salvataggio dello Stato Modale 

Per salvare esplicitamente lo stato modale (stato delle impostazioni correnti) al livello corrente di chiamata, programmate M70. Una volta che lo stato modale è stato salvato con M70, può essere ripristinato esattamente a quello stato eseguendo un M72.

Una coppia di istruzioni M70 e M72 viene solitamente utilizzata per proteggere un programma contro cambiamenti modali accidentali all'interno di sottoprogrammi.

Stato Salvato da M70 Lo stato salvato comprende:
- Impostazioni correnti di G20/G21 (imperiale/metriche)
- Piano selezionato (G17/G18/G19 G17.1,G18.1,G19.1)
- Stato della compensazione utensile (G40,G41,G42,G41.1,G42.1)
- Modalità distanza - relativa/assoluta (G90/G91)
- Modalità avanzamento (G93/G94,G95)
- Sistema di coordinate corrente (G54-G59.3)
- Stato della compensazione lunghezza utensile (G43,G43.1,G49)
- Modalità di retrazione (G98,G99)
- Modalità del mandrino (G96-css o G97-RPM)
- Modalità distanza arco (G90.1, G91.1)
- Modalità raggio/diametro tornio (G7,G8)
- Modalità controllo percorso (G61, G61.1, G64)
- Velocità e avanzamento correnti (valori F e S)
- Stato del mandrino (M3,M4,M5) - acceso/spento e direzione
- Stato nebbia (M7) e inondazione (M8)
- Override della velocità (M51) e dell'avanzamento (M50)
- Impostazioni avanzamento adattivo (M52)
- Impostazione pausa avanzamento (M53)

Nota che, in particolare, la modalità di movimento (G1 ecc.) NON viene ripristinata.

Livello di chiamata corrente significa:
- Esecuzione nel programma principale. Esiste una singola posizione di memorizzazione dello stato a livello del programma principale; se vengono eseguite più istruzioni M70 di seguito, solo lo stato più recentemente salvato verrà ripristinato quando viene eseguito un M72.
- Esecuzione all'interno di un sottoprogramma G-code. Lo stato salvato con M70 all'interno di un sottoprogramma si comporta esattamente come un parametro locale con nome - può essere riferito solo all'interno di questa invocazione del sottoprogramma con un M72 e quando il sottoprogramma esce, il parametro scompare.

Un'invocazione ricorsiva di un sottoprogramma introduce un nuovo livello di chiamata.

---
#### M71 Invalida lo Stato Modale Salvato 

Lo stato modale salvato con un M70 o da un M73 al livello di chiamata corrente viene invalidato (non può più essere ripristinato).

Un successivo M72 allo stesso livello di chiamata fallirà.

Se eseguito in un sottoprogramma che protegge lo stato modale tramite un M73, un successivo ritorno o endsub non ripristinerà lo stato modale.

L'utilità di questa funzione è dubbia. Non dovrebbe essere utilizzata come affidabile in quanto potrebbe essere eliminata.

---
#### M72 Ripristina lo Stato Modale 

Lo stato modale salvato con un codice M70 può essere ripristinato eseguendo un M72.

Il trattamento di G20/G21 è trattato in modo speciale poiché i feed vengono interpretati in modo diverso a seconda di G20/G21: se le unità di lunghezza (mm/in) stanno per essere cambiate dall'operazione di ripristino, 'M72' ripristinerà prima la modalità di distanza e poi tutti gli altri stati, inclusi i feed, per assicurarsi che il valore di feed sia interpretato nell'impostazione dell'unità corretta.

È un errore eseguire un M72 senza una precedente operazione di salvataggio M70 a quel livello.

---
#### M73 Salvataggio e Ripristino Automatico dello Stato Modale 

Per salvare lo stato modale all'interno di un sottoprogramma e ripristinarlo al termine del sottoprogramma o a qualsiasi percorso di ritorno, programmate M73.

Interrompere un programma in esecuzione in un sottoprogramma che contiene un'operazione M73 non ripristinerà lo stato.

Inoltre, la fine normale (M2) di un programma principale che contiene un M73 non ripristinerà lo stato.

---
#### M98 e M99 

L'interprete supporta i programmi principali e sottoprogrammi in stile Fanuc con i codici M98 e M99. Vedi [[Programmi in Stile Fanuc]].

23.1. Ripristino Selettivo dello Stato Modale Eseguire un M72 o ritornare da un sottoprogramma che contiene un M73 ripristinerà tutto lo stato modale salvato.

---
## Differenze con ISO RS274/NGC

#### Modifiche da RS274/NGC 
Differenze che cambiano il significato dei programmi RS274/NGC

**Posizione dopo un Cambio Utensile**  
In LinuxCNC, la macchina non torna alla sua posizione originale dopo un cambio utensile. Questa modifica è stata apportata perché il nuovo utensile potrebbe essere più lungo del vecchio, e il movimento verso la posizione originale della macchina potrebbe quindi lasciare la punta dell'utensile troppo bassa.

**I Parametri di Offset Sono in Unità del File INI**  
In LinuxCNC, i valori memorizzati nei parametri per le posizioni di "home" di G28 e G30, i sistemi di coordinate P1…P9, e l'offset G92 sono espressi in "unità del file INI". Questa modifica è stata apportata perché, altrimenti, il significato di una posizione cambiava a seconda che G20 o G21 fossero attivi quando venivano programmati G28, G30, G10 L2 o G92.3.

**Le Lunghezze/Diametri della Tabella Utensili Sono in Unità del File INI**  
In LinuxCNC, le lunghezze (offset) degli utensili e i diametri nella tabella utensili sono specificati esclusivamente in unità del file INI. Questa modifica è stata apportata perché, altrimenti, la lunghezza di un utensile e il suo diametro cambierebbero a seconda che G20 o G21 fossero attivi quando venivano attivate le modalità G43, G41, G42. Ciò rendeva impossibile eseguire G-code nelle unità non native della macchina, anche quando il G-code era semplice e ben formato (inizia con G20 o G21 e non cambia unità durante il programma), senza modificare la tabella utensili.

**G84, G87 Non Implementati**  
G84 e G87 non sono attualmente implementati, ma potrebbero essere aggiunti in una futura versione di LinuxCNC.

**G28, G30 con Parole Asse**  
Quando G28 o G30 vengono programmati con solo alcune parole asse, LinuxCNC muove solo gli assi nominati. Questo è comune su altri controlli macchina. Per muovere alcuni assi verso un punto intermedio e poi muovere tutti gli assi al punto predefinito, scrivere due righe di G-code:

```
G0 X- Y- (assi da muovere al punto intermedio)
G28 (muove tutti gli assi al punto predefinito)
```

---
#### Aggiunte a RS274/NGC  
Differenze che non cambiano il significato dei programmi RS274/NGC

**Codici di Filettatura G33, G76**  
Questi codici non sono definiti in RS274/NGC.

**G38.2**  
La punta della sonda non viene ritratta dopo un movimento G38.2. Questo movimento di retrazione potrebbe essere aggiunto in una futura versione di LinuxCNC.

**G38.3…G38.5**  
Questi codici non sono definiti in RS274/NGC.

**Codici O**  
Questi codici non sono definiti in RS274/NGC.

**Override M50…M53**  
Questi codici non sono definiti in RS274/NGC.

**M61..M66**  
Questi codici non sono definiti in RS274/NGC.

**G43, G43.1 – Lunghezze Utensile Negative**  
La specifica RS274/NGC afferma "ci si aspetta che" tutte le lunghezze utensile siano positive. Tuttavia, G43 funziona anche per lunghezze utensile negative.

**Utensili per Tornitura**  
La compensazione della lunghezza utensile G43 può compensare l'utensile sia nelle dimensioni X che Z. Questa funzione è particolarmente utile sui torni.

**Lunghezze Utensile Dinamiche**  
LinuxCNC permette la specifica di una lunghezza utensile calcolata tramite G43.1 I K.

**G41.1, G42.1**  
LinuxCNC permette la specifica di un diametro utensile e, se in modalità tornitura, l'orientamento nel G-code. Il formato è G41.1/G42.1 D L, dove D è il diametro e L (se specificato) è l'orientamento dell'utensile per tornitura.

**G43 Senza Parola H**  
In NGC questo non è consentito. In LinuxCNC, imposta gli offset di lunghezza per l'utensile attualmente caricato. Se non è caricato alcun utensile, si verifica un errore. Questa modifica è stata apportata affinché l'utente non debba specificare il numero utensile in due punti per ogni cambio utensile, ed è coerente con il modo in cui funzionano G41/G42 quando la parola D non è specificata.

**Assi U, V e W**  
LinuxCNC permette macchine con fino a 9 assi definendo un set aggiuntivo di 3 assi lineari noti come U, V e W.
