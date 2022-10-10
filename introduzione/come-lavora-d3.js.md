# Come lavora D3.js



Gli **step per creare una visualizzazione** in <img src="../.gitbook/assets/1562726.png" alt="" data-size="line"> si possono riassumere in 4 punti:

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
**`d3.metodo`**

Così, rispetto ai 4 step principali troviamo per esempio:

1. Trasformare i dati -> `d3.max, d3.cross`:\
   d3.max è un funzione che...\
   d3.cross serve a ...
2. Mappare i dati nello spazio -> `d3.scaleLinear, d3.scaleTime` due funzione necessarie per ...
3. Elaborare il layout -> `d3.path, d3.treemap`
4. Disegnare -> `d3.select, d3.append`
