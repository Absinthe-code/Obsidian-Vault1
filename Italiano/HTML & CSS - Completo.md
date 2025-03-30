#html #css

HTML (Hyper Text Markup Language) è il linguaggio che permette di strutturare e organizzare i contenuti di una pagina web, definendo la loro forma e il loro significato.

HTML funziona grazie a dei Tag (o Markup) che vengono usati da un web browser per fornire informazioni su che tipo di contenuto deve elaborare e visualizzare.

Solitamente i Tag sono a coppie con del contenuto tra il Tag iniziale e quello finale

```html
<p> Contenuto </p> <!-- esempio di un tag di tipo paragrafo -->
```

In un file HTML è possibile aggiungere dei commenti tramite la notazione `<!-- commento -->` , tutto ciò che è contenuto all'interno di un commento non viene letto o interpretato dal browser

CSS (Cascading Style Sheets) è un linguaggio di stile utilizzato per descrivere l'aspetto e la formattazione di un documento scritto in HTML o XML. In parole semplici, l'HTML definisce la struttura di una pagina web, mentre il CSS ne controlla la presentazione visiva.

## Tag di HTML

- `<!DOCTYPE html>` : definisce la versione di HTML che stiamo usando, in questo caso la versione 5 di html
- `<html> </html>` : rappresenta l'elemento root o radice di un documento HTML
- `<head> </head>` : è l'elemento head o testa del documento, contiene informazioni riguardanti il documento stesso, ad esempio
    - `<title> </title>` : titolo della pagina
    - `<meta>` : fornisce metadati sul documento (charset, author, viewport, ecc.)
    - `<link>` : collega il documento a risorse esterne, come file CSS
    - `<base>` : definisce l'URL di base per tutti i link relativi nella pagina
- `<body> </body>` : corpo del documento, contiene tutto ciò che il browser visualizzerà a schermo quando si visita la pagina web
- `<noscript> </noscript>` : mostra contenuto alternativo se il browser non supporta JavaScript

---
### Struttura e Layout (Elementi di Blocco)

#### Contenitori e Struttura Primaria:

- `<header> </header>` : utilizzato per definire l'intestazione di una pagina
- `<nav> </nav>` : definisce una sezione di navigazione, comune in siti con menu o link interni.
- `<main> </main>` : indica il contenuto principale della pagina e dovrebbe essere usato una sola volta per pagina; sebbene importante, il suo uso è limitato a un'unica occorrenza.
- `<section> </section>` : usato per raggruppare contenuti correlati in sezioni tematiche.
- `<article> </article>` : indica un contenuto autonomo, come un post o una notizia; molto usato in blog e siti di informazione.
- `<aside> </aside>` : usato per contenuti complementari (es. sidebar, note, annunci); meno frequente rispetto agli elementi sopra.
- `<footer> </footer>` : utilizzato per definire il piè di pagina.
- `<h1> </h1>` : definisce il titolo principale della pagina
- `<h2> </h2>` : definisce un sottotitolo
- `<h3> </h3>` : definisce un titolo di terzo livello
- `<h4> </h4>` : definisce un titolo di quarto livello
- `<h5> </h5>` : definisce un titolo di quinto livello
- `<h6> </h6>` : definisce un titolo di sesto livello
- `<p> </p>` : rappresenta un paragrafo di testo
- `<div> </div>` : elemento di blocco generico usato per contenere e raggruppare altri elementi. È il più utilizzato per strutturare il layout.
- `<dl> </dl>` : definisce una lista di definizioni
    - `<dt> </dt>` : definisce il termine di una definizione
    - `<dd> </dd>` : fornisce la descrizione del termine
- `<canvas> </canvas>` : elemento per la grafica dinamica tramite scripting

#### Raggruppamento, Dati e Componenti Avanzati:

- `<form> </form>` : fondamentale per l'invio di dati utente, molto usato in siti interattivi.
    - `<fieldset> </fieldset>` : raggruppa campi di un modulo.
    - `<legend> </legend>` : fornisce un titolo per il gruppo di campi.
- `<table> </table>` : utilizzato per la visualizzazione di dati in formato tabellare.
    - `<caption> </caption>` : fornisce un titolo alla tabella.
    - `<colgroup> </colgroup>` : raggruppa una o più colonne per applicare stili
        - `<col>` : specifica la formattazione di una colonna all'interno di `<colgroup>`
    - `<thead> </thead>` : contiene l'intestazione della tabella.
    - `<tbody> </tbody>` : contiene il corpo della tabella.
    - `<tfoot> </tfoot>` : contiene il piè di pagina della tabella.
    - `<tr> </tr>`, `<th> </th>`, `<td> </td>` : elementi per righe e celle.
- `<ul> </ul>` : definisce una lista non ordinata; estremamente comune per menu, elenchi e navigazione.
    - `<li> </li>` : elementi di lista, utilizzati all'interno di `<ul>` (e `<ol>`), considerati come parte integrante dell'elenco.
- `<ol> </ol>` : definisce una lista ordinata per numero.
    - `<li> </li>` : elemento di lista (come sopra).
- `<blockquote> </blockquote>` : utilizzato per citazioni di blocco; comune in articoli e post.
- `<figure> </figure>` : raggruppa immagini con la loro didascalia, centrato per default.
    - `<figcaption> </figcaption>` : descrizione dell'immagine all'interno di `<figure>`
- `<address> </address>` : utilizzato per indicare informazioni di contatto; usato tipicamente in pagine "contatti".
- `<hr>` : crea una linea orizzontale per separare i contenuti; usato saltuariamente.
- `<pre> </pre>` : mantiene la formattazione e gli spazi del testo così come scritti nel codice sorgente; usato in contesti di visualizzazione di codice o testi preformattati.
- `<details> </details>` : crea un widget espandibile/collassabile; elemento HTML5 relativamente nuovo e quindi meno diffuso.
    - `<summary> </summary>` : fornisce il titolo cliccabile per il contenuto di `<details>`.
- `<dialog> </dialog>` : rappresenta una finestra di dialogo o un modale interattivo; anch'esso relativamente nuovo e con un uso limitato.
- `<object> </object>` : usato per incorporare contenuti multimediali o documenti esterni
    - `<param> </param>` : definisce i parametri per `<object>`
- `<template> </template>` : contiene markup che non viene renderizzato immediatamente ma che può essere attivato tramite script

---
### Testo e Formattazione (Elementi in Linea)

#### Formattazione di Base:

- `<span>` : contenitore generico in linea usato per applicare stili o script a una parte di testo; il più comune per interventi stilistici su piccole porzioni di contenuto.
- `<strong> </strong>` : indica testo di forte importanza, visualizzato di solito in grassetto.
- `<em> </em>` : indica enfasi, generalmente visualizzato in corsivo.
- `<b> </b>` : indica testo stilisticamente evidenziato; simile a `<strong>` ma senza particolare semantica.
- `<i> </i>` : indica testo con uno stile diverso (corsivo), usato per scopi tecnici o per enfatizzare termini in lingue straniere.
- `<small> </small>` : indica testo di minore importanza, di solito visualizzato con dimensioni ridotte.
- `<abbr> </abbr>` : usato per abbreviazioni e acronimi, con un attributo `title` opzionale per la spiegazione.
- `<code> </code>` : indica porzioni di codice, spesso con font monospace.
- `<time> </time>` : utilizzato per specificare date o orari;
- `<mark> </mark>` : evidenzia il testo (di solito con sfondo giallo)
- `<u> </u>` : indica testo sottolineato; usato moderatamente.
- `<cite> </cite>` : usato per citare il titolo di un'opera; meno diffuso.
- `<dfn> </dfn>` : indica la definizione di un termine; utilizzato in contesti didattici o documentativi.
- `<samp> </samp>` : indica output di un programma; usato principalmente in documentazioni tecniche.
- `<kbd> </kbd>` : indica input da tastiera; anch'esso di nicchia, in testi tecnici.
- `<var> </var>` : indica una variabile in una formula o codice; meno comune.
- `<data> </data>` : associa una stringa visibile a un valore macchina leggibile; usato in contesti specifici.
- `<s> </s>` : indica testo non più valido o errato, di solito barrato.
- `<ruby> </ruby>` : contiene annotazioni per testi in lingue come il giapponese; di nicchia.
    - `<rt> </rt>` : fornisce la pronuncia o spiegazione del testo in `<ruby>`.
    - `<rp> </rp>` : fornisce un fallback per i browser che non supportano `<ruby>`.
- `<sub> </sub>` : abbassa il testo rispetto alla linea di base (pedice)
- `<sup> </sup>` : alza il testo rispetto alla linea di base (apice)
- `<q> </q>` : per citazioni brevi inline
- `<ins> </ins>` : per contenuto inserito
- `<del> </del>` : per contenuto cancellato

---

### Interazione e Multimedialità (Elementi Interattivi e Non Generici)

#### Contenuti e Interazione:

- `<a> </a>` : definisce un collegamento ipertestuale; fondamentale e tra gli elementi più usati.
- `<br>` : inserisce un'interruzione di riga; estremamente comune per formattare il testo.
- `<img>` : usato per incorporare immagini; elemento vuoto molto frequente.
    - _(Gli elementi `<map>`, `<area>` e `<picture>` sono trattati insieme come parte integrante dell'uso delle immagini.)_
- `<input>` : campo per l'inserimento di dati, essenziale per i form.
- `<button> </button>` : rappresenta un pulsante cliccabile; molto usato nelle interfacce interattive.
- `<label> </label>` : associa un'etichetta descrittiva a un elemento di input; fondamentale nei moduli.
- `<select> </select>` : crea un menu a tendina; comune in form.
    - `<option> </option>` e `<optgroup> </optgroup>` sono considerati parte integrante dell'elemento `<select>`.
- `<textarea> </textarea>` : campo di testo a più righe; usato nei form.
- `<iframe> </iframe>` : incorpora un'altra pagina web all'interno della pagina corrente
- `<embed>` : incorpora contenuti esterni, come plugin multimediali
- `<video> </video>` : incorpora contenuti video; molto usato su siti multimediali.
- `<audio> </audio>` : incorpora contenuti audio; comune in siti che offrono contenuti multimediali.
- `<source>` : specifica una fonte alternativa per `<picture>`, `<audio>` e `<video>`; utilizzato in associazione agli elementi multimediali.
- `<track>` : fornisce sottotitoli o descrizioni per `<video>` e `<audio>`; meno comune.
- `<picture> </picture>` : fornisce diverse versioni di un'immagine a seconda delle condizioni del dispositivo; in crescita, ma ancora meno usato rispetto a `<img>`.
- `<wbr>` : suggerisce un possibile punto di interruzione di riga; raramente usato.
- `<map> </map>` : definisce una mappa immagine con aree cliccabili; poco comune.
    - `<area> </area>` : definisce le aree all'interno di una `<map>`.
- `<bdi> </bdi>` : isola una porzione di testo per impedire che venga influenzata dalla direzione del testo circostante; usato in casi particolari.
- `<bdo> </bdo>` : imposta esplicitamente la direzione del testo; di nicchia.
- `<progress> </progress>` : rappresenta una barra di avanzamento; utilizzato in contesti specifici.
- `<meter> </meter>` : rappresenta un valore all'interno di un intervallo noto; meno comune.
- `<output> </output>` : rappresenta il risultato di un calcolo o di un'azione dell'utente; di nicchia.