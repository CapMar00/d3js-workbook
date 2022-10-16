# Disegniamo il grafico

Non ci resta dunque che disegnare gli assi e il grafico sullo schermo utilizzando `d3.append()`.

Innanzitutto selezioniamo con `.select()` il gruppo `<g>` in cui inserire il grafico.

Nel caso dell'asse y dovremo applicare una trasformazione per farlo comparire al piede del grafico invece che in alto:

{% tabs %}
{% tab title="chart.js" %}
```javascript
const chartBody = d3.select("#chart_body");

const createChart = (data) => {
   
  ...
  
  const line = d3
    .line()
    .x((d) => xScale(d.date))
    .y((d) => yScale(d.price));
    
  chartBody.append("g")
    .call(d3.axisLeft(yScale));
  
  chartBody
    .append("g")
    .attr("transform", `translate(0, ${height})`)
    .call(d3.axisBottom(xScale));
}
```
{% endtab %}

{% tab title="style.css" %}
```css
.line {
  fill: none;
  stroke: #1c7af5;
  stroke-width: 3px;
}
```
{% endtab %}
{% endtabs %}

All'oggetto line invece dovremo associare i dati per poter creare il `<path>` della linea. Per farlo si utilizza `d3.datum()`, invece di `d3.data()` perché dobbiamo associare i dati a un unico elemento  `<path>` invece che ad una serie.&#x20;

{% tabs %}
{% tab title="chart.js" %}
```javascript
const chartBody = d3.select("#chart_body");

const createChart = (data) => {
   
  ...
  
  const line = d3
    .line()
    .x((d) => xScale(d.date))
    .y((d) => yScale(d.price));
    
  chartBody.append("g").call(d3.axisLeft(yScale));
  chartBody
    .append("g")
    .attr("transform", `translate(0, ${height})`)
    .call(d3.axisBottom(xScale));

  chartBody.append("path").datum(data).attr("d", line).attr("class", "line");
  
  }
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Per approfondire: [Understanding the difference between the d3 data and datum methods](https://www.intothevoid.io/data-visualization/understanding-d3-data-vs-datum/)
{% endhint %}

A questo punto il grafico è fatto. Non resta che arricchirlo con ulteriori funzionalità come per esempio visualizzando un tooltip al mouse over (come nel codice condiviso nel link a piè di pagina)&#x20;

<figure><img src="../../.gitbook/assets/grafico-con-tooltip.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Il codice completo del grafico è disponibile a questo link: [https://github.com/CapMar00/d3js-line-chart](https://github.com/CapMar00/d3js-line-chart)
{% endhint %}

