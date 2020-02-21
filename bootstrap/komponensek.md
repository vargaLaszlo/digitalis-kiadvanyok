# Komponensek

A Bootstrap komponensei előre elkészített felhasználói felület darabkák, rendszerint egy kötött formátumú HTML struktúrából állnak, amire a Bootstrap CSS stílusai, és adott esetben a Bootstrap JavaScript hatással van.

Ebben a fejezetben bemutatásra kerülő komponensek a legjellemzőbben használtak közül lettek kiválogatva, bővebben komponensekről az alábbi linken olvashatunk: [https://getbootstrap.com/docs/4.4/components](https://getbootstrap.com/docs/4.4/components)

## Média elem

A média elem segítségével képet helyezhetünk el egy cím és a hozzá tartozó bekezdés\(-ek\) mellett. Jellemző felhasználása blog, vagy hír lista.

```markup
<div class="media">
  <img src="duckling.jpg" class="mr-3" alt="Kiskacsa" width="96">
  <div class="media-body">
    <h3 class="mt-n1">Indiai futókacsa</h3>
    A házikacsa (Anas platyrhynchos domestica) a récefélék családjába
    tartozó baromfi, a tőkés réce (vadkacsa) alfaja, háziasított változata.
    Többnyire fehér színben tenyésztik, de egyes vidékeken, különösen ott,
    ahol vadon élő őseivel könnyen kereszteződhet „vad” színezetű
    példányokat is találunk.
  </div>
</div>
```

![](../.gitbook/assets/media-block.png)

A kép és a szöveges tartalom megcserélésével vízszintesen tudjuk rendezni az elemeket:

```markup
<div class="media">
  <div class="media-body">
    <h3 class="mt-n1">Indiai futókacsa</h3>
    A házikacsa (Anas platyrhynchos domestica) a récefélék családjába
    tartozó baromfi, a tőkés réce (vadkacsa) alfaja, háziasított változata.
    Többnyire fehér színben tenyésztik, de egyes vidékeken, különösen ott,
    ahol vadon élő őseivel könnyen kereszteződhet „vad” színezetű
    példányokat is találunk.
  </div>
  <img src="duckling.jpg" class="ml-3" alt="Kiskacsa" width="96">
</div>
```

![](../.gitbook/assets/media-block-reverse.png)

