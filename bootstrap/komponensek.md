# Komponensek

A Bootstrap komponensei előre elkészített felhasználói felület darabkák, rendszerint egy kötött formátumú HTML struktúrából állnak, amire a Bootstrap CSS stílusai, és adott esetben a Bootstrap JavaScript hatással van.

Ebben a fejezetben bemutatásra kerülő komponensek a legjellemzőbben használtak közül lettek kiválogatva, bővebben a komponensekről az alábbi linken olvashatunk: [https://getbootstrap.com/docs/4.4/components](https://getbootstrap.com/docs/4.4/components)

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

Média elemről bővebben:

{% embed url="https://getbootstrap.com/docs/4.4/components/media-object/" %}

## Kártya

A kártyákban különböző tartalmakat helyezhetünk el, például képet a tetején vagy az alján a `card-img-bottom` és `card-img-top` osztályokkal \(ezt a képen kell elhelyezni\).

```markup
<div class="card" style="width: 18rem;">
  <img src="duckling.jpg" class="card-img-top" alt="Kiskacsa">
  <div class="card-body">
    <h3 class="card-title">Házikacsa</h3>
    <p class="card-text">A házikacsa (Anas platyrhynchos domestica) a récefélék családjába tartozó baromfi, a tőkés réce (vadkacsa) alfaja, háziasított változata...</p>
    <a href="#" class="btn btn-primary">Réce rendelés</a>
  </div>
</div>
```

![](../.gitbook/assets/card.png)

A kártyában elhelyezett `card-body` osztályú elem gondoskodik az elemek eltartásáról: 

```markup
<div class="card" style="width: 18rem;">
  <div class="card-body">
    <img src="duckling-t.jpg" class="img-fluid rounded mb-3" alt="Kiskacsa">
    <h5 class="card-title">Házikacsa</h5>
    <p class="card-text">A házikacsa (Anas platyrhynchos domestica) a récefélék családjába tartozó baromfi, a tőkés réce (vadkacsa) alfaja, háziasított változata...</p>
    <a href="#" class="btn btn-primary">Réce rendelés</a>
  </div>
</div>
```

![](../.gitbook/assets/card-body.png)

A kártyákban el lehet helyezni előre formázott listákat, ezekből  függőleges navigációs menü szervezhető: 

```markup
<div class="card" style="width: 18rem;">
    <div class="card-header font-weight-bold">
        Kacsaféléink
    </div>
    <ul class="list-group list-group-flush">
        <li class="list-group-item"><a href="#">Házikacsa</a></li>
        <li class="list-group-item"><a href="#">Indiai futókacsa</a></li>
        <li class="list-group-item"><a href="#">Tőkés kacsa</a></li>
    </ul>
</div>
```

![](../.gitbook/assets/vertical-menu.png)

Kártyáról bővebben:

{% embed url="https://getbootstrap.com/docs/4.4/components/card/" %}

## Jumbotron

A Jumbotron, vagy marketink banner a weboldalunk nyitó eleme, méretéből kifolyólag szöveges vagy képi tartalmára irányítja a látogató tekintetét.

```markup
<div class="jumbotron">
   <h1 class="display-4">Üdvözöljük honlapunkon</h1>
   <p class="lead">Lorem ipsum, dolor sit amet consectetur adipisicing 
   elit. Autem deleniti eos possimus.</p>
   <hr class="my-4">
   <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Animi
   eos numquam eius expedita eligendi rerum, exercitationem consequuntur
   voluptatem aut quisquam?</p>
   <a class="btn btn-primary btn-lg" href="#">Olvasson tovább</a>
 </div>
```

![](../.gitbook/assets/jumbotron.png)

A Jumbotronnak van egy széles \(faltól falig érő\) változata. ezt a `jumbotron-fluid` osztállyal hozzuk létre.

```markup
<div class="jumbotron jumbotron-fluid">
    <div class="container">
        <h1 class="display-4">Üdvözöljük honlapunkon</h1>
        <p class="lead">Lorem ipsum, dolor sit amet consectetur
        adipisicing elit. Autem deleniti eos possimus.</p>
        <hr class="my-4">
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing
        elit. Animi eos numquam eius expedita eligendi rerum,
        exercitationem consequuntur voluptatem aut quisquam?</p>
        <a class="btn btn-primary btn-lg" href="#">Olvasson tovább</a>
    </div>
</div>
```

![](../.gitbook/assets/jumbotron-fluid.png)

Jumbotronról bővebben:

{% embed url="https://getbootstrap.com/docs/4.4/components/jumbotron/" %}





