# Function chaining

<img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> utilizza in maniera estensiva l'approccio _function chaining_ dove più funzioni vengono chiamate consecutivamente sullo stesso oggetto.

```javascript
d3.select("body")
    .append("p")
    .text("Hello World!")
    .attr("style", "color:blue");
```

&#x20;Le funzioni possono essere concatenate perché l'istruzione che precede restuisce un risultato che può essere processato da quella successiva.
