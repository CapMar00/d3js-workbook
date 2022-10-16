# Associamo il layout

Per esprimere i nostri dati abbiamo scelto come visualizzazione un andamento.

Per creare questo genere di grafico <img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> mette a disposizione il metodo `.line()`

{% tabs %}
{% tab title="chart.js" %}
```javascript
const createChart = (data) => {
  ...
  const yScale = d3.scaleLinear().range([height, 0]).domain([0, maxValue]);
  const xScale = d3.scaleTime().range([0, width]).domain(dateRange);

  const line = d3
    .line()
    .x((d) => xScale(d.date))
    .y((d) => yScale(d.price));
}
```
{% endtab %}

{% tab title="Second Tab" %}

{% endtab %}
{% endtabs %}

{% hint style="info" %}
Per approfondire: [d3-shape](https://github.com/d3/d3-shape)
{% endhint %}

&#x20;
