# Kijelölők

![](../.gitbook/assets/selector.png)

## Mire szolgál a CSS kijelölő?

A **kijelölők** segítenek kiválasztani azokat a HTML elemeket, amelyekre bizonyos stílus szabályokat szeretnénk alkalmazni. Minden stílusnak tartalmaznia kell egy kijelölőt.

## Általános kijelölő

Az **általános kijelölő** az összes elemre általánosan hivatkozik, segítségével a HTML dokumentumban lévő összes elemre vonatkozó stílusokat tudunk definiálni.

```css
* {
    ...
}
```

Az általános kijelölőt csillag \(\*\) karakterrel hozhatunk létre.

{% hint style="warning" %}
Az általános kijelölő hatással van a HTML dokumentum fejlécére is, próbáljuk csak ki az alábbi stílust:  
  
`* {   
    display: block;  
}`
{% endhint %}

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

Az elem összes példányát ki fogja választani az elem kijelölő az adott HTML dokumentumban.

## Osztály kijelölő

Az **osztály kijelölő** az elemet az `class` ****\(osztály\) ****tulajdonsága alapján célozza be.

```markup
<p class="first-paragraph">Lorem ipsum dolor sit amet</p>
```

```css
.first-paragraph {
    ...
}
```

Az osztály kijelölő ponttal kezdődik \(.\) ezt követi az osztály neve.

Ugyanazzal az osztállyal több elem is rendelkezhet, és egy elem rendelkezhet több osztállyal is. Így lehetőség van elemeinket rugalmasan csoportosítani.

```markup
<div class="osztaly-1 osztaly-2 osztaly-3">...</div>
```

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

Az azonosító kijelölő rácsjellel \(\#\) kezdődik, ezt követi az azonosító neve.

Egy HTML dokumentumban egy elem rendelkezhet egy adott egyedi azonosítóval, és ezt az elemet az azonosítókijelölővel tudjuk célozni.

{% hint style="warning" %}
Az osztály és az azonosító nevére vonatkoznak bizonyos megkötések, ezek a következők: Speciális karakter nem lehet a névben, a speciális karakterek közül kivételt képez a kötőjel \(-\), és az aláhúzás jel \(\_\), ezek megengedettek. Nem kezdődhetnek számmal, két kötőjellel, vagy egy kötőjellel, és egy számmal. Az alábbi osztálynevek és azonosítók **hibásak**:

* &item
* 4item
* --item
* -4item
{% endhint %}

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

## Szomszédos testvér kijelölő

Ezzel a kijelölővel egy bizonyos elem után következő elemet célozhatunk meg.

```markup
<p>Lorem ipsum dolor sit, amet consectetur adipisicing elit.</p>
<p>Doloremque impedit laborum eum ad fugiat.</p>
<p>Error quam voluptatibus sequi dolore iure corrupti ab.</p>
```

```css
p + p {
    ...
}
```

Ebben az esetben a második, és a harmadik bekezdésre fog vonatkozni a stílus \(ezek a bekezdések találhatóak egy másik után\).

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

