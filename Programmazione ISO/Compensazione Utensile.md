### **Tipi di compensazione**

1. **Compensazione utensile a destra (G41)**:
    
    - L'utensile viene spostato **a sinistra** del percorso programmato (guardando nella direzione del movimento).
    - Usata per lavorazioni in cui l'utensile deve rimanere esterno al percorso, come nel taglio esterno di una sagoma.
2. **Compensazione utensile a sinistra (G42)**:
    
    - L'utensile viene spostato **a destra** del percorso programmato (guardando nella direzione del movimento).
    - Usata per lavorazioni in cui l'utensile deve rimanere interno al percorso, come nel taglio interno di una sagoma.

---

### **Esempio pratico**

Supponiamo di voler eseguire una lavorazione lungo un contorno rettangolare. Se il percorso teorico è definito al centro dell'utensile, bisogna specificare una compensazione per tener conto del raggio dell'utensile:

- Con un utensile di diametro 10 mm (raggio 5 mm):
    - **G41** sposta il percorso 5 mm verso l'esterno per lavorazioni lungo l'esterno del contorno.
    - **G42** sposta il percorso 5 mm verso l'interno per lavorazioni lungo l'interno del contorno.

---

### **Comandi principali**

1. **Attivare la compensazione**:
    
    - `G41` per la compensazione a destra.
    - `G42` per la compensazione a sinistra.
    - Seguito da un movimento che definisce il percorso iniziale di compensazione.
    
    Esempio:
    
    gcode
    
    CopiaModifica
    
    `G41 D1  ; Attiva la compensazione utensile a sinistra usando il raggio dell'utensile definito nel registro D1 G01 X10 Y20  ; Movimento lineare lungo il percorso compensato`
    
2. **Disattivare la compensazione**:
    
    - `G40` annulla qualsiasi compensazione utensile.
    - Deve essere specificato prima di terminare il programma o eseguire movimenti fuori dal contorno.
    
    Esempio:
    
    gcode
    
    CopiaModifica
    
    `G40 ; Disattiva la compensazione utensile`
    

---

### **Considerazioni importanti**

1. **Raggio utensile**: Deve essere definito nel registro utensile (es. **D** o **H**) per calcolare correttamente lo spostamento.
2. **Percorsi di ingresso e uscita**: Quando si usa la compensazione utensile, è importante fornire un ingresso e un'uscita dal contorno sufficientemente lunghi per evitare collisioni o tagli errati.
3. **Direzione di taglio**: La compensazione deve corrispondere alla direzione corretta del taglio (orario o antiorario) rispetto al pezzo.

---

### **Quando usarla?**

- Quando si lavora con frese di dimensioni variabili o diverse da quelle teoriche del programma.
- Per lavorazioni precise che richiedono tolleranze strette.
- Per evitare errori causati da variazioni nei diametri degli utensili.