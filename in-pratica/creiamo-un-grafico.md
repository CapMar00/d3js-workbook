---
description: >-
  Applichiamo quanto visto in precedenza per realizzare un grafico che esprima
  l'andamento dei prezzi del gas da riscaldamento in Italia dal 2005 a oggi
  (ottobre 2022).
---

# Creiamo un grafico

L'andamento avrà sull'asse delle ascisse il tempo e su quello delle ordinate il prezzo.

<figure><img src="../.gitbook/assets/Prezzo-gasolio-riscaldamento.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Il codice completo del grafico è disponibile a questo link: [https://github.com/CapMar00/d3js-line-chart](https://github.com/CapMar00/d3js-line-chart)
{% endhint %}

I dati sono pubblicati dal [Ministero della Trasizione Ecologica](https://dgsaie.mise.gov.it/open-data). Sono in formato csv e fanno parte di un dataset più ampio che contiene i prezzi di più carburanti che per semplicità è stato ridotto a 2 colonne e salvato in locale:&#x20;

* **SURVEY\_DATE** -> data espressa in aaaa-mm-gg
* **HEATING\_GAS\_OIL** -> il prezzo espresso in €/1.000 L

```csv
SURVEY_DATE,HEATING_GAS_OIL
2005-01-03,948.5
2005-01-10,947.94
2005-01-17,952.42
2005-01-24,963.98
2005-01-31,972.95
...
2022-09-12,1825.04
2022-09-19,1771.42
2022-09-26,1789.38
2022-10-03,1792.42
2022-10-10,1894.96
```

### Step 0. Creiamo la struttura

Ci servirà un file `index.html` che conterrà l'import della libreria `d3.js`, qualche piccola impostazione di stile contenuta in `style.css` e un file `chart.js` che conterrà il codice per generare il grafico.

All'interno del tag `body` di `index.html` inseriamo già:

* il titolo, sommario e fonte del grafico
* un tag `svg` `#chart` con all'interno un gruppo `g` `#chart_body` che conterrà il grafico, opportunamento traslato di qualche pixel per ottimizzare la visualizzazione.

{% tabs %}
{% tab title="HTML" %}
```html
<!DOCTYPE html>
<html lang="it">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="shortcut icon" href="#" type="image/x-icon">
    <link rel="stylesheet" href="css/style.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/d3/7.6.1/d3.min.js"
        integrity="sha512-MefNfAGJ/pEy89xLOFs3V6pYPs6AmUhXJrRlydI/9wZuGrqxmrdQ80zKHUcyadAcpH67teDZcBeS6oMJLPtTqw=="
        crossorigin="anonymous" referrerpolicy="no-referrer"></script>
    <title>Prezzo del gasolio per il riscaldamento</title>
</head>

<body>
    <div id="container">
        <h1>Prezzo del gasolio per riscaldamento</h1>
        <p>Media settimanale dei prezzi nazionali dal 2005 a oggi (€/1.000 L)</p>
        <svg id="chart" width="700" height="400">
            <g id="chart_body" transform="translate(50,50)"></g>
        </svg>
        <div class=" source">
            Fonte: <a href="https://dgsaie.mise.gov.it/open-data" target="_blank" rel="noopener noreferrer">
                Ministero della Transizione Ecologica - Direzione Generale Infrastrutture e Sicurezza</a>
        </div>
    </div>
    <script src="chart.js"></script>
</body>
</html>
```
{% endtab %}

{% tab title="style.css" %}
```css
body {
  font-family: Tahoma, sans-serif;
}

a:link {
  color: #fb5c01;
  text-decoration: none;
}

a:visited {
  color: #fb5c01;
  text-decoration: none;
}

a:hover {
  color: #fb5c01;
  text-decoration: underline;
}

a:active {
  color: #fb5c01;
  text-decoration: underline;
}

div.tooltip {
  position: absolute;
  text-align: center;
  width: 150px;
  height: 40px;
  padding: 2px;
  font: 16px;
  background: #1c7af5;
  color: #fff;
  border: 0px;
  border-radius: 8px;
  pointer-events: none;
}

#container {
  width: fit-content;
  margin: auto;
}

.source {
  padding-top: 30px;
  font-size: 0.8em;
}

```
{% endtab %}

{% tab title="chart.js" %}
```javascript
// codice d3
```
{% endtab %}
{% endtabs %}

Da ora in poi ci sposteremo sul file `chart.js` e lavoreremo solo su quello.&#x20;

### Step 1. Manipoliamo i dati

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
