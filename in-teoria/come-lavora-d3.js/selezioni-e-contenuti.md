# Le selezioni

Le selections di <img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> permette di selezionare elementi del DOM e di manipolarli.

Esistono 2 metodi per farlo:

* `d3.select(selettore)` che seleziona il primo elemento di un tipo
* `d3.selectAll(selettore)` che seleziona tutti gli elementi di un tipo

Fra le parentesi si posso utilizzare tutti i selettori validi nei CSS: tag, classi, id, ecc.

Le selezioni possono essere concatenate:

```javascript
let title = d3.select("div").select(".title")
```

Così selezioniamo il primo elemento con classe `title` all'interno del primo `div` e la assegniamo a una variabile title.
