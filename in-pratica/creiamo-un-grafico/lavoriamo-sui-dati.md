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

I dati vengono importati in formato stringa ma per potere applicare le funzioni di d3 abbiamo bisogno che siano rispettivamente in un formato `date` e numerico:\


{% tabs %}
{% tab title="chart.js" %}
```javascript
d3.csv("data/weekly_fuel_prices_from_2005_to_20221015.csv").then((data) =>
  createChart(data)
);

const createChart = (data) => {
  data = data.map((d) => ({
    date: new Date(d.SURVEY_DATE),
    price: +d.HEATING_GAS_OIL,
  }));
}
```
{% endtab %}
{% endtabs %}

Dobbiamo anche definire quali sono il minimo e il massimo dei range di valori per poter costruire le scale. Nel caso delle date questi valori ci vengono fornite da `d3.extent()`.\
Per i prezzi invece vogliamo che l'asse y parta da 0 per cui calcoliamo solo il massimo con `d3.max()`

{% tabs %}
{% tab title="chart.js" %}
```javascript
const createChart = (data) => {
  data = data.map((d) => ({
    date: new Date(d.SURVEY_DATE),
    price: +d.HEATING_GAS_OIL,
  }));
  
  const dateRange = d3.extent(data, (d) => d.date);
  const maxValue = d3.max(data, (d) => d.price);
}

```
{% endtab %}
{% endtabs %}
