# Step 1. Importiamo i dati

Per importare i dati <img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> mette a disposizione una serie di funzioni dedicate ai formati più comuni e che si occupano anche del parsing, come per esempio `d3.csv()` e `d3.json()`.

Così come Javascript, anche<img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> carica i dati in maniera asincrona. `.csv()` and `.json()` restituiscono una _promise_ quindi la realizzazione del grafico va gestita all'interno di un metodo `.then()`:

```javascript
d3.csv(urlDati)
  .then(funzione creaGrafico())
  .catch(errore)

d3.json(urlDati)
  .then(funzione creaGrafico())
  .catch(errore)
```

{% hint style="info" %}
Per approfondire: \
\- [https://github.com/d3/d3-fetch](https://github.com/d3/d3-fetch)\
\- [Reading in data](http://learnjsdata.com/read\_data.html)\
\- [JavaScript Promises](https://www.freecodecamp.org/news/javascript-promise-methods/)
{% endhint %}

### Data binding

Un aspetto cruciale nell'utilizzo di <img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> è capire come <img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> associa i dati agli elementi in pagina, ovvero il _binding_ o _join_ dei dati.

Si tratta di un processo utilizzato per creare, aggiornare o distruggere elementi ogni volta che i dati cambiano e viene richiamato dal metodo  `.data()` .

`.data()` prende come input un array di dati e un array di elementi del documento e restituisce tre selezioni:

* `.enter()` - rappresenta gli elementi mancanti rispetto ai dati che potrebbe essere necessario creare e aggiungere al documento.
* `.exit()` - rappressenta gli elementi in eccesso rispetto ai dati che potrebbe essere necessario rimuovere dal documento.
* `.update()` - rappresenta gli elementi esistenti che corrispondono ai dati ma che potrebbe essere necessario modificare

<figure><img src="../../.gitbook/assets/data-join (1).png" alt=""><figcaption></figcaption></figure>

La sintassi da utilizzare è `selezione.data(array[, key])` in cui `key` è un parametro opzionale per identificare il singolo dato, per esempio l'indice:

```javascript
    d3.select('svg')
        .selectAll('circle')
        .data(data)
        .enter()
```

{% hint style="info" %}
Per approfondire: [Exploring D3.js Data Binding/ Joins](https://www.youtube.com/watch?v=ZOeWdkq-L90)
{% endhint %}
