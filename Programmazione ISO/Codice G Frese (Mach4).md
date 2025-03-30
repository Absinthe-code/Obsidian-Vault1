Di seguito trovi la traduzione completa fino a pagina 5. La formattazione originale è stata mantenuta, inclusa la tabella presente a pagina 5. Al termine troverai il numero della pagina raggiunta.

---

**Copyright, Indice e Capitolo 1: Introduzione**

Copyright © 2014 Newfangled Solutions,  
Artsoft USA, Tutti i Diritti Riservati

I seguenti sono marchi registrati di Microsoft Corporation: Microsoft, Windows.  
Qualsiasi altro marchio utilizzato in questo manuale è di proprietà del rispettivo titolare.

**Indice**  
- Capitolo 1: Introduzione .............................................. Pag. 2  
- Glossario ............................................................ Pag. 3  
- Formato .............................................................. Pag. 4  
- Capitolo 2: Elenco dei Codici G .................................. Pag. 5  
- Descrizioni ed Esempi dei Codici G ........................ Pag. 7  
- Capitolo 3: Ciclidi Preimpostati ............................... Pag. 33  
  - Foratura .......................................................... Pag. 35  
  - Filettatura ....................................................... Pag. 40  
  - Scanalatura ......................................................... Pag. 43  
- Capitolo 4: Compensazione dell’utensile .................... Pag. 50  
- Capitolo 5: Elenco dei Codici M ................................. Pag. 56  
- Descrizioni dei Codici M ........................................ Pag. 56  

**Capitolo 1: Introduzione**  
Il codice G è un linguaggio di programmazione speciale che viene interpretato dalle macchine a Controllo Numerico Computerizzato (CNC) per creare movimenti e svolgere altre operazioni. Sebbene possa sembrare complesso e variare da macchina a macchina, le basi sono molto più semplici di quanto appaia e seguono, nella maggior parte dei casi, uno standard adottato dall’industria. Mach4 si è avvicinato notevolmente a questo standard.

Un punto importante da ricordare quando si legge questo manuale: il movimento della macchina verrà sempre descritto come il movimento dell’utensile rispetto al pezzo in lavorazione. In molte macchine il pezzo si muove su più assi rispetto all’utensile; tuttavia, il programma definirà sempre il movimento dell’utensile intorno al pezzo. Le direzioni degli assi seguono la regola della mano destra (vedi Figura A).

![[Pasted image 20250218225422.png]]

Figura A: Regola della mano destra

---
### Glossario

- **Blocco**: Una singola riga di codice G.  
- **Ciclo Preimpostato**: Ciclo complesso definito da un singolo blocco di codice.  
- **Dwell**: Pausa del programma con una durata specificata dal parametro “P” (in secondi).  
- **EOB (Fine Blocco)**: Obbligatorio alla fine di ogni blocco di codice G. In Mach4 corrisponde a un ritorno a capo.  
- **Velocità di Avanzamento (Feedrate)**: Velocità impostata con il comando F con cui un asse si muove.  
- **Gruppo**: Insieme di codici G che controllano la stessa funzione o modalità (es. G90 e G91 per le modalità di posizionamento).  
- **Modale**: Resta attivo fino a quando non viene richiamato un altro codice dello stesso gruppo.  
- **Normale**: Una linea perpendicolare a un piano, orientata nella direzione positiva.  
- **Origine**: Il punto in un sistema di coordinate in cui X, Y e Z sono pari a zero.  
- **RPM**: Giri al minuto.  
- **UPM (Unità per minuto)**: Pollici, millimetri, gradi, ecc.  
- **Parola**: Una singola “parola” in codice G, composta da una lettera seguita da un numero (es. G01, X1.0, ecc.).  
- **G**: Funzione preparatoria; G seguito da un codice numerico specifica modalità e funzioni di lavorazione.  
- **M**: Funzione varia; M seguito da un codice numerico definisce il flusso del programma e può controllare funzioni ausiliarie (come il refrigerante) o eseguire funzioni specifiche della macchina e macro.  
- **X, Y, Z, A, B, C**: Comandi di movimento seguiti da un valore numerico che definiscono il punto finale del comando.  
- **S**: Velocità del mandrino, seguita da un valore numerico (in RPM o velocità superficiale desiderata).  
- **T**: Chiamata dell’utensile, seguita dal numero dell’utensile da utilizzare successivamente.  
- **H**: Offset in altezza dell’utensile, generalmente corrispondente al numero dell’utensile.  
- **D**: Offset del diametro dell’utensile, generalmente corrispondente al numero dell’utensile.  
- **F**: Valore numerico che definisce la velocità di avanzamento; il valore effettivo dipende dall’impostazione della modalità di avanzamento.  
- **P**: Valore numerico che specifica il tempo di dwell in secondi (utilizzato anche in altre funzioni).  
- **N**: Numeri di sequenza, utilizzati per organizzare il programma e per i comandi di salto.

---
### Formato

Quando si scrivono programmi in codice G, è importante seguire alcune regole e linee guida di formattazione.

La prima parte di ogni programma dovrebbe essere un blocco di “avvio sicuro”. Questo blocco serve a garantire che alcune modalità siano disattivate mentre altre vengano impostate ai valori più comuni. Un esempio di blocco di avvio sicuro è:

G00 G90 G17 G54 G40 G49 G80

Questo blocco di codice indica alla macchina di:
- Utilizzare la modalità rapida (G00)
- Impostare la modalità di posizionamento assoluto (G90)
- Selezionare il piano XY (G17)
- Applicare l’offset del fixture 1 (G54)
- Cancellare ogni compensazione dell’utensile (G40)
- Cancellare l’offset di lunghezza (G49)
- Annullare eventuali cicli preimpostati (G80)

Si raccomanda di utilizzare questo blocco all’inizio del programma e anche prima o subito dopo ogni cambio utensile, poiché riduce il rischio di comportamenti inattesi (che potrebbero causare errori o incidenti).

Per terminare il programma, solitamente si riportano gli assi alla posizione di origine, si disattiva il mandrino e il refrigerante. L’ultimo blocco del programma è il codice di fine programma (spesso M30), seguito da un EOB (fine blocco). Per garantire la presenza dell’EOB, è utile inserire subito dopo il comando finale il simbolo %, come nell’esempio:

...  
M30  
%

---

| Codice G | Gruppo | Descrizione                                                                | Modale |
| -------- | ------ | -------------------------------------------------------------------------- | ------ |
| G13      | 1      | Cerchio in senso antiorario                                                | Y      |
| G15      | 11     | Annullamento coordinate polari                                             | Y      |
| G16      | 11     | Coordinate polari                                                          | Y      |
| G17      | 2      | Selezione del piano XY                                                     | Y      |
| G18      | 2      | Selezione del piano ZX                                                     | Y      |
| G19      | 2      | Selezione del piano YZ                                                     | Y      |
| G20      | 6      | Pollici                                                                    | Y      |
| G21      | 6      | Millimetri                                                                 | Y      |
| G28      | 0      | Ritorno a zero                                                             | N      |
| G30      | 0      | Ritorno a zero (2°, 3°, 4°)                                                | N      |
| G31      | 1      | Funzione di sonda                                                          | N      |
| G32      | 1      | Filettatura *                                                              | N      |
| G40      | 7      | Annullamento compensazione utensile                                        | Y      |
| G41      | 7      | Compensazione utensile a sinistra                                          | Y      |
| G42      | 7      | Compensazione utensile a destra                                            | Y      |
| G43      | 8      | Attivazione offset lunghezza utensile                                      | Y      |
| G44      | 8      | Attivazione offset lunghezza utensile (negativo)                           | Y      |
| G49      | 8      | Annullamento offset lunghezza utensile                                     | Y      |
| G50      | 9      | Annullamento scalatura                                                     | Y      |
| G51      | 9      | Scalatura assi                                                             | Y      |
| G52      | 0      | Spostamento sistema di coordinate locale                                   | Y      |
| G53      | 0      | Sistema di coordinate macchina                                             | N      |
| G54      | 12     | Offset fixture 1                                                           | Y      |
| G54.1    | 12     | Offset fixture aggiuntivi                                                  | Y      |
| G55      | 12     | Offset fixture 2                                                           | Y      |
| G56      | 12     | Offset fixture 3                                                           | Y      |
| G57      | 12     | Offset fixture 4                                                           | Y      |
| G58      | 12     | Offset fixture 5                                                           | Y      |
| G59      | 12     | Offset fixture 6                                                           | Y      |
| G60      | 0      | Avvicinamento unidirezionale                                               | N      |
| G61      | 13     | Modalità di arresto esatto                                                 | Y      |
| G64      | 13     | Modalità di taglio (velocità costante)                                     | Y      |
| G65      | 0      | Chiamata macro                                                             | N      |
| G66      |        | Macro chiamata modale                                                      | Y      |
| G67      |        | Annullamento macro chiamata modale                                         | Y      |
| G68      | 15     | Rotazione del sistema di coordinate                                        | Y      |
| G69      | 15     | Annullamento rotazione del sistema di coordinate                           | Y      |
| G73      | 16     | Foratura a scatti ad alta velocità                                         | Y      |
| G74      | 16     | Filettatura sinistra *                                                     | Y      |
| G76      | 16     | Allargamento fine *                                                        | Y      |
| G80      | 16     | Annullamento ciclo preimpostato                                            | Y      |
| G81      | 16     | Foratura di foro                                                           | Y      |
| G82      | 16     | Fresatura superficiale                                                     | Y      |
| G83      | 16     | Foratura a scatti per fori profondi                                        | Y      |
| G84      | 16     | Filettatura destra (RH)                                                    | Y      |
| G84.2    | 16     | Filettatura rigida destra (RH) *                                           | Y      |
| G84.3    | 16     | Filettatura rigida sinistra (LH) *                                         | Y      |
| G85      | 16     | Allargamento, retrazione a velocità di avanzamento, mandrino acceso        | Y      |
| G86      | 16     | Allargamento, retrazione a rapida velocità, mandrino spento                | Y      |
| G87      | 16     | Allargamento inverso *                                                     | Y      |
| G88      | 16     | Allargamento, retrazione manuale                                           | Y      |
| G89      | 16     | Allargamento, dwell, retrazione a velocità di avanzamento, mandrino acceso | Y      |
| G90      | 3      | Modalità di posizionamento assoluto                                        | Y      |
| G90.1    | 4      | Modalità centro arco assoluto                                              | Y      |
| G91      | 3      | Modalità di posizionamento incrementale                                    | Y      |
| G91.1    | 4      | Modalità centro arco incrementale                                          | Y      |
| G92      | 0      | Impostazione del sistema di coordinate locale                              | Y      |
| G92.1    | 0      | Annullamento impostazione del sistema di coordinate locale                 | Y      |
| G93      | 5      | Avanzamento in tempo inverso                                               | Y      |
| G94      | 5      | Avanzamento per minuto                                                     | Y      |
| G95      | 5      | Avanzamento per rivoluzione*                                               | Y      |
| G96      | 14     | Velocità superficiale costante*                                            | Y      |
| G97      | 14     | Velocità costante                                                          | Y      |
| G98      | 10     | Ritorno al punto iniziale                                                  | Y      |
| G99      | 10     | Ritorno al punto R                                                         | Y      |
* Implementation based on machine and control configuration
### Descrizioni ed Esempi dei Codici G

#### **G00 – Movimento Rapido**

I movimenti rapidi vengono utilizzati per spostarsi da un punto all'altro nello spazio libero, senza tagliare il materiale. Questi movimenti non richiedono un'impostazione della velocità di avanzamento (feedrate), poiché avvengono alla massima velocità della macchina.

- In modalità di posizionamento assoluto (G90), X, Y e Z definiscono il punto finale del movimento nel sistema di coordinate dell'utente.
- In modalità di posizionamento incrementale (G91), X, Y e Z definiscono la distanza e la direzione dello spostamento rispetto alla posizione attuale.

**Formato:**

```
G00 X__ Y__ Z__
```

**Esempio:**  
Programmare un movimento rapido verso X1.0, Y3.0:

```
G0 G90 G54 G17 G40 G49 G80   (Linea di avvio sicuro)  
T1 M6                         (Cambio utensile)  
S2500 M3                      (Avvio del mandrino)  
G0 X1.0 Y3.0                  (Movimento rapido alla posizione XY)  
M30                           (Fine programma e riavvolgimento)  
```

---
#### **G01 – Movimento Lineare con Avanzamento**

I movimenti lineari con avanzamento sono movimenti punto a punto in linea retta, eseguiti a una velocità di avanzamento specificata dal comando **F**.  
Questi movimenti sono interpolati, il che significa che tutti gli assi coinvolti nel movimento raggiungono il punto finale nello stesso momento.

- In modalità di posizionamento assoluto (G90), X, Y e Z definiscono il punto finale del movimento nel sistema di coordinate dell'utente.
- In modalità di posizionamento incrementale (G91), X, Y e Z definiscono la distanza e la direzione dello spostamento rispetto alla posizione attuale.

> **Nota:**  
> Per maggiore chiarezza, i movimenti rotazionali sono stati omessi in questo manuale.  
> Tutti i comandi di movimento possono includere anche il movimento sugli assi A, B e/o C.

**Formato:**

```
G01 X__ Y__ Z__ F__.
```

**Esempio:**  
Programmare un movimento di avanzamento da X1.0, Y3.0 a X10.0, Y-1.0 con una velocità di avanzamento di 15 UPM:

```
G0 G90 G54 G17 G40 G49 G80   (Linea di avvio sicuro)  
T1 M6                         (Cambio utensile)  
S2500 M3                      (Avvio del mandrino)  
G94                           (Modalità avanzamento per minuto)  
G0 X1.0 Y3.0                  (Movimento rapido alla posizione XY)  
G1 X10.0 Y-1.0 F15.0          (Movimento alla posizione XY con avanzamento)  
M30                           (Fine programma e riavvolgimento)  
```

---
#### **G02/G03 – Movimento ad Arco con Avanzamento**

I comandi **G02** e **G03** vengono utilizzati per eseguire un movimento ad arco con una velocità di avanzamento specificata dal parametro **F**.

Un arco è definito dai seguenti parametri:

- Punto iniziale (coincide con la posizione attuale della macchina)
- Punto finale (**X, Y, Z**)
- Raggio o punto centrale
- Direzione (**G02** per orario, **G03** per antiorario)
- Piano di lavoro selezionato (**G17** per XY, **G18** per XZ, **G19** per YZ)

La direzione dell’arco è determinata dai comandi:

- **G02** → Movimento in senso orario
- **G03** → Movimento in senso antiorario

Quando si lavora sul piano XY (**G17**), si osserva il piano dall'alto, con l'asse X positivo verso destra e l'asse Y positivo verso l'alto.

Il punto iniziale è sempre la posizione attuale della macchina, mentre il punto finale viene definito tramite **X, Y, Z**. Se viene aggiunto un terzo asse nel comando, verrà eseguita un'interpolazione elicoidale.
###### **Definizione dell’Arco: Raggio o Centro**

È possibile specificare un arco in due modi:

1. **Utilizzando il raggio dell’arco (R)**
2. **Utilizzando il punto centrale dell’arco (I, J, K)**

🔹 **Utilizzo del Raggio (R)**

- Il valore **R** rappresenta il raggio dell’arco desiderato.
- Esistono due possibili soluzioni per un arco con un dato raggio:
    - **R positivo** → Arco con un'ampiezza inferiore a 180°
    - **R negativo** → Arco con un'ampiezza superiore a 180°

🔹 **Utilizzo del Punto Centrale (I, J, K)**

- Metodo più accurato e affidabile.
- **I, J, K** rappresentano le coordinate del centro dell’arco nel piano corrente:
    - **I** → Distanza lungo X
    - **J** → Distanza lungo Y
    - **K** → Distanza lungo Z
- Il punto centrale può essere definito in modalità **assoluta** o **incrementale**, configurabile tramite **G90.1** (assoluto) e **G91.1** (incrementale).
    - **Modalità incrementale** → I, J, K indicano la distanza tra il punto iniziale e il centro dell’arco.
    - **Modalità assoluta** → I, J, K indicano la posizione assoluta del centro nel sistema di coordinate dell’utente.
##### **Formati dei Comandi**

**Formato con il Punto Centrale (I, J, K):**

```gcode
(G17) G02/03 X__ Y__ I__ J__ F__  ; Piano XY  
(G18) G02/03 X__ Z__ I__ K__ F__  ; Piano XZ  
(G19) G02/03 Y__ Z__ J__ K__ F__  ; Piano YZ  
```

**Formato con il Raggio (R):**

```gcode
(G17) G02/03 X__ Y__ R__ F__  ; Piano XY  
(G18) G02/03 X__ Z__ R__ F__  ; Piano XZ  
(G19) G02/03 Y__ Z__ R__ F__  ; Piano YZ  
```

![[Pasted image 20250218205301.png]]
![[Pasted image 20250218205345.png]]
##### **Esempi di Programmazione degli Archi**

 **Esempio 1: Arco con Centro a (1.0, 0.0) nel Piano XY e Raggio 2**

- **Punto di partenza:** (3.0, 0.0)
- **Sweep dell’arco:** 90° in senso antiorario (**G03**)
- **Modalità centro arco:** **Incrementale** (**G91.1**)
- **Velocità di avanzamento:** 10 UPM

 **Formato 1: Utilizzo delle coordinate del centro (I, J)**

```gcode
G0 G90 G54 G17 G40 G49 G80    ; Linea di avvio sicuro  
T1 M6                         ; Cambio utensile  
S2500 M3                      ; Avvio del mandrino  
G0 X3.0 Y0.0                  ; Posizionamento al punto iniziale (X, Y)  
G43 H1 Z0.5                   ; Attivazione offset utensile 1 e spostamento in Z rapido  
G94                           ; Modalità avanzamento per minuto  
G1 Z0.0 F10.0                 ; Discesa in Z con avanzamento  
G3 X1.0 Y2.0 I-2.0 J0.0 F10.0 ; Movimento ad arco  
G0 Z0.5                       ; Ritiro asse Z in rapido  
G0 G53 Z0.0                   ; Ritorno a zero in Z  
M30                           ; Fine programma e riavvolgimento  
```

 **Formato 2: Utilizzo del raggio (R)**

```gcode
G0 G90 G54 G17 G40 G49 G80    ; Linea di avvio sicuro  
T1 M6                         ; Cambio utensile  
S2500 M3                      ; Avvio del mandrino  
G0 X3.0 Y0.0                  ; Posizionamento al punto iniziale (X, Y)  
G43 H1 Z0.5                   ; Attivazione offset utensile 1 e spostamento in Z rapido  
G94                           ; Modalità avanzamento per minuto  
G1 Z0.0 F10.0                 ; Discesa in Z con avanzamento  
G3 X1.0 Y2.0 R2.0 F10.0       ; Movimento ad arco  
G0 Z0.5                       ; Ritiro asse Z in rapido  
G0 G53 Z0.0                   ; Ritorno a zero in Z  
M30                           ; Fine programma e riavvolgimento  
```
##### **Interpolazione Elicoidale**

L’interpolazione elicoidale è simile alla programmazione di un arco, con la differenza che si aggiunge una terza coordinata nel punto finale, che definisce l’altezza della spirale.

 **Formato 1: Utilizzo del centro (I, J, K)**

```gcode
(G17) G02/03 X__ Y__ Z__ I__ J__ F__
```

 **Formato 2: Utilizzo del raggio (R)**

```gcode
(G17) G02/03 X__ Y__ Z__ R__ F__
```

 **Esempio 2: Interpolazione Elicoidale**

- **Centro dell’elica:** (0.0, 0.0) nel piano XY
- **Punto di partenza:** (0.0, 0.5)
- **Altezza della spirale:** 1.0
- **Sweep dell’arco:** 270° in senso orario (**G02**)
- **Velocità di avanzamento:** 10 UPM

```gcode
G0 G90 G54 G17 G40 G49 G80    ; Linea di avvio sicuro  
T1 M6                         ; Cambio utensile  
S2500 M3                      ; Avvio del mandrino  
G0 X0.0 Y0.5                  ; Posizionamento al punto iniziale (X, Y)  
G43 H1 Z0.5                   ; Attivazione offset utensile 1 e spostamento in Z rapido  
G94                           ; Modalità avanzamento per minuto  
G1 Z0.0 F10.0                 ; Discesa in Z con avanzamento  
G2 X-0.5 Y0.0 Z-1.0 I0.0 J-0.5 F10.0 ; Interpolazione elicoidale  
G0 Z0.5                       ; Ritiro asse Z in rapido  
G0 G53 Z0.0                   ; Ritorno a zero in Z  
M30                           ; Fine programma e riavvolgimento  
```

![[Pasted image 20250218205716.png]]

---
#### **G04 – Pausa (Dwell)**

Il comando **G04** introduce una pausa nel programma per una durata specificata dal parametro **P** in secondi.  
Durante la pausa, la macchina non eseguirà alcun movimento, ma tutti i codici ausiliari attivi rimarranno invariati (ad esempio, il mandrino e il refrigerante rimarranno accesi se erano attivi).
##### **Formato:**

```gcode
G04 P__
```
##### **Esempio:**

Programmare una pausa di 5 secondi dopo essersi posizionati a **X1.0, Y1.0, Z0.5**.

```gcode
G0 G90 G54 G17 G40 G49 G80    ; Linea di avvio sicuro  
T1 M6                         ; Cambio utensile  
S2500 M3                      ; Avvio del mandrino  
G0 X1.0 Y1.0                  ; Movimento rapido alla posizione XY  
Z0.5                          ; Movimento rapido alla posizione Z  
G4 P5.0                       ; Pausa di 5 secondi  
M30                           ; Fine programma e riavvolgimento  
```

---
#### **G09 – Arresto Esatto (Exact Stop)**

Il comando **G09** impone un arresto esatto al termine del movimento, assicurando che la macchina raggiunga esattamente la posizione specificata prima di eseguire il blocco successivo.

- Durante i movimenti, le accelerazioni della macchina possono arrotondare leggermente gli angoli.
- Quando è necessario un angolo netto, si usa **G09** per verificare la posizione finale prima di continuare.
- **G09** è un comando **non modale**, cioè agisce solo sulla linea in cui è presente.
- **G61** è una funzione simile, ma **modale**, quindi rimane attiva fino alla sua disattivazione.
##### **Formato:**

```gcode
G01 G09 X__ Y__ F__
```

##### **Esempio:**

Programmare un quadrato di **2.0 pollici** centrato in **X0.0, Y0.0**, con angoli netti in **X1.0, Y1.0** e **X1.0, Y-1.0**, a una velocità di avanzamento di **15 UPM**.

```gcode
G0 G90 G54 G17 G40 G49 G80    ; Linea di avvio sicuro  
T1 M6                         ; Cambio utensile  
S2500 M3                      ; Avvio del mandrino  
G94                           ; Modalità avanzamento per minuto  
G0 X-1.0 Y1.0                 ; Movimento rapido alla posizione XY iniziale  
G1 G9 X1.0 F15.0              ; Movimento a posizione con arresto esatto attivo  
Y-1.0                         ; Movimento alla posizione successiva  
G9 X-1.0                      ; Movimento a posizione con arresto esatto attivo  
Y1.0                          ; Movimento alla posizione finale  
M30                           ; Fine programma e riavvolgimento  
```

![[Pasted image 20250218210159.png]]

---
#### **G10 – Impostazione degli Offset di Fixture e Utensile**

Il comando **G10** permette di impostare gli offset di fixture e utensili direttamente nel programma.  
Questa funzione è utile per:

- Programmare più fixture con punti zero predefiniti.
- Macchine multi-pallet.
- Compensare automaticamente l’usura degli utensili.
- Automatizzare i cambi di offset senza l’intervento dell’operatore.

> **Attenzione:**  
> La modifica degli offset nel programma richiede cautela: un errore può causare danni ai pezzi e agli utensili.  
> Tuttavia, se utilizzato correttamente, **G10** migliora la flessibilità e la sicurezza della macchina, soprattutto in ambienti automatizzati.

##### **Impostazione degli Offset di Fixture**

Il comando **G10 L2** consente di impostare gli offset di fixture.  
Il valore **P** specifica quale offset viene modificato.

##### **Formato:**

```gcode
G10 L2 P__ X__ Y__ Z__ A__ B__ C__
```

Dove:

- **L2** → Seleziona l’impostazione degli offset di fixture.
- **P** → Numero dell’offset da modificare.
- **X, Y, Z, A, B, C** → Valori degli offset per ciascun asse.

##### **Tabella degli Offset di Fixture Standard**

|Offset Fixture|G__|P__|
|---|---|---|
|G54|1|1|
|G55|2|2|
|G56|3|3|
|G57|4|4|
|G58|5|5|
|G59|6|6|

> **Nota:** Non è necessario specificare tutti i valori **X, Y, Z, A, B, C**.  
> Se un valore non viene programmato, l’offset corrispondente non verrà modificato.

##### **Modalità Assoluta vs Incrementale**

- **In modalità assoluta (G90)**: I valori specificati vengono assegnati direttamente all’offset.
- **In modalità incrementale (G91)**: I valori vengono sommati all’offset attuale.
##### **Esempio 1: Impostazione dell’Offset di Fixture G56**

Imposta **G56** con i seguenti valori:

- **X = -8.0**
- **Y = -3.0**
- **Z = -5.0**
- **A = 45.0**

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro  
G10 L2 P3 X-8.0 Y-3.0 Z-5.0 A45.0  ; Imposta l'offset di fixture G56  
M30                           ; Fine programma e riavvolgimento  
```
##### **Offset Aggiuntivi (G54.1 Pxx)**

Gli offset **G54.1 Pxx** possono essere impostati con **G10 L20**.  
Questa modalità è equivalente alla legacy **G59 Pxx**.

##### **Tabella di Conversione degli Offset Aggiuntivi**

|G54.1 P__|G10 L20 P__|Legacy G59 P__|Legacy G10 L2 P__|
|---|---|---|---|
|1|1|7|7|
|2|2|8|8|
|3|3|9|9|
|…|…|…|…|
|248|248|254|254|

> **Nota:** **G54.1 P1** è lo stesso offset di **G59 P7**, quindi i comandi **G10 L20 P1** e **G10 L2 P7** impostano gli stessi valori.

**Esempio:** Impostare l'offset di fixture **G54.1 P5** a **X3.0, Y3.4, Z-10.0** in un programma.

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro
G10 L20 P5 X3.0 Y3.4 Z-10.0   ; Imposta i valori dell'offset di fixture G54.1 P5
M30                         ; Fine programma e riavvolgimento
```

Il cambio turno e il cambio testata possono anch'essi essere impostati con **G10**.

- Il cambio turno viene impostato usando **G10 L2 P0**.
- Il cambio testata viene impostato usando **G10 L20 P0**.  
    (Nota: viene usato **L20** per il cambio testata.)  
    Tutti gli altri valori sono impostati nello stesso formato degli altri offset di fixture.

L'impostazione degli offset utensile richiede altrettanta attenzione quanto quella degli offset di fixture.  
Le modalità **G90** e **G91** influenzano l'impostazione degli offset allo stesso modo:

- **G90** sovrascrive il valore corrente con quello specificato nel blocco **G10**.
- **G91** somma il valore specificato al valore corrente.

**Formato per l'impostazione degli offset utensile:**

```gcode
G10 L1 P__ Z__ W__ D__ R__ X__ U__ Y__ V__ Q__
```

> Non tutti i valori sono obbligatori; se un valore viene omesso, l'offset corrispondente non verrà modificato.  
> **L1** specifica l'impostazione degli offset utensile;  
> **P** indica il numero dell'offset da impostare (offset #1 = P1, offset #2 = P2, ecc.).
> 
> Le definizioni dei parametri sono:
> 
> - **Z**: Offset in altezza
> - **W**: Offset in usura dell'altezza
> - **D**: Offset del diametro
> - **R**: Offset in usura del diametro
> - **X***: Offset lungo X
> - **U***: Offset in usura lungo X
> - **Y***: Offset lungo Y
> - **V***: Offset in usura lungo Y
> - **Q**: Tasca utensile
> 
> _Funzionalità futura non ancora implementata._

**Esempio:** Impostare l'altezza dell'offset utensile #5 a **1.5** e aggiungere **0.05** all'usura del diametro per l'offset utensile #2.

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro
G10 L1 P5 Z1.5               ; Imposta l'altezza dell'offset utensile 5 a 1.5
G91                          ; Modalità incrementale per sommare al valore corrente
G10 L1 P2 R0.05              ; Aggiunge 0.05 all'usura del diametro per l'offset utensile #2
M30                          ; Fine programma e riavvolgimento
```

---
#### G12/G13 – Interpolazione Circolare

Questi codici vengono utilizzati per fresare un cerchio utilizzando la posizione attuale come punto centrale.  
I comandi **I** e **J** definiscono il raggio del cerchio e la direzione di ingresso.

- **G12** freserà un cerchio in senso orario.
- **G13** freserà un cerchio in senso antiorario.

È inoltre possibile fresare una tasca circolare più ampia specificando **Q** per il raggio iniziale e **P** per il passo di avanzamento, utile per fresare una tasca circolare o una scanalatura interna.

**Formato 1:**

```gcode
G12/13 I__ J__ F__
```

**Formato 2:**

```gcode
G12/13 I__ J__ P__ Q__
```

Vedi la figura 12-1 per una rappresentazione grafica del movimento; la posizione attuale sarà il centro del cerchio.

**Figura 12-1: Movimento dell'utensile durante l'interpolazione circolare**  
(Punto centrale: I, J; Q, P, I, J; Raggio)

![[Pasted image 20250218211211.png]]

**Esempio 1:** Fresare un cerchio di raggio 1.0 pollici, centrato in **X1.5, Y0.25**, con ingresso lungo l'asse X.

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro, modalità assoluta, piano XY
G0 X1.5 Y0.25                ; Spostamento alla posizione iniziale
G13 I1.0 F30.0               ; Fresatura del cerchio
G0 G53 Z0.0                  ; Portare l'asse Z a zero macchina
M30                         ; Fine programma e riavvolgimento
```

**Esempio 2:** Fresare lo stesso cerchio, ma con ingresso a 45°  
_(X = 1·Cos(45°) = 0.7071, Y = 1·Sin(45°) = 0.7071)_

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro, modalità assoluta, piano XY
G0 X1.5 Y0.25                ; Spostamento alla posizione iniziale
G13 I0.7071 J0.7071 F30.0     ; Fresatura del cerchio
G0 G53 Z0.0                  ; Portare l'asse Z a zero macchina
M30                         ; Fine programma e riavvolgimento
```

---
#### G15/G16 – Coordinate Polari

Per abilitare il posizionamento in coordinate polari, si utilizza il comando **G16** in un programma. Questa impostazione è modale e rimarrà attiva fino a quando non verrà emesso il comando **G15** (annullamento delle coordinate polari) oppure il sistema verrà resettato. In modalità coordinate polari, i punti finali dei movimenti sono specificati come raggio e angolo, la cui origine è determinata dall'impostazione della modalità di posizionamento assoluta/incrementale (vedi G90/G91). In modalità di posizionamento assoluto l'origine per il posizionamento è il punto zero del sistema di coordinate utente, mentre in modalità incrementale l'origine è la posizione attuale.

**Formato:**

```gcode
G16 X__ Y__ Z__
```

L'impostazione del piano corrente determina quale parola rappresenta il raggio e quale l'angolo:

- **G17** – Piano XY: X è il raggio, Y l'angolo.
- **G18** – Piano ZX: Z è il raggio, X l'angolo.
- **G19** – Piano YZ: Y è il raggio, Z l'angolo.

I movimenti lineari e ad arco possono essere programmati in modalità coordinate polari. Quando si programmano movimenti ad arco con **G02** e **G03**, si usa **R** per specificare il raggio dell'arco.

**Esempio:**  
_(Vedi figura 15-1 per il percorso dell'utensile del seguente programma.)_

```gcode
G0 G90 G54 G17 G40 G49 G80 ; Linea di avvio sicuro, modalità assoluta, piano XY
G16                        ; Abilita la modalità coordinate polari
G0 X1.0 Y45.0              ; Spostamento a raggio 1 e angolo 45° dall'origine
G3 X1.0 Y135.0 R0.75 F60.0 ; Movimento ad arco: raggio 0.75, punto finale con raggio 1.0 e angolo 135°
G1 X2.25 Y180.0            ; Movimento lineare a raggio 2.25 e angolo 180°
G3 X2.25 Y0 R5.0           ; Movimento ad arco: raggio 5, punto finale con raggio 2.25 e angolo 0
G1 X1.0 Y45.0              ; Movimento lineare a raggio 1.0 e angolo 45°
G15                        ; Disabilita la modalità coordinate polari
G0 G53 Z0.0                ; Asse Z riportato a zero macchina
M30                        ; Fine programma e riavvolgimento
```

![[Pasted image 20250218211429.png]]

---
#### G17/G18/G19 – Selezione del Piano

Gli archi, i cerchi e i cicli di foratura richiedono la selezione di un piano. I tre assi X, Y e Z definiscono tre piani disponibili: XY, ZX e YZ, vedi la figura 17-1. Il terzo asse definisce la parte superiore del piano, questo asse è anche conosciuto come normale, vedi la figura 17-2. La selezione di un piano avviene specificando uno dei tre codici G: **G17** per il piano XY, **G18** per il piano ZX e **G19** per il piano YZ. Questi sono codici G modali e rimarranno attivi fino a quando non verrà selezionato un altro piano o il sistema verrà resettato. Il piano predefinito è **G17**. Tutti i movimenti ad arco e circolari avverranno su un unico piano. La direzione del movimento, orario o antiorario, è quella vista dalla direzione normale, vedi la figura 17-2.

Anche i cicli di foratura predefiniti richiedono la selezione di un piano. In questo caso, tutte le posizioni dei fori saranno localizzate nel piano selezionato e l'asse normale sarà l'asse di foratura. Ad esempio, nel piano XY, l'asse Z è l'asse di foratura.

![[Pasted image 20250218211832.png]]

---
#### G20/G21 – Selezione dell'unità

Le unità di programmazione vengono selezionate utilizzando **G20** per le pollici e **G21** per i millimetri. Utilizzare questi codici G per specificare le unità nel programma; l'impostazione non influenzerà i DRO della macchina, le impostazioni di configurazione o i compensi.

---
#### G28 – Ritorno a Zero

Questa funzione viene utilizzata per inviare uno o più assi alla posizione di origine tramite un punto intermedio. Fare attenzione quando si utilizza questa funzione. Se non completamente compresa, il movimento risultante potrebbe differire notevolmente da quanto previsto. Se utilizzato correttamente, il punto intermedio può essere utile per evitare ostacoli sul percorso diretto verso la posizione di origine, vedi la figura 28-1.
![[Pasted image 20250218212043.png]]

**Formato:**

```gcode
G28 X__ Y__ Z__ A__ B__ C__
```

Questo non è un codice modale e sarà attivo solo nel blocco in cui è specificato. Dopo il **G28**, vanno indicati gli assi da inviare a casa. Ad esempio, per inviare l'asse Z alla posizione di origine, il programma sarà: **G28 Z0**. Il valore specificato con la lettera dell'asse specifica il punto intermedio.

Esempio di programma:

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro
G0 X1.0 Y.5 Z1.0            ; Posizionamento rapido al punto
G28 Z0.0                    ; Invia l'asse Z a casa tramite il punto Z0
M30                         ; Fine programma e riavvolgimento
```

Leggendo il programma, troviamo un blocco di avvio sicuro che imposta la macchina in modalità di posizionamento assoluto. La riga successiva causa il movimento della macchina al punto X1, Y.5, Z1. nel sistema di coordinate impostato dal compenso di fissaggio **G54**. Ora, per il blocco **G28**, questa riga di codice, **G28 Z0**, fornisce le istruzioni per inviare l'asse Z alla posizione di origine tramite il punto Z0. Il movimento sarà il seguente: prima l'asse Z scenderà al punto Z0 e poi tornerà alla posizione di origine. Se non è intenzionato, questo movimento potrebbe causare la rottura dell'utensile o la scarto del pezzo. Per evitare questo movimento non intenzionato, il formato comune di programmazione è il seguente:

```gcode
G91 G28 Z0
```

In questo caso, il punto intermedio è un movimento incrementale di 0 pollici, risultando in nessun movimento prima che l'asse Z ritorni alla posizione di origine.

---
#### G30 – 2nd, 3rd, 4th Zero Return

**G30** funziona allo stesso modo di **G28**, spostando la macchina verso un punto di ritorno a zero tramite un punto intermedio. Tuttavia, invece di inviare la macchina alla posizione di origine, il movimento **G30** termina in un punto di ritorno a zero definito dall'utente, che può essere il 2°, 3° o 4° punto di ritorno a zero, specificato rispettivamente da **P2**, **P3** o **P4**. Se **P** viene omesso, viene selezionato il 2° punto di ritorno a zero. Questa funzione è utile per i cambi utensile che non si trovano nella posizione di origine o per qualsiasi altra applicazione.

**Formato:**

```gcode
G30 P__ X__ Y__ Z__ A__ B__ C__
```

Il 2° punto di ritorno a zero è definito dalle variabili **#** come segue:

|Asse|P2 Variabili #|P3 Variabili #|P4 Variabili #|
|---|---|---|---|
|X|5301|5311|5321|
|Y|5302|5312|5322|
|Z|5303|5313|5323|
|A|5304|5314|5324|
|B|5305|5315|5325|
|C|5306|5316|5326|

I valori di posizione nelle variabili **#** possono essere impostati in un programma o in modalità MDI.

---
#### G31/G31.X – Funzione di Sonda

Conosciuto anche come funzione di salto, **G31** consente l'uso di sonde per il pezzo e per l'utensile. Possono essere utilizzate sonde multiple: **G31** per la sonda 1, **G31.1** per la sonda 2, **G31.2** per la sonda 3 e **G31.3** per la sonda 4. Il movimento è definito lungo gli assi lineari, in un formato simile a **G01**, con una velocità di avanzamento.

**Formato:**

```gcode
G31 X__ Y__ Z__ F__
```

La macchina si muoverà verso il punto finale specificato, contemporaneamente cercando che l'input della sonda venga attivato. Quando l'input della sonda viene attivato, la posizione attuale viene registrata nelle variabili **#** secondo la tabella sottostante e il movimento viene fermato. La posizione registrata può essere utilizzata per calcolare i compensi per l'utensile, i compensi per il lavoro, misurare i pezzi, ecc.

|Asse|G31 Variabili #|G31.1 Variabili #|G31.2|G31.3|
|---|---|---|---|---|
|X|5061|5071|||
|Y|5062|5072|||
|Z|5063|5073|||
|A|5064|5074|||
|B|5065|5075|||
|C|5066|5076|||

---
#### G32 – Filettatura

È possibile realizzare filetti utilizzando un mandrino per ruotare il pezzo e uno strumento di filettatura che non ruota. È possibile tagliare filetti diritti, conico e a scroll usando questo comando. È necessaria una retroazione della velocità del mandrino da un encoder, impulso di indice, tachimetro o altro dispositivo per questa operazione. La sincronizzazione dell'asse di avanzamento con la velocità del mandrino crea un filetto preciso; tuttavia, l'accelerazione dell'asse può causare variazioni nel passo del filetto, soprattutto all'inizio e alla fine del filetto. Il programma di compensazione potrebbe creare un filetto leggermente più lungo per dare tempo all'asse di accelerare. La quantità di lunghezza extra del filetto varierà in base alle specifiche della macchina. Cambiamenti nella velocità del mandrino e nella velocità di avanzamento influiranno sulla qualità e sull'accuratezza del filetto. L'uso della modalità di velocità superficiale costante può anche causare variazioni nel passo del filetto quando si tagliano filetti conici o a scroll, quindi è preferibile utilizzare la modalità **G97** a RPM costante. Durante il movimento di filettatura, la velocità del mandrino e i sovraspansioni di avanzamento saranno disabilitati e la macchina funzionerà al 100%. La pausa nell'avanzamento sarà ritardata, e se premuto, la macchina si fermerà alla fine del movimento di filettatura.

**Formato:**

```gcode
G32 X__ Y__ Z__ F__
```

Il ciclo di filettatura **G32** è un singolo movimento lineare sincronizzato con la velocità del mandrino. **F** specifica il passo del filetto. Ad esempio, un filetto ¼-20 avrà un passo di 0,05 pollici, quindi si programma **F.05**. Di default, il movimento è un semplice movimento lineare con velocità di avanzamento sincronizzata. I costruttori di macchine e gli utenti avanzati hanno l'opzione aggiuntiva di creare codici **M** personalizzati per specificare il vettore di avanzamento per creare filetti personalizzati.

**Esempio:** Filettare una barra ¼-20 tenuta nel mandrino, con una lunghezza del filetto di 1”.

```gcode
G0 G90 G54 G18 G40 G49 G80   ; Linea di avvio sicuro
G0 X0.3 Y0.0 Z0.1           ; Posizionamento rapido
G97 S1000 M3                 ; Avvia il mandrino a 1000 RPM
G0 X0.22                     ; Posizionamento iniziale per la lavorazione grezza
G32 X0.22 Z-1.0 F.05         ; Taglio filetto dritto
G0 X0.3                      ; Ritrazione asse X
Z0.1                         ; Ritrazione asse Z
X0.21                        ; Posizionamento iniziale per la finitura
G32 X0.21 Z-1.0 F.05         ; Taglio filetto dritto
G0 X0.3                      ; Ritrazione asse X
Z0.1                         ; Ritrazione asse Z
G53 Z0.0 M5                  ; Casa Z e ferma mandrino
M30                          ; Fine programma e riavvolgimento
```

I filetti possono anche essere tagliati con un cono aggiungendo il punto finale corretto.

**Esempio:** Taglio dello stesso filetto dell'esempio precedente con una conicità di 0,03.

```gcode
G0 G90 G54 G18 G40 G49 G80   ; Linea di avvio sicuro
G0 X0.3 Y0.0 Z0.1           ; Posizionamento rapido
G97 S1000 M3                 ; Avvia il mandrino a 1000 RPM
G0 X0.22                     ; Posizionamento iniziale per la lavorazione grezza
G32 X0.25 Z-1.0 F.05         ; Taglio filetto conico
G0 X0.3                      ; Ritrazione asse X
Z0.1                         ; Ritrazione asse Z
X0.21                        ; Posizionamento iniziale per la finitura
G32 X0.24 Z-1.0 F.05         ; Taglio filetto conico
G0 X0.3                      ; Ritrazione asse X
Z0.1                         ; Ritrazione asse Z
G53 Z0.0 M5                  ; Casa Z e ferma mandrino
M30                          ; Fine programma e riavvolgimento
```
![[Pasted image 20250218212441.png]]

---

### G40 – Annullamento della Compensazione Utensile

Annulla la modalità di compensazione dell'utensile.

### G41/G42 – Compensazione Utensile Sinistra/Destra

Abilita la compensazione dell'utensile a sinistra (**G41**) o a destra (**G42**) rispetto al percorso dell'utensile di una quantità specificata in un offset selezionato con **D**.

**Formato:**

```gcode
G1 G42 D__ X__ Y__ Z__ F__
```

Per informazioni dettagliate, consulta la sezione sulla compensazione dell'utensile di questo manuale.

### G43/G44 – Compensazione Lunghezza Utensile

Attiva un offset di lunghezza utensile selezionato con **H**. Quando attivato, i DRO delle posizioni verranno aggiornati per visualizzare la posizione del punto del programma dell'utensile, generalmente la punta. L'offset dell'utensile può essere applicato in direzione positiva con **G43** o in direzione negativa con **G44**. Generalmente, si utilizza **G43** per applicare l'offset dell'utensile. Esistono diversi modi per fare il tocco dell'utensile e determinare il valore dell'offset, vedi gli offset utensile nel manuale operativo per ulteriori dettagli, ma tutti vengono chiamati e applicati allo stesso modo.

**Formato:**

```gcode
G43 H__ X__ Y__ Z__
```

Se le posizioni degli assi sono specificate nello stesso blocco di **G43**, la macchina si muoverà al punto comandato. Se gli assi sono omessi, non ci sarà alcun movimento.

### G49 – Annullamento Offset Lunghezza Utensile

Annulla l'offset della lunghezza dell'utensile. Se non viene comandato alcun movimento nel blocco **G49**, non ci sarà movimento della macchina.

### G50 – Annullamento Scala

Annulla la scala.

### G51 – Funzione di Scala/Riflesso

Quando attivata, la funzione di scala moltiplica tutte le posizioni comandate per il fattore di scala specificato. I DRO e gli offset non sono influenzati, ma il movimento comandato da un programma o dalla schermata MDI è influenzato.

**Formato:**

```gcode
G51 X__ Y__ Z__ A__ B__ C__
```

Specifica l'asse da scalare e il fattore di scala desiderato. Per esempio:

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro
G0 X4.0 Y0.0 Z1.0           ; Posizione rapida al punto (posizione X è 4)
G51 X2.0                    ; Attiva la scala sull'asse X (fattore di scala = 2)
G0 X5.0                     ; Posizione rapida al punto (posizione X è 10)
G50                         ; Annulla la scala
G0 X5.0                     ; Posizione rapida al punto (posizione X è 5)
M30                         ; Fine programma e riavvolgimento
```

Quando la scala è attiva, i movimenti di posizione vengono calcolati moltiplicando la posizione comandata per il fattore di scala. Nell'esempio sopra, il fattore di scala sull'asse X è impostato su 2, quindi un movimento verso **X5** è comandato. La posizione finale effettiva di questo movimento sarà **5 * 2 = 10**. Quindi, l'asse X si muoverà a 10.

Esegui attenzione quando usi la scala, i risultati possono essere imprevedibili a seconda della complessità del programma. Ad esempio, se **G52 X2 Y4** è programmato seguito da un movimento ad arco nel piano XY, l'arco **NON** verrà scalato 2x sull'asse X e 4x sull'asse Y per ottenere un'ellisse. Le posizioni di partenza e di arrivo saranno quelle previste, ma il movimento da una all'altra potrebbe non esserlo. Controlla e ricontrolla la visualizzazione del percorso utensile prima di eseguire il programma.

Per riflettere un programma, inserisci un valore di scala negativo. Per esempio:

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro
G0 X4.0 Y0.0 Z1.0           ; Posizione rapida al punto (posizione X è 4)
G51 X-1.0                   ; Riflette l'asse X (fattore di scala = -1)
G0 X5.0                     ; Posizione rapida al punto (posizione X è -5)
G50                         ; Annulla la scala
G0 X5.0                     ; Posizione rapida al punto (posizione X è 5)
M30                         ; Fine programma e riavvolgimento
```
### G52 – Spostamento del Sistema di Coordinate Locale

Il comando G52 consente di impostare uno spostamento del sistema di coordinate locale, ovvero uno spostamento del piano di lavoro programmabile. L'impostazione è globale; l'intero sistema viene spostato dai valori specificati. Ogni offset del fissaggio verrà influenzato, anche se i valori effettivi degli offset del fissaggio non cambieranno.

**Formato:**

```gcode
G52 X__ Y__ Z__ A__ B__ C__
```

Per attivare un sistema di coordinate locale con **G52**, usa il formato sopra riportato. L'impostazione di un sistema di coordinate locale è simile all'impostazione di un offset di fissaggio. Nel blocco **G52**, specifica gli assi desiderati da impostare e il valore dello spostamento. Per esempio (vedi figura 52-1 per il percorso dell'utensile):

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro
G0 X-4.0 Y0.0 Z1.0          ; Posizione rapida al punto
G12 I2.0 F30.0              ; Taglia cerchio con raggio 2.0
G52 X7.0                    ; Sistema di coordinate locale attivo, offset X = 7
G0 X-4.0 Y0.0 Z1.0          ; Posizione rapida al punto di partenza
G12 I2.0 F30.0              ; Taglia lo stesso cerchio con raggio 2.0
G52 X0.0                    ; Annulla il sistema di coordinate locale
M30                         ; Fine programma e riavvolgimento
```

**Figura 52-1:** Esempio di percorso utensile nel programma.

![[Pasted image 20250218212712.png]]
Una volta impostato, il sistema di coordinate locale rimarrà attivo fino a quando non verrà annullato da un altro **G52** o il sistema verrà resettato. Come nell'esempio sopra, un sistema di coordinate locale può essere annullato specificando l'asse con valore zero. Questo annulla effettivamente lo spostamento del sistema di coordinate locale, impostandolo su zero, senza alcun effetto.

---
### G53 – Sistema di Coordinate della Macchina

Anche se la maggior parte del posizionamento della macchina avviene in un sistema di coordinate creato dall'utente, a volte può essere utile programmare le posizioni nel sistema di coordinate della macchina. **G53** è un codice non modulare, che è attivo solo per il blocco in cui viene specificato, e consente all'utente di eseguire movimenti di posizionamento nel sistema di coordinate della macchina. Questo può essere utile per spostarsi in una posizione di carico/scarico al termine di un programma o per spostarsi in una posizione di cambio utensile in una macro di cambio utensile. È anche un modo più sicuro per tornare alla posizione home della macchina **(G53 X0 Y0 Z0)** rispetto all'uso di **G28**, poiché non c'è una posizione intermedia da considerare.

**Formato:**

```gcode
G53 X__ Y__ Z__ A__ B__ C__
```

**Esempio:**

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro
G0 X4.0 Y0.0 Z1.0          ; Posizione rapida in G54
... Corpo del programma
G53 Z0.0                   ; Ritorna direttamente alla posizione Z home
G53 X10.0 Y0.0             ; Spostamento alla posizione di carico/scarico
M30                        ; Fine programma e riavvolgimento
```

Nel programma sopra, gli ultimi due movimenti di posizionamento sono eseguiti nel sistema di coordinate della macchina. Questi due blocchi potrebbero essere gli stessi per ogni programma su questa macchina.

---

### G54-G59 – Offset del Fissaggio

Questi codici vengono utilizzati per selezionare l'offset di fissaggio attivo in un programma. L'offset del fissaggio rimarrà attivo fino a quando non ne verrà chiamato un altro o il sistema verrà resettato. È possibile utilizzare più offset del fissaggio in un singolo programma.

---

### G54.1 – Offset Aggiuntivi del Fissaggio

Gli offset aggiuntivi del fissaggio sono forniti per gli utenti che utilizzano molti fissaggi/parti/configurazioni. Sono disponibili 248 offset aggiuntivi.

**Formato:**

```gcode
G54.1 P__
```

**P** specifica il numero dell'offset aggiuntivo, da 1 a 248.  
Le versioni precedenti di Mach usavano **G59 P7**, **P8** e così via. Questi offset legacy possono ancora essere utilizzati al posto di **G54.1**. Ad esempio:  
**G59 P7 = G54.1 P1**, **G59 P8 = G54.1 P2**, e così via. **G54.1** è più coerente con le macchine industriali.

Per maggiori dettagli sulla configurazione degli offset di fissaggio, consulta la sezione sugli offset di fissaggio in questo manuale.

---

### G60 – Approccio Unidirezionale

Nei casi in cui il gioco meccanico causi errori di posizionamento, l'approccio unidirezionale può essere utilizzato per aumentare la precisione. **G60** è un codice non modulare, e quando specificato in un blocco di movimento, il movimento si sposterà verso il punto finale partendo da una distanza e direzione definite dai parametri. Vedi la figura **60-1**. La distanza e la direzione del movimento di approccio sono specificate impostando valori nelle variabili **#** come mostrato nella tabella seguente:

**Tabella delle variabili:**

|Asse|Variabile #|
|---|---|
|X|5440|
|Y|5441|
|Z|5442|
|A|5443|
|B|5444|
|C|5445|

**Formato:**

```gcode
G60 G0/G1 X__ Y__ Z__
```

Quando viene utilizzato l'approccio unidirezionale in un ciclo di foratura, il movimento sull'asse **Z** non viene influenzato. I cicli di alesatura **G76** e **G87** hanno uno spostamento dell'utensile che non viene influenzato dall'approccio unidirezionale **G60**.
![[Pasted image 20250218212834.png]]

---
### G61 – Modalità Stop Esatto (Exact Stop Mode)

In modalità **Exact Stop**, la macchina decelererà fino a fermarsi completamente al termine di ogni movimento comandato, come mostrato nella figura **9-1**. Questo è un codice modulare, quindi una volta attivato, rimarrà attivo fino a quando non verrà annullato. Per angoli acuti e posizionamenti semplici, questa modalità funziona bene. Tuttavia, quando il codice diventa più complesso, o nelle fresature laterali con archi, la modalità **Exact Stop** produrrà movimenti bruschi e segni visibili sulla superficie del pezzo. Per la maggior parte dei lavori di fresatura, si consiglia di usare **G64**.

---

### G64 – Modalità Velocità Costante (Constant Velocity Mode)

In modalità **Constant Velocity**, Mach cercherà di mantenere la velocità di avanzamento anche attorno agli angoli acuti. Di conseguenza, gli angoli acuti saranno leggermente arrotondati e la macchina potrebbe non raggiungere mai il punto programmato prima di un cambio di direzione. La magnitudine di questi errori di posizione dipenderà dalla capacità di accelerazione della macchina e dalla velocità di avanzamento programmata. Nella maggior parte dei casi, l'errore sarà troppo piccolo per essere notato o influire sulla funzionalità del pezzo. La fresatura sarà più veloce e più fluida, con finiture migliori e senza segni visibili derivanti da arresti. Questa modalità sarà quella attiva per la maggior parte del tempo di lavorazione. È modulare e rimarrà attiva fino a quando non verrà attivata la modalità **Exact Stop**.

---

### G65 – Chiamata Macro (Macro Call)

Le macro funzionano come sottoprogrammi (vedi **M98** a pagina 57), ma consentono di passare valori dal programma principale sotto forma di variabili locali. I programmi macro possono utilizzare queste variabili locali per modificare le dimensioni del pezzo, selezionare caratteristiche, regolare le velocità di avanzamento, o qualsiasi altra cosa l'utente voglia cambiare.

**Formato:**

```gcode
G65 P____ A__ B__ C__ …
```

Il numero del programma desiderato da chiamare è specificato da **P**. Gli altri argomenti sono determinati dal programma macro che viene chiamato. I valori di questi argomenti verranno passati alle variabili locali per l'uso nel programma macro. Gli argomenti disponibili e le corrispondenti variabili sono mostrati nella tabella seguente.

**Tabella degli indirizzi e variabili:**

Ecco la traduzione della tabella:

|Indirizzo|Variabile|Indirizzo|Variabile|Indirizzo|Variabile|
|---|---|---|---|---|---|
|A|#1|I|#4|T|#20|
|B|#2|J|#5|U|#21|
|C|#3|K|#6|V|#22|
|D|#7|M|#13|W|#23|
|E|#8|Q|#17|X|#24|
|F|#9|R|#18|Y|#25|
|H|#11|S|#19|Z|#26|

La chiamata macro **G65** non è modulare e non ha un'opzione per essere ripetuta; il sottoprogramma macro verrà eseguito solo una volta per ogni chiamata **G65**. Per maggiori informazioni sulla programmazione delle macro e sull'uso delle variabili **#**, consulta la guida alla programmazione delle macro Mach4.

---

### G66 – Chiamata Macro Modale (Modal Macro Call)

A volte è utile eseguire la stessa macro in posizioni diverse (simile ai cicli di foratura) o con parametri diversi. **G66** è una chiamata macro modulare, la macro viene chiamata e i valori vengono passati allo stesso modo di **G65**, ma **G66** rimane attiva fino a quando non viene annullata. I blocchi successivi a **G66** possono contenere nuove posizioni e variabili per eseguire nuovamente la macro.

**Formato:**

```gcode
G66 P____ A__ B__ C__ …
A__ B__ C__ …  
```

Ulteriori informazioni sulla programmazione delle macro sono disponibili nella guida alla programmazione delle macro Mach4.

---

### G67 – Annulla Chiamata Macro Modale (Cancel Modal Macro Call)

**G67** annulla la chiamata macro modale **G66**.

Ecco la traduzione del testo:

### G68 – Rotazione del Sistema di Coordinate

È possibile ruotare un programma attorno a un punto specificato utilizzando il comando di rotazione del sistema di coordinate. Il comando è specificato nel seguente modo:

**Formato:**

```gcode
G68 X__ Y__ R__
```

Il comando è disponibile solo nel piano XY (G17) ed è un codice _modal_. **X** e **Y** specificano il punto attorno al quale il programma verrà ruotato, e **R** specifica l'angolo. Un valore positivo per **R** ruoterà il programma in senso antiorario quando osservato dal lato positivo del piano.

Una volta dato il comando di rotazione, tutti i movimenti successivi verranno eseguiti in questo sistema ruotato. In effetti, gli assi **X** e **Y** della macchina ruoteranno della quantità specificata da **R**.

**Esempio:**

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro
G0 X0.0 Y0.0 Z1.0          ; Posizione rapida al punto
G68 X0.0 Y0.0 R45.0        ; Ruotare di 45° in senso antiorario attorno a X0, Y0
G0 X1.0                    ; Posizione rapida a X1
G69                        ; Cancellare la rotazione
M30                        ; Fine programma e riavvolgimento
```

Nel programma sopra, la macchina si sposterà a **X0, Y0**, quindi avvierà la rotazione del sistema di coordinate di **45°**. Il movimento successivo è un movimento puramente sull'asse **X** fino a **X1**. Tuttavia, poiché il sistema di coordinate è stato ruotato, l'asse **X** attuale è effettivamente ruotato di **45°** rispetto all'asse **X** reale della macchina. Quando il movimento avverrà, sia gli assi **X** che **Y** si muoveranno al punto programmato. In questo caso, i **DRO** (Digital Readouts) mostreranno **X.7071** e **Y.7071**.

![[Pasted image 20250218213149.png]]
**Figura 68-1**: Rotazione del sistema di coordinate (G68 X0 Y0 R45)  

Le coordinate **X.7071** e **Y.7071** possono essere verificate utilizzando la geometria semplice o le funzioni trigonometriche. La rotazione del sistema di coordinate è utile in molte applicazioni. Combinato con una sonda per parti, questa funzione può fornire molta potenza e precisione. Quando si sonda una parte per trovarne la posizione, è anche possibile determinare se la parte è fissata in modo quadrato rispetto agli assi o se è orientata a un certo angolo. Se la parte è inclinata, può essere automaticamente compensata, risultando in pezzi di qualità superiore.

---
### G69 – Annullamento Rotazione del Sistema di Coordinate

Annulla un comando di rotazione del sistema di coordinate. La macchina ritorna alla funzione normale.

---

### G73-G89 – Cicli di Lavorazione Preimpostati

I cicli preimpostati sono codici G speciali utilizzati per semplificare la programmazione. Consulta la sezione sui Cicli di Lavorazione Preimpostati di questo manuale per informazioni dettagliate.

- **G73** – Ciclo di Foratura ad Alta Velocità

```gcode
G73 X_ Y_ Z_ R_ Q_ F_
```

- **G74** – Filettatura Inversa

```gcode
G74 X_ Y_ Z_ R_ F_
```

- **G76** – Alesatura Fine

```gcode
G76 X_ Y_ Z_ R_ I_ J_ P_ F_
```

- **G80** – Annullamento Ciclo Preimpostato

```gcode
G80
```

- **G81** – Foratura

```gcode
G81 X_ Y_ Z_ R_ F_
```

- **G82** – Foratura a Punto

```gcode
G82 X_ Y_ Z_ R_ P_ F_
```

- **G83** – Foratura Profonda con Pecking

```gcode
G83 X_ Y_ Z_ R_ Q_ F_
```

- **G84** – Filettatura

```gcode
G84 X_ Y_ Z_ R_ F_
```

- **G85** – Alesatura, Ritiro a Velocità di Avanzamento, Mandrino Acceso

```gcode
G85 X_ Y_ Z_ R_ F_
```

- **G86** – Alesatura, Ritiro a Velocità Rapida, Mandrino Spento

```gcode
G86 X_ Y_ Z_ R_ F_
```

- **G87** – Alesatura da Retro

```gcode
G87 X_ Y_ Z_ R_ I_ J_ F_
```

- **G88** – Alesatura, Ritiro Manuale

```gcode
G88 X_ Y_ Z_ R_ P_ F_
```

- **G89** – Alesatura, Dwell, Ritiro a Velocità di Avanzamento, Mandrino Acceso

```gcode
G89 X_ Y_ Z_ R_ P_ F_
```

---

### G90/G91 – Modalità di Posizionamento Assoluto/Incrementale

In modalità di posizionamento assoluto, la macchina si sposterà verso la posizione comandata nel sistema di coordinate utente attivo.

**Esempio:** Scrivi un programma per muoversi alle posizioni dei fori nella figura 90-1 in modalità di posizionamento assoluto. Si assume che la macchina parta dalla posizione **X0, Y0**, e termini il programma su **X0, Y0**.
![[Pasted image 20250218213657.png]]

**Figura 90-1**: Esempio di Schema dei Fori

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro
G90 Modalità di posizionamento assoluto
G0 X1.0 Y-1.0               ; Rapido al 1° foro
X2.0                        ; Rapido al 2° foro
X3.0                        ; Rapido al 3° foro
X0.0 Y0.0                   ; Rapido indietro a 0,0
M30                         ; Fine programma e riavvolgimento
```

In modalità di posizionamento incrementale, i movimenti comandati sono interpretati come distanza e direzione dalla posizione corrente. Un comando di **X1** sposterà di 1 nell'indirizzo positivo, **NON** necessariamente al punto **X1** nel sistema di coordinate utente.

**Esempio:** Scrivi un programma per muoversi alle posizioni dei fori nella figura 90-1 in modalità di posizionamento incrementale. Si assume che la macchina parta dalla posizione **X0, Y0**, e termini il programma su **X0, Y0**.

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro
G91 Modalità di posizionamento incrementale
G0 X1.0 Y-1.0               ; Rapido al 1° foro
X1.0                        ; Rapido al 2° foro
X1.0                        ; Rapido al 3° foro
X-3.0 Y1.0                  ; Rapido indietro a 0,0
M30                         ; Fine programma e riavvolgimento
```

Confronta questo con il programma di **G90**. Poiché il punto di partenza è **X0, Y0** in entrambi gli esempi, il movimento al 1° foro è lo stesso. Tuttavia, se la macchina fosse partita da **X1, Y1**, il programma in modalità assoluta sarebbe comunque corretto, mentre il programma incrementale sarebbe spostato dalla posizione di inizio. Per questo motivo, è importante assicurarsi che la modalità corretta sia attivata per il programma in uso. Una buona linea di avvio sicura conterrà sempre un **G90** o **G91**. Questi codici G sono modal e rimarranno attivi finché non ne viene specificato un altro.

---
### G90.1/G91.1 – Modalità Centro Arco Assoluto/Incrementale

Questa impostazione influisce sugli archi quando programmati nel formato **I**, **J**, **K**. In modalità **centro arco assoluto**, i valori **I**, **J**, **K** designano la posizione del centro dell'arco nel sistema di coordinate utente. In modalità **centro arco incrementale**, i valori **I**, **J**, **K** designano la distanza e la direzione dal punto di partenza al centro dell'arco. Vedi la figura 2-1 per una descrizione grafica.
![[Pasted image 20250218213829.png]]

**Figura 2-1:** Traiettoria del punto utensile in interpolazione circolare e elicoidale (G02).

- **I (Assoluto)**
- **J (Assoluto)**
- **I (Incrementale)**
- **J (Incrementale)**
- **R**
- **Punto di partenza**
- **Zero di lavoro**
- **Y**
- **X**

---

**Esempio:** Programma un arco centrato a **1.0, 0.0** nel piano **XY** con raggio **2**. Punto di partenza a **3.0, 0.0** e rotazione di 90 gradi in senso antiorario. Programma due volte, una in modalità centro arco incrementale e una in modalità centro arco assoluto.

#### In modalità centro arco incrementale (**G91.1**):

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro
G91.1 Modalità centro arco incrementale
T1 M6 Cambio utensile
S2500 M3 Avvio mandrino
G0 X3.0 Y0.0 Posizionamento al punto di partenza X e Y
G43 H1 Z.5 Attiva il offset utensile 1 e sposta al piano rapido Z
G1 Z0.0 F10.0 Pieno avanzamento su Z
G3 X1.0 Y2.0 I-2.0 J0.0 F10.0 Movimento arco
G0 Z.5 Retrattamento Z al piano rapido
G0 G53 Z0.0 Ritorno Z alla posizione home
M30 Fine programma e riavvolgimento
```

#### In modalità centro arco assoluto (**G90.1**):

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro
G90.1 Modalità centro arco assoluto
T1 M6 Cambio utensile
S2500 M3 Avvio mandrino
G0 X3.0 Y0.0 Posizionamento al punto di partenza X e Y
G43 H1 Z.5 Attiva il offset utensile 1 e sposta al piano rapido Z
G1 Z0.0 F10.0 Pieno avanzamento su Z
G3 X1.0 Y2.0 I1.0 J0.0 F10.0 Movimento arco
G0 Z.5 Retrattamento Z al piano rapido
G0 G53 Z0.0 Ritorno Z alla posizione home
M30 Fine programma e riavvolgimento
```

Si noti la differenza nei valori **I** nei programmi di esempio. Entrambi i programmi produrranno lo stesso arco.

---
### G92 – Impostazione Sistema di Coordinate Locale

Il sistema di coordinate può essere impostato utilizzando **G92** nel programma. Questa funzione differisce da **G52** (Spostamento del Sistema di Coordinate Locale) nel modo in cui viene specificato. Mentre **G52** è specificato con valori di spostamento, **G92** è specificato con la posizione desiderata degli assi. L'effetto è globale e dovrebbe essere usato con cautela.

**Formato:**

```gcode
G92 X__ Y__ Z__ A__ B__ C__
```

Utilizzando il formato sopra, specificare un valore per l'asse desiderato. Quando **G92** è specificato, i valori degli **DRO** di posizione vengono aggiornati con i valori specificati. L'impostazione del sistema di coordinate locale sarà annullata quando viene specificato **G92.1** o quando il sistema viene resettato.

**Esempio:**

```gcode
G0 G90 G54 G17 G40 G49 G80   ; Linea di avvio sicuro
G0 X4.0 Y0.0 Z1.0          ; Movimento rapido, posizione corrente X4, Y0, Z1
G92 X1.0 Y2.0 Z3.0         ; Imposta il sistema di coordinate locale, posizione corrente X1, Y2, Z3
G92.1                       ; Annulla il sistema di coordinate locale, posizione corrente X4, Y0, Z1
M30                         ; Fine programma e riavvolgimento
```

**Nota:**  
**G92** veniva usato per l'impostazione dell'offset di fissaggio prima che gli offset di fissaggio fossero disponibili. Si consiglia di utilizzare gli offset di fissaggio invece di **G92**. La quantità di offset impostata con **G92** non è immediatamente nota all'utente, pertanto i risultati possono essere imprevedibili quando gli offset di fissaggio e **G92** sono combinati.

---
### G93 – Avanzamento Tempo Inverso

L'avanzamento tempo inverso viene utilizzato più comunemente per i movimenti della macchina che includono almeno un asse rotante, ma non è l'unica applicazione. Invece di specificare una velocità, si specifica un tempo per completare il movimento. La formula seguente viene utilizzata per determinare **F**:

F=1tempo (min)=feedrate (unitaˋ/min)distanza (unitaˋ)F = \frac{1}{\text{tempo (min)}} = \frac{\text{feedrate (unità/min)}}{\text{distanza (unità)}}

Quando l'avanzamento tempo inverso è attivo, una parola **F** è richiesta in ogni blocco di codice contenente un movimento di avanzamento.

---
### G94 – Avanzamento Per Minuto

Impostazione di feedrate più comune. Specificare il feedrate desiderato in unità/minuto. In questa modalità, il feedrate è modulare e non è richiesto in tutti i blocchi di movimento di avanzamento.

---
### G95 – Avanzamento Per Rivoluzione

Nel caso dei fresatrici, l'impostazione di avanzamento per rivoluzione è più comunemente usata per i cicli di filettatura. In questa modalità, il feedrate viene specificato in unità/rivoluzione del mandrino. Nel caso della filettatura, il feedrate può essere impostato come il passo della filettatura. Per ogni rivoluzione del mandrino, la macchina sposterà le unità specificate. La modalità di avanzamento per rivoluzione richiede il feedback delle RPM dal mandrino.

---
### G96 – Velocità Superficiale Costante

La velocità del mandrino può essere specificata in due modi. Uno di questi è la velocità superficiale costante. In questa modalità, Mach cercherà di mantenere la velocità superficiale costante in base al diametro di taglio. La velocità superficiale viene specificata in unità superficiali per minuto. In modalità pollici, questa è espressa in piedi superficiali per minuto, mentre in modalità millimetri è espressa in metri superficiali per minuto.

---
### G97 – RPM Costante

In questa modalità, la velocità del mandrino è specificata in rivoluzioni al minuto. Questa è la configurazione più comune per le fresatrici.

---
### G98 – Ritorno al Punto Iniziale

Specifica che un ciclo preimpostato termini al livello iniziale di **Z**. La macchina tornerà anche al punto iniziale prima di eseguire un movimento rapido verso la posizione successiva. Il ritorno al punto iniziale è utile per evitare passi nei pezzi o nei fermi dei fissaggi senza aggiungere un tempo significativo al ciclo. Vedi la figura **98-1**.
![[Pasted image 20250218214019.png]]
### G99 – R Point Return

Specifica che un ciclo preimpostato termini al livello **R** programmato. Vedi la figura **98-1**. Quando si eseguono fori in una piastra piatta, **G99** può essere utilizzato per ridurre i movimenti eccessivi della macchina, diminuendo il tempo di ciclo.

---

### Cicli Preimpostati

| **Ciclo**                                                               | **Comando**                 |
| ----------------------------------------------------------------------- | --------------------------- |
| **G73** – Foratura a pecking ad alta velocità                           | G73 X_ Y_ Z_ R_ Q_ F_       |
| **G74** – Filettatura inversa                                           | G74 X_ Y_ Z_ R_ F_          |
| **G76** – Alesatura fine                                                | G76 X_ Y_ Z_ R_ I_ J_ P_ F_ |
| **G80** – Annulla ciclo preimpostato                                    | G80                         |
| **G81** – Foratura                                                      | G81 X_ Y_ Z_ R_ F_          |
| **G82** – Faccia di posizionamento                                      | G82 X_ Y_ Z_ R_ P_ F_       |
| **G83** – Foratura profonda con pecking                                 | G83 X_ Y_ Z_ R_ Q_ F_       |
| **G84** – Filettatura                                                   | G84 X_ Y_ Z_ R_ F_          |
| **G85** – Alesatura, ritrazione con avanzamento, mandrino acceso        | G85 X_ Y_ Z_ R_ F_          |
| **G86** – Alesatura, ritrazione rapida, mandrino spento                 | G86 X_ Y_ Z_ R_ F_          |
| **G87** – Alesatura a ritroso                                           | G87 X_ Y_ Z_ R_ I_ J_ F_    |
| **G88** – Alesatura, ritrazione manuale                                 | G88 X_ Y_ Z_ R_ P_ F_       |
| **G89** – Alesatura, dwell, ritrazione con avanzamento, mandrino acceso | G89 X_ Y_ Z_ R_ P_ F_       |

I **cicli preimpostati** vengono utilizzati per semplificare la programmazione. Ad esempio, forare un buco da 1 pollice con un incremento di foratura di 0,1 pollice richiederebbe 30 righe di codice normale, ma con un ciclo preimpostato questo stesso foro può essere completato in solo 2 righe di codice. Inoltre, se sono necessari più fori, basta aggiungere solo 1 riga di codice per ogni foro.

Esistono diversi cicli preimpostati per diversi tipi di fori, inclusi foratura, alesatura e filettatura.

---

### Parametri Comuni nei Cicli di Foratura

I cicli di foratura comportano parametri simili, ma il significato di ciascun parametro può cambiare a seconda di due impostazioni:

1. **Modalità G90/G91 (Assoluto/Incrementale):** Come definito precedentemente nel manuale.
2. **Selezione del punto di ritorno:** **G98** per ritorno al punto iniziale o **G99** per ritorno al punto **R**.

La selezione del piano (G17/G18/G19) può anche influenzare i cicli di foratura. La posizionamento avverrà nel piano attivo, e l'operazione di foratura avverrà sull'asse normale. Ad esempio, in **G17** (Piano XY) la posizione del foro sarà nel piano XY e l'asse di foratura sarà **Z**. In **G18** (Piano ZX), il posizionamento sarà nel piano ZX e l'asse di foratura sarà **Y**. Per gli scopi di questo manuale, tutti gli esempi e le definizioni saranno nel piano **XY** (**G17**).

---

### Formato Base di un Ciclo Preimpostato

Il formato base di un ciclo preimpostato è il seguente:

```gcode
Gcc G98/99 Xxx Yyy Zzz Qqq Rrr Ppp Lll Fff
Xxn Yyn
G80
```

Dove i parametri sono definiti come segue:

| **Parametro** | **Descrizione**                                                                                                                                                               |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **cc**        | Numero del ciclo preimpostato desiderato (es. 81, 83, 74, ecc.)                                                                                                               |
| **xx**        | In **G90**: Posizione X del centro del primo foro rispetto al punto zero attuale. In **G91**: Distanza e direzione lungo l'asse X dal punto attuale al centro del primo foro. |
| **yy**        | In **G90**: Posizione Y del centro del primo foro rispetto al punto zero attuale. In **G91**: Distanza e direzione lungo l'asse Y dal punto attuale al centro del primo foro. |
| **zz**        | In **G90**: Posizione Z del fondo del foro rispetto al punto zero attuale. In **G91**: Distanza e direzione lungo l'asse Z, dal punto **R**, fino al fondo del foro.          |
| **qq**        | Incremento di foratura (peck) se foratura di fori profondi, sempre positivo.                                                                                                  |
| **rr**        | Piano di ritrazione, posizione di ritrazione tra i peck, in modalità **G99** questo è il piano rapido.                                                                        |
| **pp**        | Dwell, in secondi, al fondo del foro.                                                                                                                                         |
| **ll**        | Numero di ripetizioni.                                                                                                                                                        |
| **ff**        | Feedrate.                                                                                                                                                                     |
| **xn**        | Posizione del foro **n** sull'asse X, con le stesse regole applicate a **xx**.                                                                                                |
| **yn**        | Posizione del foro **n** sull'asse Y, con le stesse regole applicate a **yy**.                                                                                                |
![[Pasted image 20250218214210.png]]

---
### Nota Importante

Non tutti i parametri appariranno in tutti i cicli, e ci sono alcuni casi speciali che verranno discussi in seguito.

### G80 – Canned Cycle Cancel

Per terminare un ciclo preimpostato, è necessario chiamare **G80**. **G80** dovrebbe essere specificato su una riga separata per evitare movimenti indesiderati. Ecco un esempio di codice:

```gcode
G0 G90 G54 G17 G40 G49 G80  ; Linea di partenza sicura
T1 M6                     ; Cambio utensile
S2500 M3                  ; Avvio del mandrino
G0 X1.0 Y-1.0             ; Posizionamento al punto di partenza X e Y
G43 H1 Z.5                ; Attivazione del offset utensile 1 e movimento al punto iniziale Z
G81 G99 X1.0 Y-1.0 Z-1.0 R.25 F10  ; Inizio ciclo di foratura
X2.0 Y-1.0                ; Foratura secondo foro
X3.0 Y-1.0                ; Foratura terzo foro
G80                       ; Annullamento ciclo preimpostato
G0 G53 Z0                 ; Ritorno Z al punto zero
M30                       ; Fine programma e riavvolgimento
```

---

### G81 – Drilling (Foratura)

**G81** avvia un ciclo di foratura semplice. Lo strumento si sposta semplicemente nella posizione desiderata, alimenta fino al fondo del foro e poi si ritira rapidamente al punto **R** o al punto iniziale.

Il formato di **G81** è il seguente:

```gcode
G81 X__ Y__ Z__ R__ L__ F__
```

Dove:

- **X, Y** – Posizione del foro nel piano XY.
- **Z** – Punto finale del foro (profondità).
- **R** – Piano di ritrazione.
- **L** – Numero di ripetizioni del foro (opzionale).
- **F** – Velocità di avanzamento (feedrate).

#### Esempio di Foratura:

```gcode
G81 X1.0 Y1.0 Z-1.0 R0.1 F10
X2.0 Y1.0
X3.0 Y1.0
G80
```

In questo esempio:

- **G81** avvia il ciclo di foratura.
- Il primo foro è posizionato a **X1.0 Y1.0**, con una profondità di **Z-1.0** e una ritrazione di **R0.1**.
- Il ciclo continua con il secondo e terzo foro alle posizioni **X2.0 Y1.0** e **X3.0 Y1.0**.
- **G80** annulla il ciclo preimpostato.

Il ciclo **G81** è comunemente utilizzato per forare in modo semplice e rapido, risparmiando spazio nel programma rispetto alla scrittura di movimenti di foratura separati per ciascun foro.

![[Pasted image 20250218214656.png]]
Esempio: Crea il programma per i fori mostrati nella Figura 2.

```gcode
G0 G90 G54 G17 G40 G49 G80  ; Linea di partenza sicura
T1 M6                     ; Cambio utensile
S2500 M3                  ; Avvio del mandrino
G0 X1.0 Y-1.0             ; Posizionamento al punto di partenza X e Y
G43 H1 Z.5                ; Attivazione dell'offset utensile 1 e movimento al punto iniziale Z
G81 G99 X1.0 Y-1.0 Z-1.0 R.25 F10  ; Inizio ciclo di foratura
X2.0 Y-1.0                ; Secondo foro
X3.0 Y-1.0                ; Terzo foro
G80                       ; Annullamento del ciclo preimpostato
G0 G53 Z0                 ; Ritorno Z al punto zero
M30                       ; Fine programma e riavvolgimento
```

---

**G82 – Spot Face (Faccia di Appoggio):** Il ciclo **G82** aggiunge la possibilità di fare una pausa (dwell) alla base del foro per un periodo di tempo specificato. Il movimento dell'utensile è lo stesso del ciclo **G81**, ma con la pausa è possibile ottenere una maggiore precisione e finitura nella parte inferiore del foro. Questo è utile per smussare, controforare e fare facce di appoggio. Il formato di **G82** è il seguente:

```gcode
G82 X__ Y__ Z__ R__ P__ L__ F__
```

Dove:

- **X, Y** – Posizione del foro nel piano XY.
- **Z** – Punto finale del foro (profondità).
- **R** – Piano di ritrazione.
- **P** – Tempo di attesa (dwell) alla base del foro (in secondi).
- **L** – Numero di ripetizioni del ciclo.
- **F** – Velocità di avanzamento (feedrate).

---

**Esempio:** Crea un programma di smussatura (chamfering) per i fori mostrati nella figura 2, con una pausa di **0.2 secondi**.

```gcode
G0 G90 G54 G17 G40 G49 G80  ; Linea di partenza sicura
T1 M6                     ; Cambio utensile
S2500 M3                  ; Avvio del mandrino
G0 X1.0 Y-1.0             ; Posizionamento al punto di partenza X e Y
G43 H1 Z.5                ; Attivazione dell'offset utensile 1 e movimento al punto iniziale Z
G82 G99 X1.0 Y-1.0 Z-0.2 P0.2 R0.25 F10  ; Inizio ciclo di foratura con dwell
X2.0 Y-1.0                ; Smussatura del secondo foro
X3.0 Y-1.0                ; Smussatura del terzo foro
G80                       ; Annullamento del ciclo preimpostato
G0 G53 Z0                 ; Ritorno Z al punto zero
M30                       ; Fine programma e riavvolgimento
```

**G83 – Peck Drilling (Foratura a Pezzi):** La foratura a pezzi (Peck drilling) è un ciclo utilizzato per forare fori profondi. Questo ciclo consente di rompere e rimuovere i trucioli e di applicare meglio il refrigerante, ritirando completamente l'utensile dal foro tra un pezzo e l'altro. Il movimento di ritiro e il ritorno alla profondità precedente sono movimenti rapidi, mentre ogni pezzo è un movimento di avanzamento alla velocità di avanzamento specificata. La posizione finale del foro (Z) sarà determinata dalla modalità **G98/G99**. Il formato è il seguente:

```gcode
G83 X__ Y__ Z__ Q__ R__ L__ F__
```

Dove:

- **X, Y** – Posizione del foro nel piano XY.
- **Z** – Punto finale del foro (profondità).
- **Q** – Profondità del pezzo (peck depth).
- **R** – Piano di ritrazione.
- **L** – Numero di ripetizioni del ciclo.
- **F** – Velocità di avanzamento (feedrate).

![[Pasted image 20250218214912.png]]

**Esempio:** Crea il programma per i fori mostrati nella figura 2 utilizzando una profondità di pezzo di **0.1**.

```gcode
G0 G90 G54 G17 G40 G49 G80  ; Linea di partenza sicura
T1 M6                     ; Cambio utensile
S2500 M3                  ; Avvio del mandrino
G0 X1.0 Y-1.0             ; Posizionamento al punto di partenza X e Y
G43 H1 Z.5                ; Attivazione dell'offset utensile 1 e movimento al punto iniziale Z
G83 G99 X1.0 Y-1.0 Z-1.0 Q.1 R.25 F10  ; Inizio ciclo di foratura a pezzi
X2.0 Y-1.0                ; Foratura del secondo foro
X3.0 Y-1.0                ; Foratura del terzo foro
G80                       ; Annullamento del ciclo preimpostato
G0 G53 Z0                 ; Ritorno Z al punto zero
M30                       ; Fine programma e riavvolgimento
```

**G73 – High Speed Peck (Foratura a Pezzi ad Alta Velocità):** In materiali che producono trucioli lunghi e filanti, può essere utilizzato un ciclo di foratura a pezzi ad alta velocità (High Speed Peck) per romperli. A differenza del ciclo **G83** che ritrae completamente l'utensile dal foro dopo ogni pezzo, il ciclo **G73** ritrae solo di **0.100 pollici**. Questa breve ritrazione aiuta a ridurre i tempi di ciclo quando una ritrazione completa non è necessaria. Il formato è il seguente:

```gcode
G73 X__ Y__ Z__ Q__ R__ L__ F__
```

Dove:

- **X, Y** – Posizione del foro nel piano XY.
- **Z** – Punto finale del foro (profondità).
- **Q** – Profondità del pezzo (peck depth).
- **R** – Piano di ritrazione.
- **L** – Numero di ripetizioni del ciclo.
- **F** – Velocità di avanzamento (feedrate).

![[Pasted image 20250218215106.png]]

**Esempio:** Crea il programma per i fori mostrati nella figura 2 utilizzando una profondità di pezzo di **0.025**.

```gcode
G0 G90 G54 G17 G40 G49 G80  ; Linea di partenza sicura
T1 M6                     ; Cambio utensile
S2500 M3                  ; Avvio del mandrino
G0 X1.0 Y-1.0             ; Posizionamento al punto di partenza X e Y
G43 H1 Z.5                ; Attivazione dell'offset utensile 1 e movimento al punto iniziale Z
G73 G99 X1.0 Y-1.0 Z-1.0 Q.1 R.25 F10  ; Inizio ciclo di foratura a pezzi ad alta velocità
X2.0 Y-1.0                ; Foratura del secondo foro
X3.0 Y-1.0                ; Foratura del terzo foro
G80                       ; Annullamento del ciclo preimpostato
G0 G53 Z0                 ; Ritorno Z al punto zero
M30                       ; Fine programma e riavvolgimento
```

### Tapping

**G84 – Tapping a Destra (Right Hand Tapping):** Il ciclo di filettatura (tapping) viene utilizzato per creare fori filettati utilizzando una maschiatura. La maschiatura richiede che la velocità del mandrino (rpm) e la velocità di avanzamento dell'asse Z siano sincronizzate, in relazione alla passo della filettatura che si sta realizzando. Esistono due modi per ottenere questa sincronizzazione tra velocità del mandrino e velocità di avanzamento dell'asse Z.

1. **Feed per rivoluzione (G95):** Nella modalità "feed per rivoluzione", il valore di avanzamento specificato corrisponderà semplicemente al passo della filettatura. Le filettature metriche sono classificate dal passo della filettatura, ad esempio, la filettatura **M8x1.25mm** ha un passo di **1.25mm**. Le filettature unificate sono classificate in base al numero di filetti per pollice (TPI), e per calcolare il passo occorre dividere 1 pollice per il TPI. Per esempio, per un fastener **¼-20**, calcoliamo **1/20 = 0.05**, che è il passo della filettatura.
    
2. **Feed per minuto (G94):** Se la macchina non ha un sistema di feedback sulla velocità del mandrino, è possibile programmare il ciclo di maschiatura in modalità "feed per minuto" (G94). In questo caso, per calcolare correttamente la velocità di avanzamento in base alla velocità del mandrino e al passo della filettatura, si utilizza la formula:  
    **RPM * Passo = IPM (Inches per Minute)**  
    Per esempio, per una filettatura **¼-20** a **1500 RPM**, calcoliamo il passo come **1/20 = 0.05**, quindi la velocità di avanzamento sarà **1500 * 0.05 = 75 IPM**. È importante notare che se la velocità del mandrino cambia, la velocità di avanzamento (IPM) dovrà essere adeguata di conseguenza.
    

**Formato del Codice:**

```gcode
G84 X__ Y__ Z__ R__ L__ F__
```

Dove:

- **X, Y** – Posizione del foro nel piano XY
- **Z** – Punto finale del foro (profondità)
- **R** – Piano di ritrazione
- **L** – Numero di ripetizioni
- **F** – Velocità di avanzamento (feedrate)

**Movimento del Ciclo di Maschiatura:** Il movimento del ciclo di maschiatura è simile a un ciclo di foratura diretto, con l'azione principale che dipende dalla rotazione del mandrino. Il mandrino deve essere avviato in direzione oraria prima di avviare il ciclo **G84**. La macchina si sposterà quindi alla posizione del foro, l'asse **Z** si sposterà al piano **R**, e l'asse **Z** avanzerà fino alla profondità specificata. Una volta raggiunta la profondità, il mandrino e l'asse **Z** si fermeranno e invertendo la direzione, si ritireranno dal foro.

Si raccomanda di utilizzare una testa di maschiatura speciale che permette all'utensile di "galleggiare" leggermente per compensare eventuali variazioni nelle velocità di mandrino, avanzamento e accelerazioni della macchina, specialmente nel fondo del foro.

**Attenzione:** Non cambiare la velocità di avanzamento o la velocità del mandrino durante il ciclo di maschiatura, poiché potrebbe danneggiare l'utensile e il pezzo. Durante il ciclo, gli override della velocità di avanzamento e della velocità del mandrino sono disabilitati, e la macchina lavorerà al 100% dell'override. Anche la funzione **feed hold** (pausa avanzamento) è disabilitata durante il ciclo. Se viene premuto **feed hold**, il movimento si fermerà al termine del ciclo di maschiatura.
![[Pasted image 20250218215220.png]]
**Esempio:** Creare il programma per maschiare i fori mostrati nella figura 2 fino a una profondità di **0.500** utilizzando un maschio **3/8-16** in modalità **feed/min**.

Calcoliamo il passo del maschio:

1. **Passo del maschio** per una filettatura **3/8-16**:  
    **1/16 = 0.0625**  
    **RPM * Passo = Feedrate (IPM)**  
    Per esempio, con **RPM = 1000**, calcoliamo:  
    **1000 * 0.0625 = 62.5 IPM**

Il programma sarà il seguente:

```gcode
G0 G90 G54 G17 G40 G49 G80 Safe start line
T1 M6 Tool change
S1000 M3 Start spindle
G0 X1.0 Y-1.0 Position to X and Y start point
G43 H1 Z.5 Activate tool offset 1 and move to Z initial point
G84 G99 X1.0 Y-1.0 Z-.500 R.25 F62.5 Tapping cycle start
X2.0 Y-1.0 Tap second hole
X3.0 Y-1.0 Tap third hole
G80 Canned cycle cancel
G0 G53 Z0 Return Z to home
M30 Program end and rewind
```

---

**G74 – Tapping a Sinistra (Left Hand Tapping):**  
Il ciclo di maschiatura a sinistra è simile a quello a destra (**G84**), ma viene utilizzato per creare filettature a sinistra. Prima di chiamare il ciclo **G74**, il mandrino deve essere avviato in direzione inversa (antioraria).

**G84.2/G84.3 – Tapping Rigido a Destra e a Sinistra (Rigid Tapping):**  
Il tapping rigido può essere eseguito su macchine compatibili. In questo caso, il maschio è tenuto rigidamente nel mandrino senza l'uso di un supporto di tipo tensione/compressione. Questo richiede che la macchina abbia il controllo preciso della velocità del mandrino, dell'avanzamento degli assi e del feedback preciso sulla velocità del mandrino. L'asse di maschiatura è sincronizzato elettronicamente con la velocità del mandrino. Utilizzare **G84.2** per tapping a destra e **G84.3** per tapping a sinistra.

**Formato del Codice:**

```gcode
G84.2/84.3 X__ Y__ Z__ R__ P__ L__ F__ J__
```

Dove:

- **X, Y** – Posizione del foro nel piano XY
- **Z** – Punto finale del foro (profondità)
- **R** – Piano di ritrazione
- **P** – Dwell in secondi
- **L** – Numero di ripetizioni
- **F** – Velocità di avanzamento (feedrate)
- **J** – Velocità del mandrino per la ritrazione

**Esempio:** Creare il programma per maschiare i fori mostrati nella figura 2 fino a una profondità di **0.500** utilizzando un maschio **3/8-16** con feed/min. Eseguire il tapping a **1000 RPM** e la ritrazione a **2000 RPM**.

2. **Passo del maschio**:  
    **1/16 = 0.0625**  
    **1000 * 0.0625 = 62.5 IPM**

Il programma sarà:

```gcode
G0 G90 G54 G17 G40 G49 G80 Safe start line
T1 M6 Tool change
S1000 M3 Start spindle
G0 X1.0 Y-1.0 Position to X and Y start point
G43 H1 Z.5 Activate tool offset 1 and move to Z initial point
G84.2 G99 X1.0 Y-1.0 Z-.500 R.25 F62.5 J2000 Rigid tapping cycle start
X2.0 Y-1.0 Tap second hole
X3.0 Y-1.0 Tap third hole
G80 Canned cycle cancel
G0 G53 Z0 Return Z to home
M30 Program end and rewind
```

### Boring

**G76 – Ciclo di Foratura Fine (Fine Boring):**  
Il ciclo di foratura fine consente all'utente di fermare il mandrino e spostare lo strumento lontano dalla parete prima di ritirarsi. Questo permette di fare una ritrazione rapida senza lasciare graffi sulla parete del foro.

**Formato del Codice:**

```gcode
G76 X__ Y__ Z__ R__ I__ J__ P__ L__ F__
```

Dove:

- **X, Y** – Posizione del foro nel piano XY
- **Z** – Punto finale del foro
- **R** – Piano di ritrazione
- **I** – Distanza e direzione di spostamento in X
- **J** – Distanza e direzione di spostamento in Y
- **P** – Dwell in secondi (tempo di pausa)
- **L** – Numero di ripetizioni
- **F** – Velocità di avanzamento (feedrate)
![[Pasted image 20250218215359.png]]
Il ciclo di foratura fine include:

1. Movimento a velocità di avanzamento (**F**)
2. Movimento rapido
3. Dwell, fermata del mandrino, e spostamento definito da **I** e **J**

Il programma di esempio:

```gcode
G0 G90 G54 G17 G40 G49 G80 Safe start line
T1 M6 Tool change
S2500 M3 Start spindle
G0 X1.0 Y-1.0 Position to X and Y start point
G43 H1 Z.5 Activate tool offset 1 and move to Z initial point
G76 G99 X1.0 Y-1.0 Z-1.0 R.25 I-.025 J0 F10.0 Fine bore cycle, shift X-.025 at bottom
X2.0 Y-1.0 Bore second hole
X3.0 Y-1.0 Bore third hole
G80 Canned cycle cancel
G0 G53 Z0 Return Z to home
M30 Program end and rewind
```

**Funzionamento del ciclo G76:**

4. Dopo che la macchina ha alimentato fino al fondo del foro, si farà una pausa per il tempo specificato dal dwell (**P**).
5. Il mandrino si fermerà nella posizione orientata prima di eseguire lo spostamento definito da **I** (per X) e **J** (per Y).
6. Su macchine con una funzione di orientamento del mandrino (**M19**), l'orientamento e lo spostamento sono automatici. Se la macchina non supporta questa funzione, è necessario eseguire manualmente l'orientamento del mandrino. In tal caso, è possibile utilizzare un macro **M19.mcs** per fermare il mandrino e chiedere un fermo obbligatorio (**M0**) per orientare il mandrino prima che venga eseguito lo spostamento.

Esempio di macro per orientamento manuale:

```gcode
INSERT MANUAL M19 MACRO PROGRAM HERE
```

**G85 – Foratura, Retrattamento con Velocità di Avanzamento:**  
Il ciclo G85 è un ciclo di foratura rettilineo, comunemente utilizzato per la foratura o la alesatura. La ritrazione avviene alla velocità di avanzamento programmata, con il mandrino acceso.

**Formato del Codice:**

```gcode
G85 X__ Y__ Z__ R__ L__ F__
```

Dove:

- **X, Y** – Posizione del foro nel piano XY
- **Z** – Punto finale del foro
- **R** – Piano di ritrazione
- **L** – Numero di ripetizioni
- **F** – Velocità di avanzamento (feedrate)

**Movimento del Ciclo G85:**

- Il movimento avviene alla velocità di avanzamento (**F**)
- Il movimento è rapido quando necessario
- **Punto iniziale**: Posizione di partenza
- **Piano di ritrazione** (**R**)
- **Profondità finale del foro** (**Z**)
![[Pasted image 20250218215703.png]]

**Esempio:** Crea il programma per forare i fori mostrati nella figura 2.

```gcode
G0 G90 G54 G17 G40 G49 G80 Safe start line
T1 M6 Tool change
S2500 M3 Start spindle
G0 X1.0 Y-1.0 Position to X and Y start point
G43 H1 Z.5 Activate tool offset 1 and move to Z initial point
G85 G99 X1.0 Y-1.0 Z-1.0 R.25 F10.0 Boring cycle start
X2.0 Y-1.0 Bore second hole
X3.0 Y-1.0 Bore third hole
G80 Canned cycle cancel
G0 G53 Z0 Return Z to home
M30 Program end and rewind
```

**Funzionamento del ciclo G85:**

1. La macchina si muove alla velocità di avanzamento (**F**) per forare il foro fino alla profondità desiderata (**Z**).
2. Al termine della foratura, la macchina si ritrae alla velocità di avanzamento programmata, con il mandrino acceso.

**G86 – Foratura, Retrattamento Rapido:**  
Il ciclo G86 è un ciclo di foratura rettilineo. Prima di ritirarsi dal foro, il mandrino viene fermato. La ritrazione avviene quindi alla velocità rapida. Questo processo può lasciare dei graffi o più graffi sulla parete del foro, dove le lame di taglio sono in contatto.

**Formato del Codice:**

```gcode
G86 X__ Y__ Z__ R__ L__ F__
```

Dove:

- **X, Y** – Posizione del foro nel piano XY
- **Z** – Punto finale del foro
- **R** – Piano di ritrazione
- **L** – Numero di ripetizioni
- **F** – Velocità di avanzamento (feedrate)

**Movimento del Ciclo G86:**

- La macchina si muove alla velocità di avanzamento (**F**) fino a raggiungere la profondità del foro (**Z**).
- Prima di ritirarsi, il mandrino si ferma.
- La ritrazione avviene alla velocità rapida (**rapido**), ma può lasciare dei graffi dove le lame di taglio toccano la parete del foro.

![[Pasted image 20250218215824.png]]

**Esempio:** Crea il programma per forare i fori mostrati nella figura 2.

```gcode
G0 G90 G54 G17 G40 G49 G80 Safe start line
T1 M6 Tool change
S2500 M3 Start spindle
G0 X1.0 Y-1.0 Position to X and Y start point
G43 H1 Z.5 Activate tool offset 1 and move to Z initial point
G86 G99 X1.0 Y-1.0 Z-1.0 R.25 F10.0 Boring cycle start
X2.0 Y-1.0 Bore second hole
X3.0 Y-1.0 Bore third hole
G80 Canned cycle cancel
G0 G53 Z0 Return Z to home
M30 Program end and rewind
```

**Funzionamento del ciclo G86:**

1. La macchina avanza fino alla profondità del foro alla velocità di avanzamento (**F**).
2. Il mandrino si ferma alla fine del foro.
3. La ritrazione viene eseguita alla velocità rapida, il che può lasciare dei graffi sulla parete del foro dove il utensile è in contatto con la superficie.

**G87 – Foratura da Retro (Back Boring):**  
Il ciclo G87 è un ciclo di foratura da retro, utile per operazioni come la rifilatura dei punti, il contornatura o la smussatura del lato posteriore di un pezzo. All'inizio del ciclo, il mandrino si ferma nella posizione di orientamento e l'utensile si sposta dalla posizione centrale del foro in base alla distanza e direzione definite dai valori **I** e **J**. Se la macchina non ha la capacità di orientare il mandrino, si può fare riferimento al macro M19 descritto nel ciclo G76. Successivamente, l'utensile si posiziona nel piano di ritrazione (**R**) sotto il pezzo. Una volta raggiunto il piano di ritrazione, l'utensile si sposterà al centro del foro e il mandrino verrà avviato per eseguire l'operazione di foratura da retro. Quando il punto **Z** specificato è raggiunto, la macchina orienta il mandrino, compensa con gli offset **I** e **J** e si ritrae fino al punto iniziale. Questo ciclo sempre ritorna al punto iniziale dopo il completamento, non è possibile specificare un punto di ritorno **R** (piano di ritrazione) con **G99**.

**Formato del Codice:**

```gcode
G87 X__ Y__ Z__ R__ I__ J__ P__ L__ F__
```

Dove:

- **X, Y** – Posizione del foro nel piano XY
- **Z** – Punto finale del foro
- **R** – Piano di ritrazione
- **I** – Distanza e direzione di spostamento sull'asse X
- **J** – Distanza e direzione di spostamento sull'asse Y
- **P** – Dwell in secondi (tempo di attesa)
- **L** – Numero di ripetizioni
- **F** – Velocità di avanzamento (feedrate)

**Movimento del Ciclo G87:**

1. Il mandrino si ferma nella posizione di orientamento.
2. L'utensile si sposta dalla posizione centrale del foro, secondo gli offset **I** e **J**.
3. Una volta raggiunto il piano di ritrazione, l'utensile si posiziona al centro del foro e il mandrino viene avviato.
4. Il mandrino forerà fino al punto **Z**.
5. Una volta raggiunto il punto **Z**, la macchina orienta il mandrino e si ritira fino al punto iniziale.
6. Il ciclo G87 sempre ritorna al punto iniziale e non permette di impostare un punto di ritorno con **G99**.

![[Pasted image 20250218215935.png]]

**Esempio:** Crea il programma per eseguire la foratura da retro dei fori passanti nelle stesse posizioni della figura 2. Profondità passante 1 pollice, profondità di foratura da retro 0.150 pollici.

```gcode
G0 G90 G54 G17 G40 G49 G80 Safe start line
T1 M6 Tool change
S2500 M3 Start spindle
G0 X1.0 Y-1.0 Position to X and Y start point
G43 H1 Z.5 Activate tool offset 1 and move to Z initial point
G87 G98 X1.0 Y-1.0 Z-0.85 R-1.05 I-.10 F10.0 Back boring cycle start (Shift -.1 in X axis)
X2.0 Y-1.0 Bore second hole
X3.0 Y-1.0 Bore third hole
G80 Canned cycle cancel
G0 G53 Z0 Return Z to home
M30 Program end and rewind
```

**Funzionamento del ciclo G87:**

1. Il mandrino viene fermato e l'utensile si sposta di **-0.10** sull'asse **X**.
2. L'utensile si muove fino al piano di ritrazione **R** e successivamente al centro del foro.
3. Il mandrino inizia a forare fino al punto **Z**.
4. Al termine della foratura, la macchina orienta il mandrino e si ritira verso il punto iniziale.

**G88 – Foratura con Ritrazione Manuale (Manual Retract):**  
Il ciclo G88 è un ciclo di foratura che include una ritrazione manuale. Al fondo del foro, viene eseguito un tempo di attesa (dwell), quindi il mandrino si ferma e il programma viene messo in pausa. A questo punto, l'operatore può ritirare manualmente l'utensile dal foro. Una volta che l'utensile è stato ritirato, l'operatore preme il pulsante per far ripartire il programma e proseguire l'operazione.

**Formato del Codice:**

```gcode
G88 X__ Y__ Z__ R__ P__ L__ F__
```

Dove:

- **X, Y** – Posizione del foro nel piano XY
- **Z** – Punto finale del foro
- **R** – Piano di ritrazione
- **P** – Dwell in secondi (tempo di attesa)
- **L** – Numero di ripetizioni
- **F** – Velocità di avanzamento (feedrate)

![[Pasted image 20250218220100.png]]

**Movimento del Ciclo G88:**

1. Il mandrino esegue la foratura fino al punto finale **Z**.
2. Una volta raggiunto il punto **Z**, il mandrino si ferma e viene eseguito il tempo di attesa definito da **P**.
3. Il mandrino si ferma e il programma va in pausa.
4. L'operatore manualmente ritira l'utensile dal foro.
5. Quando l'utensile è stato ritirato, l'operatore preme il pulsante di avvio per riprendere l'esecuzione del programma.

**Esempio:** Crea il programma per eseguire la foratura dei fori mostrati nella figura 2.

```gcode
G0 G90 G54 G17 G40 G49 G80 Safe start line
T1 M6 Tool change
S2500 M3 Start spindle
G0 X1.0 Y-1.0 Position to X and Y start point
G43 H1 Z.5 Activate tool offset 1 and move to Z initial point
G88 G99 X1.0 Y-1.0 Z-1.0 R.25 F10.0 Boring cycle start, pause for manual retract
X2.0 Y-1.0 Bore second hole, pause for manual retract
X3.0 Y-1.0 Bore third hole, pause for manual retract
G80 Canned cycle cancel
G0 G53 Z0 Return Z to home
M30 Program end and rewind
```

**Funzionamento del ciclo G88:**

1. Il mandrino inizia a forare fino al punto **Z** (fondo del foro).
2. Una volta raggiunto il fondo, viene eseguito il **dwell** definito da **P**.
3. Il mandrino si ferma e il programma va in pausa.
4. L'operatore ritira manualmente l'utensile dal foro.
5. Dopo il ritiro manuale, l'operatore preme "Start" per far ripartire il programma e completare le operazioni successive.

**G89 – Foratura con Dwell e Ritrazione a Feedrate:**  
Il ciclo G89 è simile al G85, ma con l'aggiunta di un dwell (tempo di attesa) al fondo del foro. Dopo aver raggiunto la profondità finale del foro, il ciclo esegue una pausa (dwell) prima di eseguire la ritrazione, che avviene con il feedrate programmato.

**Formato del Codice:**

```gcode
G89 X__ Y__ Z__ R__ P__ L__ F__
```

Dove:

- **X, Y** – Posizione del foro nel piano XY
- **Z** – Punto finale del foro
- **R** – Piano di ritrazione
- **P** – Tempo di attesa (dwell) in secondi
- **L** – Numero di ripetizioni
- **F** – Velocità di avanzamento (feedrate)

![[Pasted image 20250218220245.png]]

**Movimento del Ciclo G89:**

1. Il mandrino esegue la foratura fino al punto finale **Z**.
2. Una volta raggiunto il fondo del foro, il ciclo si ferma per il tempo di attesa **P**.
3. Dopo il dwell, la ritrazione avviene con il feedrate specificato.

**Esempio:** Crea il programma per eseguire la foratura dei fori mostrati nella figura 2.

```gcode
G0 G90 G54 G17 G40 G49 G80 Safe start line
T1 M6 Tool change
S2500 M3 Start spindle
G0 X1.0 Y-1.0 Position to X and Y start point
G43 H1 Z.5 Activate tool offset 1 and move to Z initial point
G89 G99 X1.0 Y-1.0 Z-1.0 R.25 P.250 F10.0 Boring cycle start
X2.0 Y-1.0 Bore second hole
X3.0 Y-1.0 Bore third hole
G80 Canned cycle cancel
G0 G53 Z0 Return Z to home
M30 Program end and rewind
```

**Funzionamento del ciclo G89:**

1. Il mandrino inizia a forare fino al punto finale **Z** (fondo del foro).
2. Una volta raggiunto il fondo, viene eseguito un **dwell** di **P** secondi.
3. Dopo il dwell, il mandrino si ritira con il feedrate specificato.

### Capitolo 4

**Capitolo 4: Compensazione dell'Utensile**  
La compensazione dell'utensile fornisce all'utente la possibilità di regolare il percorso dell'utensile per variazioni nel diametro dell'utensile stesso. Può essere utilizzata in due modi. In primo luogo, quando si programma manualmente, senza l'ausilio del software CAM (Computer Aided Manufacturing), è molto più semplice programmare le dimensioni effettive della parte, la programmazione delle linee della parte. Questo consente al programmatore di non dover calcolare il percorso corretto al centro dell'utensile quando è il bordo a eseguire il taglio. Quando viene fornito un corretto offset del diametro, la compensazione dell'utensile farà le necessarie regolazioni del percorso dell'utensile per tagliare correttamente la parte. In sostanza, la macchina esegue i calcoli al posto del programmatore. In secondo luogo, con l'uso più diffuso dei sistemi CAM, il percorso dell'utensile è già regolato per il diametro dell'utensile e la parte dovrebbe, in teoria, essere tagliata perfettamente alle dimensioni desiderate. In pratica, tuttavia, ci sono molti fattori che determinano la dimensione finale di una parte lavorata, come la deflessione dell'utensile e della macchina, la precisione del posizionamento della macchina, le variazioni nel diametro dell'utensile, ecc. La compensazione dell'utensile consente di perfezionare il percorso dell'utensile e regolare le dimensioni della parte, senza dover modificare il programma stesso.

Esistono due codici G utilizzati per abilitare la compensazione dell'utensile. **G41** sposta l'utensile a sinistra del percorso dell'utensile, mentre **G42** sposta l'utensile a destra del percorso. Questo è valido solo per valori di offset positivo. Se viene specificato un offset negativo, la direzione dell'offset sarà invertita, come mostrato nella figura 41-1. Esistono due modi per chiamare il valore dell'offset con **G41** e **G42**.

**Formato 1:**  
`G00/G01 G41/G42 D__ X__ Y__ F__`

**Formato 2:**  
`G00/G01 G41/G42 P__ X__ Y__ F__`

Utilizzare **D** per chiamare un offset del diametro da un numero specifico di offset utensile. Ad esempio, **D2** utilizza il valore di offset del diametro dell'utensile numero 2. Un'alternativa è usare **P**. Il valore specificato con **P** sarà il valore effettivo dell'offset. Ad esempio, **P.05** sposterà il percorso dell'utensile di 0,05 a sinistra o a destra.

La compensazione dell'utensile funziona solo sugli assi in piano, quindi per **G17** (piano XY), gli assi **X** e **Y** sono influenzati dalla compensazione, e lo stesso vale per **G18** (piano ZX) e **G19** (piano YZ).

![[Pasted image 20250218220514.png]]

**Figura 41-1:** Direzione dell'offset della compensazione dell'utensile.

- Percorso utensile programmato
- Percorso utensile con compensazione
- **G41** + Offset
- **G42** - Offset
- **G42** + Offset
- **G41** - Offset

**Fresa a Fronte Avanti (Climb Milling) vs Fresa Convenzionale (Conventional Milling)**

Ci sono due tipi di fresatura, che stile si utilizza determina come l'utensile deve essere compensato. I due tipi sono **fresatura a fronte avanti (climb milling)** e **fresatura convenzionale (conventional milling)**, come mostrato nella figura 41-1. La fresatura convenzionale è lo standard nelle macchine manuali, ma con la fresatura CNC è possibile e raccomandato eseguire la fresatura a fronte avanti quando possibile. Questo manuale assume che l'utensile esegua sempre la fresatura a fronte avanti. Con tale assunzione, se **G41** è utilizzato per le caratteristiche esterne, come il profilo di una parte, un offset positivo farà la parte **più grande** e un offset negativo farà la parte **più piccola**. Per le caratteristiche interne, come un foro, **G42** farà il foro **più grande** con un offset positivo e **più piccolo** con un offset negativo, come mostrato nella figura 41-2. Questo metodo tende a rendere i valori di offset più intuitivi per l'operatore. Se si utilizza la fresatura convenzionale, questa descrizione verrà invertita.

![[Pasted image 20250218220707.png]]

**Fresatura a fronte avanti (Climb Milling)**

- **Parte esterna**:  
    Con **G41** e un offset positivo, le dimensioni della parte diventano **più grandi**.
    
- **Parte interna**:  
    Con **G42** e un offset positivo, le dimensioni del foro diventano **più grandi**.
    

La compensazione dell'utensile dovrebbe essere abilitata su un movimento lineare di ingresso (lead-in). Verrà generato un errore se la compensazione dell'utensile viene abilitata in un blocco con un arco. Se c'è un valore diverso da zero nell'offset, questo movimento di ingresso potrebbe non essere parallelo al percorso programmato, come illustrato nelle figure 41-1, 41-6 e 41-7. Il punto finale del blocco di inizio è il punto a 90° rispetto al movimento nel blocco successivo e alla distanza dell'offset. Vedi la figura 41-3 per gli esempi. Questo movimento lineare deve essere più lungo dell'ammontare dell'offset, altrimenti si verificherà un errore. Inoltre, se ci sono segmenti del percorso dell'utensile più corti dell'offset, è probabile che si verifichi un intaglio (gouge), come mostrato nella figura 41-4. La visualizzazione del percorso dell'utensile in Mach mostrerà il percorso effettivo con la compensazione, quindi è importante controllare che non ci siano intagli o anomalie prima di eseguire il ciclo di lavorazione della parte.

**Percorso utensile programmato e percorso con compensazione utensile**

![[Pasted image 20250218220841.png]]

**Tool Path 1: Senza compensazione utensile**

```plaintext
G00 G90 G54 G17 G40 G49 G80
G0 X0 Y0 Z1.
S1000 M3
G1 G41 P0 Y.5 F25.
X1.5
Y.6
X2.0
G40 Y1.25
M30
```

**Tool Path 2: Compensazione raggio .05**

```plaintext
G00 G90 G54 G17 G40 G49 G80
G0 X0 Y0 Z1.
S1000 M3
G1 G41 P0.05 Y.5 F25.
X1.5
Y.6
X2.0
G40 Y1.25
M30
```

**Tool Path 3: Compensazione raggio .15**

```plaintext
G00 G90 G54 G17 G40 G49 G80
G0 X0 Y0 Z1.
S1000 M3
G1 G41 P0.15 Y.5 F25.
X1.5
Y.6
X2.0
G40 Y1.25
M30
```

**Figura 41-4** mostra tre percorsi utensile generati dallo stesso programma con diversi valori di compensazione utensile. Il rischio di intaglio (gouge) si verifica quando un valore di offset maggiore di 0,10 viene inserito. Quando questo accade, il percorso compensato si sovrappone e si inverte, creando un intaglio. Un altro esempio di questo fenomeno si verifica nelle piccole scanalature, come mostrato in **Figura 41-5**.

![[Pasted image 20250218220957.png]]

**Figura 41-5: Compensazione utensile in una scanalatura stretta.**

**Percorso utensile programmato**  
**Percorso utensile con compensazione**  
_La compensazione supera i bordi della parte in questi angoli._

La compensazione dell'utensile viene annullata specificando **G40** nel programma, oppure quando il controllo viene resettato. Quando **G40** viene specificato, dovrebbe essere usato in un movimento di uscita (lead-out) seguendo le stesse regole di quando la compensazione è abilitata. Il percorso sarà determinato come mostrato in **Figura 41-3**. Si verificheranno errori se la distanza di uscita è inferiore all'importo dell'offset o se **G40** è specificato in un blocco che contiene un movimento ad arco.

![[Pasted image 20250218221025.png]]
**Capitolo 5: Elenco dei Codici M**

|Codice|Descrizione|Pagina|
|---|---|---|
|M00|Fermata Obbligatoria del Programma|56|
|M01|Fermata Opzionale del Programma|56|
|M02|Fine Programma|56|
|M03|Mandrino in Avanti/Orario|56|
|M04|Mandrino in Retro/Antiorario|56|
|M05|Fermata Mandrino|56|
|M06|Cambio Utensile|57|
|M07|Raffreddamento a Nebbia Attivo|57|
|M08|Raffreddamento a Flusso Attivo|57|
|M09|Fermata di Tutti i Raffreddamenti|57|
|M19|Orientamento Mandrino|57|
|M30|Fine Programma e Riavvolgimento|57|
|M48|Abilita Override di Velocità di Avanzamento/Spindle|57|
|M49|Disabilita Override di Velocità di Avanzamento/Spindle|57|
|M98|Chiamata Subprogramma|57|
|M99|Ritorno dal Subprogramma / Riavvolgimento|59|
|M???|Codici M Macro Personalizzati|60|

### Descrizioni dei Codici M

- **M00 – Fermata Obbligatoria del Programma:** Per mettere in pausa un programma in qualsiasi punto, specificare un M00. Tutti i movimenti vengono interrotti e il mandrino fermato. Per riprendere l'operazione, premere il pulsante di avvio del ciclo.
    
- **M01 – Fermata Opzionale del Programma:** Il programma si ferma come M00, ma solo quando l'interruttore di fermata opzionale è attivato. Permette all'operatore di fermare e controllare i punti del programma quando necessario, ma consente anche di farlo eseguire senza fermate.
    
- **M02 – Fine Programma:** Termina il programma al blocco M02. Tutte le operazioni del programma vengono terminate e le impostazioni predefinite (G54, G17, G90, ecc.) vengono ripristinate. Il programma non verrà riavvolto e se il pulsante di avvio del ciclo viene premuto, l'esecuzione del programma inizierà dal blocco successivo al M02.
    
- **M03 – Mandrino in Avanti/Orario:** Accende il mandrino nella direzione avanti (orario) alla velocità designata. M03 è solitamente combinato con una parola S per definire la velocità. Se una parola S non è specificata, verrà utilizzata l'ultima velocità del mandrino.
    
- **M04 – Mandrino in Retro/Antiorario:** Accende il mandrino nella direzione inversa (antiorario) alla velocità designata. M04 è solitamente combinato con una parola S per definire la velocità. Se una parola S non è specificata, verrà utilizzata l'ultima velocità del mandrino.
    
- **M05 – Fermata Mandrino:** Ferma la rotazione del mandrino.
    
- **M06 – Cambio Utensile:** Indica alla macchina di cambiare a un utensile specificato dal numero T. La parola T deve comparire nello stesso blocco dell'M06 o sopra di essa nel programma.
    
- **M07 – Raffreddamento a Nebbia Attivo:** Accende l'uscita del raffreddamento a nebbia.
    
- **M08 – Raffreddamento a Flusso Attivo:** Accende l'uscita del raffreddamento a flusso.
    
- **M09 – Fermata di Tutti i Raffreddamenti:** Spegne tutte le uscite di raffreddamento.
    
- **M19 – Orientamento Mandrino:** Sebbene questo codice non sia incorporato in Mach e sia completamente definito dall'utente, è necessario per orientare il mandrino in alcuni cicli di lavorazione, come G76 e G87. I cambi utensile generalmente richiedono un orientamento del mandrino, e sebbene questo orientamento possa essere qualsiasi codice M definito dall'utente o anche integrato nell'M6, M19 è raccomandato poiché è uno standard dell'industria.
    
- **M30 – Fine Programma e Riavvolgimento:** Termina il programma corrente e riavvolge all'inizio. Premendo il pulsante di avvio del ciclo, l'esecuzione del programma ripartirà dal primo blocco. Tutte le impostazioni predefinite (G54, G17, G90, ecc.) verranno ripristinate.
    
- **M48 – Abilita Override di Velocità di Avanzamento/Spindle:** Abilita gli override di velocità di avanzamento e mandrino dopo che è stato emesso un M49.
    
- **M49 – Disabilita Override di Velocità di Avanzamento/Spindle:** Disabilita gli override di velocità di avanzamento e mandrino.
- **M49 – Disabilita gli Override di Velocità di Avanzamento/Spindle:** Disabilita gli override della velocità di avanzamento e del mandrino. Questo può essere vantaggioso in ambienti di produzione e anche in programmi o macro sensibili alla velocità di avanzamento e del mandrino, prevenendo così override accidentali.

**M98 – Chiamata Subprogramma:** I subprogrammi sono programmi esterni richiamati dal programma corrente in esecuzione. Quando viene chiamato, l'esecuzione del programma continuerà nel subprogramma. Questo consente all'utente di ridurre la lunghezza e la complessità del programma, permettendo di ripetere facilmente sezioni di codice, eseguire la stessa sezione di codice in più posizioni o in più offset di supporto. Le possibilità sono limitate solo dal programmatore. Per chiamare un subprogramma, si usa il comando M98 con il numero del programma come segue.

**Formato:**  
M98 P____ Q__ L__

- **P** specifica il numero del programma da chiamare. Questo è un numero intero di quattro cifre. Quando Mach legge l'M98, scansiona il file corrente alla ricerca di un blocco contenente il numero del programma nel seguente formato: **Formato:** O1234  
    Nota che la lettera “O” è usata per specificare il numero del programma 1234, **non** il numero "0". L'esecuzione del programma continuerà con il blocco successivo al numero O.

Per questo metodo, il subprogramma dovrebbe trovarsi sotto la fine del programma corrente:

**(PROGRAMMA PRINCIPALE)** Intestazione del programma principale  
G0 G90 G54 G17 G40 G49 G80 Linea di avvio sicuro  
G0 X4.0 Y0.0 Z1.0 Spostamento rapido  
T1 M6 Cambio utensile in utensile 1  
G0 X10.0 Y-5.0 Z1.0 Spostamento rapido  
M98 P1000 Chiamata subprogramma numero 1000  
M30 Fine programma e riavvolgimento

**O1000 (INIZIO SUBPROGRAMMA)** Numero del subprogramma  
G12 I-0.25 Taglia cerchio  
M99 Torna al programma principale

Ci sono limitazioni per questo metodo; principalmente, il subprogramma deve essere copiato in ogni programma che deve richiamarlo. Mach consente anche di chiamare un subprogramma da un file esterno. In questo modo, più programmi possono chiamare lo stesso subprogramma senza doverlo includere nel file principale. Se è necessario apportare una modifica al subprogramma, deve essere fatta solo in un file, non in ogni file da cui viene chiamato il subprogramma.

Se il controllo non trova il numero del programma nel file corrente, cercherà quindi nel **Mach4\Subroutines** directory. In questo caso, cercherà i nomi dei file. I file in questa directory dovrebbero essere denominati con il numero del programma come segue: **Formato:** O____  
Nota che la lettera "O" è seguita da quattro numeri, e non deve esserci un'estensione di file, quindi **O1234** e **non** O1234.txt. Quando il programma viene caricato, questo file verrà trovato e caricato nella memoria, e la visualizzazione del percorso utensile rifletterà ciò che è nel subprogramma. Quando il file viene eseguito, il blocco M98 verrà letto e l'esecuzione del programma continuerà con il primo blocco del file del subprogramma.

Gli argomenti **Q** e **L** sono opzionali.

- **Q** specifica il numero di sequenza nel subprogramma da cui partire. Se Q è omesso, l'esecuzione inizierà dall'inizio del subprogramma (vedi figura 198-1).
- **L** è il numero di ripetizioni. Ad esempio, se L=2, il subprogramma verrà eseguito due volte prima che l'esecuzione del programma principale riprenda. Se L è omesso, il programma verrà eseguito una sola volta.

![[Pasted image 20250218221251.png]]
**M99 – Ritorno dal Subprogramma / Riavvolgimento:** Per tornare al programma principale da un subprogramma, si utilizza l'M99.

**Formato:**  
M99 P__

L'M99 specificato in un subprogramma restituirà il controllo al programma principale al blocco immediatamente successivo alla chiamata del subprogramma M98. L'aggiunta di una **P** nel blocco M99 permetterà di tornare a un numero di sequenza desiderato nel programma principale.  
Vedi figura 199-1.

![[Pasted image 20250218221356.png]]
**M99 se specificato in un programma principale (non in un subprogramma):**  
Se M99 è specificato in un programma principale (e non in un subprogramma), viene eseguito un riavvolgimento del programma. L'esecuzione riprenderà dal primo blocco del programma.

---

**Codici M personalizzati:**  
Ogni macchina è un po' diversa e ha diverse funzioni e opzioni. I codici M personalizzati permettono all'utente di creare chiamate di programmazione semplici per processi complessi, attivando o disattivando uscite, leggendo ingressi, eseguendo calcoli matematici o qualunque altra cosa l'utente e la macchina possano richiedere. Questi codici M sono programmati in Lua e collocati nella cartella **macros** sotto ciascun profilo.

Ogni profilo può avere il proprio set unico di codici M. Il nome del file deve essere il macro da chiamare.  
Ad esempio, per creare un macro di cambio utensile, **M6**, aggiungi uno script Lua con il nome del file **M6.mcs** nella cartella **macros** nel profilo desiderato. Quando un **M6** è chiamato in un programma o in MDI, il macro verrà eseguito.
