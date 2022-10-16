# Function chaining

<img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> utilizza in maniera estensiva l'approccio _function chaining_ dove più funzioni vengono chiamate consecutivamente sullo stesso oggetto.

```javascript
  let svg = d3
    .select("#multiple-charts")
    .selectAll("svg")
    .data(nestedDataByRegion)
    .enter()
    .append("svg")
    .attr("width", width + margin.left + margin.right)
    .attr("height", height + margin.top + margin.bottom)
    .attr("class", "unique-chart")
    .attr("id", (d) => { return d.key.replace(/[\.,\s,\']+/g, "_");})
    .append("g")
    .attr("transform", "translate(" + margin.left + "," + margin.top + ")");
```

&#x20;Le funzioni possono essere concatenate perché l'istruzione che precede restuisce un risultato che può essere processato da quella successiva.

{% hint style="info" %}
Per approfondire: [D3: Method Chaining and Functions of Data](https://www.youtube.com/watch?v=fArnX5QA17g)
{% endhint %}
