# Háttérszínek, háttérképek

## Háttérszín

A `background-color` segítségével színt adhatunk elemeink hátterének. Átlátszó szín esetén az elem mögött lévő elemek is \(részlegesen\) látszódni fognak.  
  
A háttérszín az elem teljes hátterét kitölti, látható a belső margó \(padding\), és a keret átlátszó része alatt \(border\). Alapértéke a `transparent`, vagyis átlátszó.

```css
div {
	background-color: purple;
}

ul li {
	background-color: rgba(14%, 75%, 10%, 0.75);
}
```

## Háttérkép

A `background-image` értékeként egy kép elérési útvonalát adhatjuk meg, **url\('elérési útvonal'\)** formában.  
  
A kép valós méretében jelenik meg az elem hátterében.  
  
Alapértéke a `none`, vagyis nincs.

```css
div {
    background-image: url('images/background.png');
}

ul li {
    backgroud-mage: url('http://mydomain.hu/picture.jpg');
}
```

## Háttérkép ismétlődése

A `background-repeat` segítségével szabályozhatjuk a háttérkép ismétlődését.

Értékei:

* _no-repeat_ - nincs ismétlődés
* _repeat_ - ismétlődés \(ez az alapérték\)
* _repeat-x_ - ismétlődés csak vízszintesen
* _repeat-y_ - ismétlődés csak függőlegesen

```css
div {
    background-repeat: repeat;
}

ul li {
    backgroud-repeat: no-repeat;
}
```

![](../.gitbook/assets/background-repeat.png)

## Háttérkép helyzete

A `background-position` a kép helyzetét határozza meg vízszintesen, és függőlegesen.

Megadhatjuk kulcsszavakkal, ezek:

* _center_ - középen
* _top_ - fent
* _bottom_ - lent
* _left_ - balra
* _right_ - jobbra

```css
div {
	background-position: center;
}

span {
	backgroud-position: left;
}
```

![](../.gitbook/assets/bgp-0.png)

![](../.gitbook/assets/bgp-1%20%281%29.png)

Két értéket is megadhatunk első a vízszintes, második a függőleges helyzetet adja meg.

```css
div {
	background-position: left top;
}

span {
	backgroud-position: right bottom;
}
```

![](../.gitbook/assets/bgp-2.png)

Hosszértéket, vagy százalékot is felvehet, ebben az esetben a bal felső sarok  
lesz az origó \(innen eltolva jelenik meg a kép\).

```css
div {
	background-position: 50% 50%;
}

span {
	backgroud-position: 10px 15px;
}
```

## Háttérkép méretezése

A `background-size` határozza meg, hogy az elem hátterének mekkora hányadát fedje a háttérkép. Alapértéke az _auto_ vagyis a kép eredeti  
méretében jelenik meg.

Megadhatjuk hosszmértékben a méretet, például pixelben, vagy százalékban, ami az elem méretéhez képest értendő.

Kulcsszavas értékei:

* _auto_ - eredeti méret \(alapérték\)
* _cover_ - a háttérkép teljesen lefedi az elemet
* _contain_ - a kép addig növekszik, amíg vízszintesen, vagy függőlegesen be nem tölti az elemet.

```css
div {
	background-size: cover;
}

ul li {
	backgroud-size: auto contain;
}
```

## Gyorsírásos háttér

A __`background` gyorsírásos forma, amivel egy menetben több háttér jellemzőt is megadhatunk.

```css
div {
	background: #c5c6c7 center no-repeat cover url('img/background.png');
}

ul li {
	backgroud: none;
}
```

