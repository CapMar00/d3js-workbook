# Le scale

I dati difficilmente corrispondono già alla posizione e alle dimensioni degli elementi grafici sullo schermo.

Per poterli normalizzare e visualizzare correttamente si utilizzano le scale che esprimono valori continui o discreti e rapporti lineari o più complessi:

* `d3.scaleLinear()`
* `d3.scaleLog()`
* `d3.scaleOrdinal()`

A ciascuna scala è associato un domain e un range: `.domain()` fa riferimento al dominio dei dati mentre `.range()` allo spazio della visualizzazione.\


<figure><img src="../../.gitbook/assets/domain-range.svg" alt=""><figcaption></figcaption></figure>

Le scale mappano il set di valori del domain nel set di valori del range secondo la relazione determinata dal tipo di scala prescelto.

{% hint style="info" %}
Per approfondire:\
\- [D3 Scale Functions](https://www.d3indepth.com/scales/)\
\- [https://github.com/d3/d3-scale](https://github.com/d3/d3-scale)
{% endhint %}