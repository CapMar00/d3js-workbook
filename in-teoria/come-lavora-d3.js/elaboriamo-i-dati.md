# Import dei dati

Per importare i dati <img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> mette a disposizione una serie di funzioni dedicate ai formati più comuni e che si occupano anche del parsing, come per esempio `d3.csv()` e `d3.json()`.

Così come Javascript, anche<img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> carica i dati in maniera asincrona: i metodi `.csv()` and `.json()` restituiscono una _promise,_ quindi la realizzazione del grafico va gestita all'interno di un costrutto `.then().catch()`:

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
