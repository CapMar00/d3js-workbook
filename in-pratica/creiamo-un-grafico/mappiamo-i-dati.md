# Mappiamo i dati

A questo punto dobbiamo rapportare i dati che abbiamo allo spazio della visualizzazione definendo una larghezza `width` e un'altezza `height` e utilizzando le opportune scale:

* `.scaleTime()` per le date
* `.scaleLinear()` per i prezzi

`.domain()` fa riferimento al dominio dei dati mentre `.range()` allo spazio della visualizzazione

{% tabs %}
{% tab title="chart.js" %}
```javascript
const createChart = (data) => {
  const width = 550;
  const height = 320;
  
  ...
  
  const dateExtent = d3.extent(data, (d) => d.date);
  const maxValue = d3.max(data, (d) => d.price);

  const xScale = d3.scaleTime().domain(dateExtent).range([0, width]);
  const yScale = d3.scaleLinear().domain([0, maxValue]).range([height, 0]);
}
```
{% endtab %}
{% endtabs %}

Nel caso dell'asse y `.range()` va dal valore massimo `height` a 0 e non il contrario perché dobbiamo tenere conto che nel sistema di coordinate degli svg l'origine degli assi è in alto a sinistra e i valori aumentano procedendo verso il basso.

<figure><img src="../../.gitbook/assets/coordinate-svg.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Per maggiori informazioni sul sistema di coordinate degli svg leggi qui: [https://www.sarasoueidan.com/blog/svg-coordinate-systems/](https://www.sarasoueidan.com/blog/svg-coordinate-systems/)
{% endhint %}
