#javascript #italiano #programming 

## Variabili

Una variabile è un contenitore che contiene un valore, si comporta come se fosse il valore che contiene. 

Ci sono due step per la creazione di una variabile:

1. **Dichiarazione:**  da il nome a una variabile es: `let x` , si possono dichiarare le variabili con diverse modalità che influenzano il loro comportamento:
	1. `let x` dichiara una variabile il cui valore può essere riassegnato
	2. `const x` dichiara una variabile il cui valore non può essere riassegnato
	3. `var x` è una modalità in disuso ma ancora accettata in JavaScript   
2. **Assegnazione:** assegna un valore a una variabile es:  `x = 100`

```js
let x; //dichiarazione
x = 100; //assegnazione

let età = 25; //assegnazione e dichiarazione
```

## Console di Sviluppo

`console.log` è una funzione di JavaScript che si utilizza per scrivere, stampare, visualizzare o mostrare informazioni nella [Console di Sviluppo] 

```js
console.log(età) //mostra il valore della variabile età

console.log("Stringa di Testo"); //scriverà la stringa di testo nella console

console.log("Età:" + età); //scriverà la stringa e scriverà il valore della variabile concatenato, cioè convertirà il valore numerico assegnato a variabile età in una stringa di testo e la scriverà nella console
```

Si può inserire ${variabile} in una stringa da visualizzare nella console se si è utilizzato un Template Literal usando il carattere  backtick \` e non le virgolette "

```js
console.log(`Hai ${età} anni,sei un vecchio di merda`); 
```

E' sempre preferibile scrivere le stringhe come Template Literal (o Template String) usando il carattere backtick \`,  si possono inserire espressioni più complesse all'interno di ${  } come espressioni matematiche o chiamate a funzioni

## Tipi di Variabili

Esistono 5 tipi di variabili principali:
 
1. **Number**: sia i numeri interi che i numeri decimali sono appartengono al tipo Number
2. **String**: una stringa è una serie di caratteri delimitate da virgolette doppie es: `"stringa"` oppure virgolette singole `'stringa'`
3. **Boolean:** o Variabile Booleana è una variabile che può avere un valore di `true` o `false`
4. **Undefined:** rappresenta una variabile a cui non è stata assegnato un valore
5. **Null:** rappresenta l'assenza intenzionale di qualsiasi valore, è un valore nullo assegnato a differenza di `undefined`

Si può visualizzare il Tipo di una variabile nella console usando `typeof`

```js
let nome = "Gianni";
let età = 26;
let sposato = false;
let x;
let y = null;

console.log(typeof nome); //mostra che nome è una Stringa
console.log(typeof età); //mostra che età è un Numero
console.log(typeof sposato); //mostra che sposato è un Boolean
console.log(typeof x); //mostra che la variabile x non è assegnata (undefined)
console.log(typeof y); //mostra che y ha valore nullo (null) 
```

