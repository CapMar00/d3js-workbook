# Step 1. Importiamo i dati

Per importare i dati <img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> mette a disposizione una serie di funzioni dedicate ai formati più comuni e che si occupano anche del parsing, come per esempio `d3.csv()` e `d3.json()`.

Così come Javascript, anche<img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> carica i dati in maniera asincrona, quindi la realizzazione del grafico va gestita all'interno di una funzione di callback in modo di avere la certezza che tutti i dati siano stati caricati.

```javascript
d3.csv(urlDati)
  .then(funzione)
  .catch(errore)

d3.json(urlDati)
  .then(funzione)
  .catch(errore)
```

{% hint style="info" %}
Per approfondire: \
\- [https://github.com/d3/d3-fetch](https://github.com/d3/d3-fetch)\
\- [Reading in data](http://learnjsdata.com/read\_data.html)
{% endhint %}

### Data binding

Nel codice precedente abbiamo anche incontrato per la prima volta il metodo `.data()` con il quale si legano i dati in input agli elementi del DOM selezionati.
