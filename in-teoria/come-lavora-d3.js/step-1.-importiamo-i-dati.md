# Step 1. Importiamo i dati

Per importare i dati  <img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> mette a disposizione una serie di funzioni dedidate a formati più comuni, in particolare d3.csv() e d3.json().

<img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> importa i dati in maniera asincrona, quindi la realizzazione del grafico va gestita .

{% hint style="info" %}
Per approfondire: [https://github.com/d3/d3-fetch](https://github.com/d3/d3-fetch)
{% endhint %}

### Data binding

Nel codice precedente abbiamo anche incontrato per la prima volta il metodo `.data()` con il quale si legano i dati in input agli elementi del DOM selezionati.
