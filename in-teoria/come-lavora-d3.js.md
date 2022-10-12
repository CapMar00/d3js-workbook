# Come lavora D3.js



Gli **step per creare una visualizzazione** in <img src="../.gitbook/assets/1562726.png" alt="" data-size="line"> si possono riassumere in 4 step:

1. Trasformare i dati importati in formati compatibili con le visualizzazioni
2. Mappare i dati rispetto allo spazio della visualizzazione, ovvero rapportare i valori allo spazio sullo schermo in modo da poterli disegnare in modo proporzionato.
3. Elaborare il layout in base al tipo di visualizzazione prescelta.
4. Disegnare il grafico sullo schermo.

<img src="../.gitbook/assets/1562726.png" alt="" data-size="line"> è composta da 2 macro famiglie di funzioni:

* i metodi per manipolare i dati
* i metodi per visualizzare i dati

Una volta importata la libreria con l'approccio  preferito (CDN, npm, ecc.)&#x20;

**`<script src="https://d3js.org/d3.v7.min.js"></script>`**

si accede alle funzioni utilizzando le API con questa sintassi:\
**`d3.metodo()`**

Così, rispetto ai 4 step principali troviamo come funzioni corrispondenti per esempio:

1. **Trasformare i dati** -> `d3.min(), d3.max(), d3.sum()` che restituiscono i valori minimo, massimo e somma di un iterabile e `d3.cross()` che restituisce il prodotto cartesiano di 2 vettori.
2. **Mappare i dati nello spazio** -> `d3.scaleLinear(), d3.scaleOrdinal()` e `d3.scaleTime()` come esempi di funzione necessarie per creare le scale.
3. **Elaborare il layout** -> `d3.path()` usata per definire i path negli svg e `d3.treemap()` per creare mappe ad albero.
4. **Disegnare** -> `d3.select(), d3.selectAll(), d3.append()` funzioni che lavorano con gli elementi del DOM.

{% hint style="info" %}
Per approfondire:\
\- [https://github.com/d3/d3-array](https://github.com/d3/d3-array)\
\- [https://observablehq.com/@d3/introduction-to-d3s-scales](https://observablehq.com/@d3/introduction-to-d3s-scales)\
\- [https://observablehq.com/@d3/d3-path](https://observablehq.com/@d3/d3-path)\
\- [https://observablehq.com/@d3/treemap](https://observablehq.com/@d3/treemap)\
\- [https://github.com/d3/d3-selection](https://github.com/d3/d3-selection)
{% endhint %}
