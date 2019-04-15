# Kijelölők

![](../.gitbook/assets/selector.png)

## Mire szolgál a CSS kijelölő?

A **kijelölők** segítenek kiválasztani azokat a HTML elemeket, amelyekre bizonyos stílus szabályokat szeretnénk alkalmazni. Minden stílusnak tartalmaznia kell egy kijelölőt.

A következő példában, a HTML állományunkban elhelyzünk egy`h1` címet:

```markup
<h1>Helló világ</h1>
```

A `h1` elem megjelenését CSS stílusokkal tudjuk befolyásolni, a lenti példában az elem szövegszínét vörösre állítjuk. Maga a kijelölő a kapcsos zárójel nyitó eleme előtt található \(h1\).

```css
h1 {
    color: red;
}
```

A kijelölők könnyebb megértését segíti a CSS Diner nevű játék, ami elérhető az alábbi linken: [https://flukeout.github.io/](https://flukeout.github.io/)

## Általános kijelölő

Az **általános kijelölő** az összes elemre általánosan hivatkozik, segítségével a HTML dokumentumban lévő összes elemre vonatkozó stílusokat tudunk megadni.

```css
* {
    color: red;
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
    color: red;
}
```

Az elem összes példányát ki fogja választani az elem kijelölő az adott HTML dokumentumban.

A következő példában az összes cím \(`h1`-`h6`\) elemet kiválasztjuk vesszővel elválasztva \(így minden cím a HTML dokumentumban vörös szövegszínű lesz\):

```css
h1,
h2,
h3,
h4,
h5,
h6 {
    color: red;
}
```

## Osztály kijelölő

Az **osztály kijelölő** az elemet az `class` \(osztály\) tulajdonsága alapján célozza be.

```markup
<p class="first-paragraph">Lorem ipsum dolor sit amet</p>
```

```css
.first-paragraph {
    color: red;
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
    color: red;
}
```

Az azonosító kijelölő rácsjellel \(\#\) kezdődik, ezt követi az azonosító neve.

Egy HTML dokumentumban egy elem rendelkezhet egy adott egyedi azonosítóval, és ezt az elemet az azonosítókijelölővel tudjuk célozni.

{% hint style="warning" %}

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
    color: red;
}
```

## Gyermek kijelölő

A **gyermek kijelölő** az alapján jelöli ki az adott HTML elemet, hogy közvetlenül melyik elemben található \(szülő\).

```markup
<div class="parent">
    <div class="child">
        color: red;
    </div>
</div>
```

```css
.parent > .child {
    ...
}
```

Gyermek kijelölőt a `>` jellel hozhatunk létre, a `>` jel bal oldalán a szülő, jobb oldalán a gyermek található.

```css
p > span {
    color: red;
}
```

Ebben a példában _kizárólag_ a közvetlenül a `p` HTML elemekben lévő `span` elemek szövegszínét festi vörösre a CSS stílus.

## Szomszédos testvér kijelölő

Ezzel a kijelölővel egy bizonyos elem után következő elemet célozhatunk meg.

```markup
<p>Lorem ipsum dolor sit, amet consectetur adipisicing elit.</p>
<p>Doloremque impedit laborum eum ad fugiat.</p>
<p>Error quam voluptatibus sequi dolore iure corrupti ab.</p>
```

```css
p + p {
    color: red;
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
**:first-of-type** első egy bizonyos elem típusból  
**:last-of-type** utolsó egy bizonyos elem típusból

```markup
<ul>
    <li>Első elem</li>
    <li>Második elem</li>
    <li>Harmadik elem</li>
    <li>Negyedik elem</li>
    <li>Ötödik, vagy utolsó elem</li>
</ul>
```

```css
li:first-child {
    color: red;
}

li:nth-child(3) {
    color: green;
}

li:last-child {
    color: blue;
}
```

Ebben a példában a lista elemek szövegszínét módosítjuk, az első elemét a `:first-child` \(első gyermek\) kijelölő segítségével vörösre, a harmadik lista elem színét a `:nth-child()` \(n-edik elem\) kijelölővel zöldre, és végül az utolsó lista elem színét kékre a `:last-child` \(utolsó gyermek\) kijelölővel.

## Álelemek

Minden HTML elemhez hozzá lehet rendelni két **álelemet**, ezek az eredeti elem gyermekei lesznek, egyet a tartalma előtt, egyet pedig a tartalma után tud megjeleníteni a böngésző. Az így létrejövő elemek _virtuális_ elemek, a CSS stílus hozza létre őket, nem képezik a HTML dokumentum részét.

```css
p:before {
    content: "";
}

p:after {
    content: "";
}
```

Az **álelemek** CSS-ében el kell helyezni egy tartalom `content` meghatározást, ez adja meg az **álelem** tartalmát, e nélkül a böngésző nem hozza létre az álelemeket. Ez rendszerint szöveg vagy kép lehet, de üresen is lehet hagyni.

```css
p:before {
    content: "Lorem ipsum dolor...";
}

div:before {
    content: url('ribbon.png');
}
```

**Álelemet** az elem tartalma előtt a `:before` kijelölővel, a tartalom után az `:after` kijelölővel hozhatunk létre. Az **álelemek** alapesetben inline \(szövegközi\) elemek, és CSS stílusokkal módosítható a megjelenésük.

A következő példában egy főcím szövege előtt, és után elhelyezünk egy-egy kötőjelet, és a két kötőjelnek a szövegszínét is beállítjuk a `:before`, és az `:after` kijelölők segítségével:

```markup
<h1>Lorem Ipse</h1>
```

```css
h1:before,
h1:after {
    content: "-";
    color: red;
}
```

## Kijelölők listája

<table>
  <thead>
    <tr>
      <th style="text-align:left">Kijel&#xF6;l&#x151;</th>
      <th style="text-align:left">Form&#xE1;tum</th>
      <th style="text-align:left">C&#xE9;l</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#xC1;ltal&#xE1;nos kijel&#xF6;l&#x151;</td>
      <td style="text-align:left"><code>*</code>
      </td>
      <td style="text-align:left">Minden HTML elem</td>
    </tr>
    <tr>
      <td style="text-align:left">Elem kijel&#xF6;l&#x151;</td>
      <td style="text-align:left"><code>p</code>
      </td>
      <td style="text-align:left">Egy t&#xED;pusba tartoz&#xF3; &#xF6;sszes elem</td>
    </tr>
    <tr>
      <td style="text-align:left">Oszt&#xE1;ly kijel&#xF6;l&#x151;.</td>
      <td style="text-align:left"><code>.container</code>
      </td>
      <td style="text-align:left">HTML elemek <code>class</code> tulajdons&#xE1;ga alapj&#xE1;n</td>
    </tr>
    <tr>
      <td style="text-align:left">Azonos&#xED;t&#xF3; kijel&#xF6;l&#x151;</td>
      <td style="text-align:left">#main-menu</td>
      <td style="text-align:left">HTML elem <code>id</code> tulajdons&#xE1;ga alapj&#xE1;n</td>
    </tr>
    <tr>
      <td style="text-align:left">Lesz&#xE1;rmazott kijel&#xF6;l&#x151;</td>
      <td style="text-align:left">.parent .child</td>
      <td style="text-align:left">HTML elem a sz&#xFC;l&#x151;i alapj&#xE1;n</td>
    </tr>
    <tr>
      <td style="text-align:left">Gyermek kijel&#xF6;l&#x151;</td>
      <td style="text-align:left">.parent &gt; .child</td>
      <td style="text-align:left">HTML elem a k&#xF6;zvetlen sz&#xFC;l&#x151;je alapj&#xE1;n</td>
    </tr>
    <tr>
      <td style="text-align:left">Szomsz&#xE9;dos testv&#xE9;r kijel&#xF6;l&#x151;</td>
      <td style="text-align:left">h1 + p</td>
      <td style="text-align:left">HTML elem az el&#x151;z&#x151; testv&#xE9;r elem alapj&#xE1;n</td>
    </tr>
    <tr>
      <td style="text-align:left">&#xC1;loszt&#xE1;ly</td>
      <td style="text-align:left">a:hover</td>
      <td style="text-align:left">
        <p>HTML elem egy bizonyos min&#x151;s&#xE9;ge,</p>
        <p>&#xE1;llapota, sorrendje alapj&#xE1;n</p>
      </td>
    </tr>
  </tbody>
</table>