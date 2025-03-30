
La **libreria standard del C** è un insieme di **header** e **funzioni** definite dallo standard ISO C. Di seguito, ti fornisco una **lista completa** degli **header della libreria standard del C**, con una breve descrizione di ognuno.

---

## 📜 **Lista completa degli header della libreria standard del C**

### **1. Intestazioni di Input/Output**

|**Header**|**Descrizione**|
|---|---|
|`<stdio.h>`|Funzioni per input/output standard (`printf()`, `scanf()`, `fopen()`, `fgets()`, ecc.).|

### **2. Intestazioni di Manipolazione della Memoria e Stringhe**

|**Header**|**Descrizione**|
|---|---|
|`<string.h>`|Funzioni per la manipolazione di stringhe (`strcpy()`, `strlen()`, `strcmp()`, ecc.).|
|`<stdlib.h>`|Funzioni per gestione della memoria (`malloc()`, `free()`, `exit()`, ecc.).|
|`<stddef.h>`|Definizioni di tipi standard (`NULL`, `size_t`, `ptrdiff_t`).|

### **3. Intestazioni per la Manipolazione Numerica e Matematica**

|**Header**|**Descrizione**|
|---|---|
|`<math.h>`|Funzioni matematiche (`sqrt()`, `pow()`, `sin()`, `cos()`, ecc.).|
|`<stdlib.h>`|Funzioni per conversione numerica (`atoi()`, `strtod()`, ecc.).|
|`<float.h>`|Costanti per i numeri in virgola mobile.|
|`<limits.h>`|Limiti numerici per i tipi di dati (`INT_MAX`, `CHAR_MIN`, ecc.).|

### **4. Intestazioni per la Gestione della Memoria Dinamica e del Controllo del Programma**

|**Header**|**Descrizione**|
|---|---|
|`<assert.h>`|Funzione `assert()` per il debugging.|
|`<errno.h>`|Costanti per la gestione degli errori (`errno`).|
|`<setjmp.h>`|Funzioni per il salto non locale (`setjmp()`, `longjmp()`).|
|`<signal.h>`|Gestione dei segnali (`SIGTERM`, `signal()`, ecc.).|
|`<stdnoreturn.h>`|Attributo `_Noreturn` per funzioni che non restituiscono il controllo.|

### **5. Intestazioni per la Gestione della Data e del Tempo**

|**Header**|**Descrizione**|
|---|---|
|`<time.h>`|Funzioni per data e ora (`time()`, `clock()`, `difftime()`, ecc.).|

### **6. Intestazioni per la Gestione dei Caratteri**

|**Header**|**Descrizione**|
|---|---|
|`<ctype.h>`|Funzioni per la classificazione e conversione di caratteri (`isdigit()`, `toupper()`, ecc.).|
|`<wctype.h>`|Versione per caratteri wide (`wchar_t`).|
|`<wchar.h>`|Funzioni per la manipolazione di stringhe wide (`wprintf()`, `wcscpy()`, ecc.).|

### **7. Intestazioni per la Manipolazione di File e Directory**

|**Header**|**Descrizione**|
|---|---|
|`<fcntl.h>`|Costanti per la gestione dei file (solo POSIX).|
|`<unistd.h>`|Funzioni di accesso ai file system (solo POSIX).|

### **8. Intestazioni per la Gestione di Processi e Thread (C11)**

|**Header**|**Descrizione**|
|---|---|
|`<threads.h>`|API per la gestione dei thread (`thrd_create()`, `mtx_lock()`, ecc.).|
|`<stdatomic.h>`|Funzioni per operazioni atomiche.|

---

## **📌 Note Importanti**

- **C89/C90:** Prima versione dello standard C, include la maggior parte di questi header.
- **C99:** Ha introdotto `<stdbool.h>` (per il tipo `bool`) e migliorato `<math.h>`.
- **C11:** Ha aggiunto `<threads.h>`, `<stdatomic.h>` e `<stdnoreturn.h>`.
- **POSIX:** Alcuni header (`<fcntl.h>`, `<unistd.h>`) non fanno parte dello standard ISO C ma sono comuni nei sistemi Unix/Linux.

Se hai bisogno di dettagli su una libreria specifica, chiedi pure! 😊