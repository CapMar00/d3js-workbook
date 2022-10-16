# Data binding

Un aspetto cruciale nell'utilizzo di <img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> è capire come <img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> associa i dati agli elementi in pagina, ovvero il _binding_ o _join_ dei dati.

Si tratta di un processo utilizzato per creare, aggiornare o rimuovere elementi ogni volta che i dati cambiano: il metodo preposto è  `.data()`.

`.data()` prende come input un array di dati e un array di elementi del documento e restituisce 3 tipi di selezioni:

* `.enter()` - rappresenta gli elementi mancanti rispetto ai dati che potrebbe essere necessario creare e aggiungere al documento.
* `.exit()` - rappresenta gli elementi in eccesso rispetto ai dati che potrebbe essere necessario rimuovere dal documento.
* `.update()` - rappresenta gli elementi esistenti che corrispondono ai dati ma che potrebbe essere necessario modificare

<figure><img src="../../.gitbook/assets/data-join (1).png" alt=""><figcaption></figcaption></figure>

La sintassi da utilizzare è `selezione.data(dataArray[, key])` in cui:

* `selezione` è una selezione di elementi che può essere anche vuota
* `.data()` associa i dati dell'array agli elementi del DOM
* &#x20;`key` è un parametro opzionale per identificare il singolo dato, per esempio l'indice

Il codice sottostante creare il legame tra i dati e gli elementi:

```javascript
d3.select('svg')
    .selectAll("circle") // selezione di elementi non ancora in pagina
    .data(data)
```

Per aggiungerli effettivamente allo schermo dobbiamo chiamare `.enter().append('circle')`:

```javascript
d3.select('svg')
    .selectAll('circle')
    .data(data)
    .enter()
    .append('circle')
```

Il codice sopra quindi seleziona i dati a cui non è associato un elemento in pagina e aggiunge gli elementi corrispondenti.

L'istruzione successiva restituisce invece la selezione degli elementi a cui non è associato nessun dato:

```javascript
d3.select('svg')
    .selectAll('circle')
    .data(data)
    .exit()
    .remove()
```

{% hint style="info" %}
Per approfondire: [Exploring D3.js Data Binding/ Joins](https://www.youtube.com/watch?v=ZOeWdkq-L90)
{% endhint %}
