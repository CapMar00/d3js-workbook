# Associamo il layout

Per esprimere i nostri dati abbiamo scelto come visualizzazione un andamento.

Per creare questo genere di grafico <img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> mette a disposizione il metodo generatore `.line()` che converte ogni dato nelle corrispondenti coordinate secondo le scale previste.

{% tabs %}
{% tab title="chart.js" %}
```javascript
const createChart = (data) => {
  ...
  const yScale = d3.scaleLinear().range([height, 0]).domain([0, maxValue]);
  const xScale = d3.scaleTime().range([0, width]).domain(dateRange);

  const valueLine = d3
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
Per approfondire:\
\- [d3-shape](https://github.com/d3/d3-shape)\
\- [https://observablehq.com/@d3/d3-line](https://observablehq.com/@d3/d3-line)
{% endhint %}

&#x20;
