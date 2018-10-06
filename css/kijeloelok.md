# Kijelölők

![](../.gitbook/assets/selector.png)

## Mire szolgál a CSS kijelölő?

A **kijelölők** segítenek kiválasztani azokat az elemeket, amelyekre bizonyos stílus szabályokat szeretnénk alkalmazni. Minden stílusnak tartalmaznia kell egy kijelölőt.

## Általános kijelölő

Az **általános kijelölő** az összes elemre általánosan vonatkozik.

```css
* {
    ...
}
```

## Elem kijelölő

Az **elem kijelölő** ez elemeket típusuk alapján azonosítja. Az alábbi példában a bekezdésekre \(p\) célzunk:

```markup
<p>Lorem ipsum dolor sit amet</p>
```

```css
p {
    ...
}
```

## Osztály kijelölő

Az **osztály kijelölő** az elemet az **class** \(osztály\) ****tulajdonsága alapján célozza be.

```markup
<p class="first-paragraph">Lorem ipsum dolor sit amet</p>
```

```css
.first-paragraph {
    ...
}
```

Ugyanazzal az osztállyal több elem is rendelkezhet, és egy elem rendelkezhet több osztállyal is. Így lehetőség van elemeinket rugalmasan csoportosítani.

## Azonosító kijelölő

Az **azonosító kijelölő** az elemet az **id** \(egyedi azonosító\) tulajdonsága alapján célozza be.

```markup
<p id="introduction">Lorem ipsum dolor sit amet</p>
```

```css
#introduction {
    ...
}
```

Egy HTML dokumentumban egy elem rendelkezhet egy adott egyedi azonosítóval, és ezt az elemet az azonosítókijelölővel tudjuk célozni.

## Leszármazott kijelölő

Ezzel a kijelölővel szülő elem alapján tudunk szűkíteni egy leszármazottra.

```markup
<section>
    <div>
        <p>Lorem ipsum dolor sit amet</p>
    </div>
</section>
```

```css
section p {
    ...
}
```

## Szomszédostestvér kijelölő

Ezzel a kijelölővel egy bizonyos elem után következő elemet célozhatunk meg.

```markup
<p>Lorem ipsum dolor sit amet</p>
<p>Dolor sit amet</p>
```

```css
p + p {
    ...
}
```

## Álosztályok

### Állapot álosztályok

Ezekkel a kijelölőkkel egy bizonyos állapotban lévő elemre hivatkozhatunk. Ilyen állapot például ha egy link fölött áll az egérkurzor, vagy ha egy beviteli mezőbe  
írunk éppen.

**:active** Aktív állapotban lévő elemre vonatkozik, egy link addig aktív, amíg lenyomva tartjuk az egér gombot.  
**:focus** Azokra az elemekre vonatkozik, amik fókuszban vannak \(ráléptettünk tabbal, vagy benne állunk egy űrlap mezőben\).  
**:hover** Az egérkurzor alatti elemekre vonatkozik.  
**:visited** Azokra a hivatkozásokra vonatkozik, amiket korábban már bejártunk.  
**:empty** Üres, és gyermek nélküli elemeket lehet kiválasztani vele.  
**:link** Eddig még nem bejárt linkeket lehet vele célozni.  
**:checked** Megjelölt input elemeket céloz.

```css
a:hover {
    color: red;
}
```

A fenti példában a linkek vörös szövegszínt kapnak, ha föléjük kerül az egér kurzor.

## Pozíció álosztályok

Ezekkel a kijelölőkkel egy bizonyos pozícióban lévő elemre hivatkozhatunk. Ilyen pozíció, hogy egy elem páratlan, vagy páros elem egy sorozatban, esetleg az első vagy az utolsó darabja egy sorozatnak.

**:nth-child\(n\)** n-edik elem a sorban  
**:nth-type\(n\)** n-edik bizonyos elem   
**:first-child** első elem  
**:last-child** utolsó elem  
**:first-of-type** első egy tipusból  
**:last-of-type** utolsó egy tipusból

## Álelemek

Minden HTML elemhez hozzá lehet rendelni két **álelemet**, ezek az eredeti elem gyermekei lesznek, egyet a tartalma előtt, egyet pedig a tartalma után tud megjeleníteni a böngésző.

```css
p:before {
    content: "";
}

p:after {
    content: "";
}
```

Az **álelemek** CSS-ében el kell helyezni egy tartalom "content" meghatározást, ez adja meg az álelem tartalmát. Ez rendszerint szöveg vagy kép lehet, de üresen is lehet hagyni.

```css
p:before {
    content: "Lorem ipsum dolor...";
}

div:before {
    content: url('ribbon.png');
}
```

