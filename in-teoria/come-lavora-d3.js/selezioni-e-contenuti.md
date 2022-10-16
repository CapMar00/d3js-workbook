# Selezioni e contenuti

Le selections di <img src="../../.gitbook/assets/1562726.png" alt="" data-size="line"> permette di selezionare elementi del DOM e di manipolarli.

Esistono 2 metodi per farlo:

* `d3.select(selettore)` che seleziona il primo elemento di un tipo
* `d3.selectAll(selettore)` che seleziona tutti gli elementi di un tipo

Fra le parentesi si posso utilizzare tutti i selettori validi nei CSS: tag, classi, id, ecc.

Le selezioni possono essere concatenate:

```javascript
let title = d3.select("div").select(".title")
```

Così per esempio abbiamo selezionato il primo elemento con classe `title` all'interno del primo `div` e lo abbiamo assegnato a una variabile title.

### Aggiungere elementi

Per aggiungere degli elementi si usa il metodo .append() e la sintassi è questa:\
`selezione.append(tag)`\
ovvero si seleziona l'elemento padre e poi si appende il figlio.

Per esempio per aggiungere un `div` al `body`:

```javascript
  const div = d3
    .select("body")
    .append("div")
```

Per inserire del contenuto all'interno del nuovo div possiamo usare:

* .text() che
* .html() che

### Rimuovere elementi

Per eliminare un elemento presente in pagina si usa la sintassi:\
`selezione.remove()`\
``ma questa volta la selezione fa riferimento all'elemento da rimuovere.

Così per rimuore tutti gli `li` di una lista, scriveremo:

```javascript
d3.selectAll("li").remove()
```

e per rimuovere solo il primo

```javascript
d3.select("li").remove()
```