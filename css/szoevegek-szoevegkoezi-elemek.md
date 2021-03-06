# Szövegek, szövegközi elemek

## Szövegközi elemek jellemzői

A szövegközi elemek nem törik meg a szöveget sortöréssel,  egyszerűen úgy viselkednek, mint egy szó, vagy mondat.

```markup
<p>Lórum ipse nem kérlő linc, hanem izismély. <strong>Több ménylő 
fejtő hajszolta ki,hogy a sörökök kedő.</strong> Sítos egyveklőjét 
azért zubálja gyetlennek.</p>
```

![A strong elem sz&#xF6;vegk&#xF6;zi elem l&#xE9;v&#xE9;n t&#xF6;bb sorba t&#xF6;rik.](../.gitbook/assets/inline.png)

A szövegközi megjelenítésű elemekre nem érvényesülnek a doboz modell tulajdonságok. Nem határozhatjuk meg a szélességüket, és a magasságukat, illetve nem működik a margó.

A `padding` \(belső margó\), és a `border` \(keret\) használható, a blokkos elemektől némileg eltérő módon.

CSS-el megváltoztathatjuk az elemek megjelenítési módját szövegközire:

```css
div {
    display: inline;
}
```

## Betűtípusok, bet**ű**családok

### **Betűcsalád \(font-family\)**

Betűcsaláddal határozhatjuk meg az elemeink szövegének a betűtípusát. Vesszővel elválasztva több betűtípust is megadhatunk, ezeket sorrendben megpróbálja betölteni a böngésző, ha az elsőt nem találja, megkísérli a következőt.

```css
p {
    font-family: Arial, Helvetica, sans-serif;
}
```

A fenti példában az első az **Arial** betűtípus, ami "minden" Windows-os gépen megtalálható, a második a **Helvetica**, ami nagyon hasonlít az Arial betűtípusra, de OSX operációs rendszeren elterjedt. A **sans-serif** általános betűcsalád \(generic-family\), a böngésző az ebbe a kategóriába eső elérhető fontok közül próbál egyet betölteni.

Több font felsorolásával, és általános betűcsalád megadásával biztosíthatjuk, hogy a böngésző kezelni tudja a szöveg betűt**í**pusát, hiányzó fontok esetén is.

**Általános betűcsaládok:**

* _serif_
* _sans-serif_
* _cursive_
* _monospace_
* _fantasy_

```markup
<p style="font-family: serif">Lorem ipsum dolor sit amet.</p>
<p style="font-family: sans-serif">Lorem ipsum dolor sit amet.</p>
<p style="font-family: cursive">Lorem ipsum dolor sit amet.</p>
<p style="font-family: monospace">Lorem ipsum dolor sit amet.</p>
<p style="font-family: fantasy">Lorem ipsum dolor sit amet.</p>
```

![](../.gitbook/assets/font-fam.png)

### **Web biztos fontok**

Web biztos fontok azok a betűkészletek, amik széles körben elérhetőek a különböző operációs rendszereken. Az első nagyobb csomagot a Microsoft adta ki 1996-ban **Core fonts for the Web** néven.

Az alábbi fontokat tartalmazza: _Andalé Mono, Arial, Arial Black, Comic Sans MS, Courier New, Georgia, Impact, Times New Roman, Trebuchet MS, Verdana, Webdings_

### **@font-face**

A `@font-face` segítségével mi is létrehozhatunk betűcsaládokat, és betölthetünk betűkészleteket a HTML állományainkba. Ehhez szükséges a böngészők számára is emészthető fontok \(webfontok\) használata.

{% tabs %}
{% tab title="@font-face" %}
```css
@font-face {
  font-family: 'MyWebFont';
  src: url('webfont.woff2') format('woff2'),
       url('webfont.woff') format('woff'),
       url('webfont.ttf')  format('truetype');
  font-weight: normal;
}

body {
  font-family: 'MyWebFont', sans-serif;
}
```
{% endtab %}

{% tab title="Magyarázat" %}
```css
@font-face {
  /* A font-family határozza meg a létrehozott betűcsalád nevét */
  font-family: 'MyWebFont';
  /* Az src-ben (source) adhatjuk meg a font 
     állományokat, vesszővel felsorolva. 
     A formátumot is meg kell adni, ez általában az
     állománykiterjesztéssel egyezik.
  */
  src: url('webfont.woff2') format('woff2'),
       url('webfont.woff') format('woff'),
       url('webfont.ttf')  format('truetype');
  /* Megadhatjuk a betűcsalád tagjának betűvastagságát is
     (vastagságonként egy @font-face-ben kell felvinni a fontokat) */     
  font-weight: normal;
}

body {
  /* Itt hivatkozunk a @font-face-ben létrehozott új betűcsaládra. */
  font-family: 'MyWebFont', sans-serif;
}
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Az interneten elérhetőek `@font-face` generátorok, ezekkel egy adott fontból elkészíthetjük a böngészőkkel kompatibilis font állományokat, a webfontokat, és a szükséges CSS-t is. A legismertebb szolgáltatás a Font Squirrel \([https://www.fontsquirrel.com/tools/webfont-generator](https://www.fontsquirrel.com/tools/webfont-generator)\). Egy jó alternatíva a Transfonter \([https://transfonter.org/](https://transfonter.org/)\). Mindkét szolgáltató a letölthető állományok között ad egy HTLM állományt töltelékszöveggel, amiben megnézhetjük a generált fontokat.

Ha nem akarjuk mi kiszolgálni a font állományokat egy jó ingyenes alternatíva a Google font szolgáltatása \([https://fonts.google.com/](https://fonts.google.com/)\), ahol 500 fölötti fontot érünk el magyar ékezettel.
{% endhint %}

{% hint style="info" %}
Font formátumokról:

**EOT \(Embedded Open Type\)** - Az első webfont, de a böngészők közül csak a Microsoft Explorer/Edge böngészők támogatják. Már csak akkor használjuk, ha a webalkalmazásokat régi, elavult Microsoft böngészőkre is optimalizálni kell.

**TTF \(True Type Font\)** - Egy időben ez volt a legszélesebb körben támogatott webfont, bizonyos  újabb böngészőkben feltételes a támogatottsága.

**WOFF \(Web Open Font Format\)** - Új webfont formátum, ami gyorsabb letöltődés tesz lehetővé, a régi típusokhoz hasonló, de optimalizált, tömörített formátum. A modern böngészők már mind támogatják. 

**WOFF2 \(Web Open Font Format v2\)** - A WOFF2 még optimálisabb, kisebb, támogatottsága egyenlőre részleges, nem minden modern böngésző képes feldolgozni, így az egyes verzióval együtt érdemes használni.

**SVG \(Scalable Vector Graphyc Font\)** - Az SVG szabványon alapul, támogatottsága részleges, a modern böngészők csak egy része képes feldolgozni, ráadásul nem használ tömörítést, így az SVG fontok mérete túl nagy.
{% endhint %}

{% page-ref page="../egyeb-eszkoezoek/google-fonts.md" %}

{% page-ref page="../egyeb-eszkoezoek/font-squirrel.md" %}

## Betűméret \(font-size\)

A betűmérettel határozhatjuk meg a szöveg méretét. A böngészők a **nagy** **M** betű alapján méretezik a betűket \(em méret\), ezért az elterjedt mértékegységek a em, és a rem, illetve a pixelben megadott méret.

```css
p {
    font-size: 16px;
}

span {
    font-size: 1.125em;
}
```

![K&#xFC;l&#xF6;nb&#xF6;z&#x151; bet&#x171;m&#xE9;retek pixelben meghat&#xE1;rozva.](../.gitbook/assets/font-size-px.png)

## Betűvastagság \(font-weight\)

A `font-weight`-et \(betűvastagságot\) megadhatjuk kulcsszóval, vagy számmal \(100-as lépésekben\). Az hogy az adott érték érvényesül-e a szövegre nagyban függ az adott betűtípustól.

**Használható kulcsszavak:**  
_normal, bold, bolder, lighter_  
  
**Használható számértékek:**  
_100-900_ -ig, ahol a _400_ a normal méret, _700_ a vastagon szedett \(bold\).

```css
p {
    font-weight: 400;
}

span {
    font-weight: bold;
}
```

Az hogy mely betű vastagság értéket lehet használni függ az adott fonttól. A legtöbb webfont, vagy rendszerfont a 400-as \(normal\), és a 700-as \(bold\) értékekeket támogatja csak.

![Open Sans bet&#x171;t&#xED;pus k&#xFC;l&#xF6;nb&#xF6;z&#x151; bet&#x171; vastags&#xE1;gai.](../.gitbook/assets/font-weight.png)

## Betűstílus \(font-style\)

A  betűstílussal tehetünk dőltté egy szöveget. Alapértéke a _normal_, a dőlt értékei _italic_ vagy _oblique_.

```css
p {
    font-style: normal;
}

span {
    font-style: italic;
}
```

## Betűvariáns \(font-variant\)

Betűvariáns segítségével készíthetünk kiskapitális szöveget. A kiskapitális szövegben a kisbetűk is olyan alakúak, mint a nagybetűk, de magasságuk megegyezik a kisbetűk magasságával \(bizonyos betűtípusoknál eltérhet\). Alapértéke a _normal_.

```css
p {
    font-variant: normal;
}

span {
    font-variant: small-caps;
}
```

![](../.gitbook/assets/font-variant.png)

## Szöveg igazítás \(text-align\)

A `text-align` segítségével lehet igazítani egy blokkos elemen belül a szöveget vízszintesen.

**Lehetséges értékei:**

* _left: balra igazítás_
* _right: jobbra igazítás_
* _center: középre igazítás_
* _justify: sorkizárt_

```css
p {
    text-align: center;
}
```

![Jobbra, balra, k&#xF6;z&#xE9;pre igaz&#xED;tott, &#xE9;s sorkiz&#xE1;rt sz&#xF6;veg.](../.gitbook/assets/text-align.png)

## Szöveg díszítés \(text-decoration\)

A `text-decoration`-al húzhatjuk át, vagy alá a szöveget.

**Lehetséges értékei:**

* _none: nincs dekoráció_
* _underline: aláhúzás_
* _overline: föléhúzás_
* _line-trought: áthúzás_

```css
p {
    text-decoration: none;
}

span {
    text-decoration: underline;
}
```

## Szöveg behúzás \(text-indent\)

A `text-indent` a bekezdés első sorában behúzást hoz létre. Negatív értéke is lehet, aminek hatására ki fog lógni az elemből az első sor. Megadhatjuk százalékban is, de inkább jellemző az em, vagy a pixeles értékadás. Alapértéke _0_ \(nincs behúzás\).

```css
p {
    text-indent: 1em;
}

p {
    text-indent: -1em;
}
```

![A bal has&#xE1;b pozit&#xED;v sz&#xF6;veg beh&#xFA;z&#xE1;st kapott, a jobb has&#xE1;b negat&#xED;v sz&#xF6;veg beh&#xFA;z&#xE1;st.](../.gitbook/assets/text-indent.png)

## Szöveg transzformáció \(text-transform\)

A `text-transform`-al csupa kis vagy nagybetűssé változtathatunk egy szöveget attól függetlenül, hogy a HTML állományban hogy szerepel.

**Értékei:**

* _none: nincs_
* _capitalize: szóeleji nagybetű_
* _uppercase: csupa nagybetű_
* _lowercase: csupa kisbetű_

```css
p {
    text-transform: none;
}

span {
    text-transform: uppercase;
}
```

![Sz&#xF6;veg transzform&#xE1;ci&#xF3;k sorrendben: none, capitalize, uppercase, lowercase. ](../.gitbook/assets/text-transform.png)

## Sormagasság \(line-height\)

A `line-height` határozza meg a szöveg két sora közötti távolságot. Alapértéke _normal_, megadhatjuk százalékban, vagy hosszmértékben.

```css
p {
    line-height: normal;
}

span {
    line-height: 1.25em;
}
```

![](../.gitbook/assets/line.png)

A tartalom terület \(vörös vonalakkal határolva a fenti képen\) a nagy M-betű magasságával egyező magasságú, gyakorlatban ez a font mérete \(tipográfiában a verzál magasság, ezen túlnyúlhatnak a betűk fel- és lenyúló szárai\). A szövegközi mező magassága a sormagasság \(kék vonalakkal határolt terület a fenti képen\). 

![](../.gitbook/assets/line2.png)

A tartalom terület és a szövegközi mező külömbsége a sortávolság \(adott esetben negatív értéket is felvehet\) - vonjuk ki a `line-height` \(sormagasság\) értékéből a `font-size` \(betűméret\) értékét, így megkapjuk a két sor pontos távolságát. 

![K&#xFC;l&#xF6;nb&#xF6;z&#x151; sormagass&#xE1;g &#xE9;rt&#xE9;kek em-ben megadva.](../.gitbook/assets/line-height.png)

## Szóköz \(word-spacing\)

A `word-spacing` határozza meg a szavak közötti távolságot. Alapértéke a _normal_, ez nullával egyenlő, a módosított értéke a betűtípus szóköz karakterének szélességét módosítja, akár negatív irányban is, ekkor egymásra csúsznak a szavak.

```css
p {
    word-spacing: normal;
}

span {
    word-spacing: 0.125em;
}
```

![K&#xFC;l&#xF6;nb&#xF6;z&#x151; sz&#xF3;k&#xF6;z&#xF6;k pixelben megadva.](../.gitbook/assets/letter-spacing%20%281%29.png)

## Betűköz \(letter-spacing\)

A `letter-spacing` \(betűköz\) határozza meg a betűk karaktermezői közötti távolságot. Alapértéke a _normal_, ezt módosíthatjuk hosszmérték megadásával. Értéke lehet negatív, ebben az esetben a betűk közelebb kerülnek egymáshoz.

```css
p {
    letter-spacing: normal;
}

span {
    letter-spacing: 0.125em;
}
```

![K&#xFC;l&#xF6;nb&#xF6;z&#x151; m&#xE9;ret&#x171; bet&#x171;k&#xF6;z&#xF6;k pixelben meghat&#xE1;rozva.](../.gitbook/assets/letter-spacing.png)

