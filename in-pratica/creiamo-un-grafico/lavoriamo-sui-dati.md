# Lavoriamo sui dati

Da ora in poi ci sposteremo sul file `chart.js` e lavoreremo solo su quello.&#x20;

Importiamo i dati per poi richiamare la funzione che costruirà il grafico e che chiamiamo `createChart()`

{% tabs %}
{% tab title="chart.js" %}
```javascript
d3.csv("data/weekly_fuel_prices_from_2005_to_20221015.csv").then((data) =>
  createChart(data)
);

const createChart = (data) => {
  console.log(data);
}
```
{% endtab %}
{% endtabs %}

I dati vengono importati in formato stringa ma per poterci lavorare abbiamo bisogno che siano rispettivamente in un formato `date` e numerico.\
Fissiamo una larghezza e un'altezza per il grafico:\
&#x20;

{% tabs %}
{% tab title="chart.js" %}
```javascript
d3.csv("data/weekly_fuel_prices_from_2005_to_20221015.csv").then((data) =>
  createChart(data)
);

const createChart = (data) => {
  const width = 550;
  const height = 320;

  data = data.map((d) => ({
    date: new Date(d.SURVEY_DATE),
    price: +d.HEATING_GAS_OIL,
  }));
}
```
{% endtab %}
{% endtabs %}
