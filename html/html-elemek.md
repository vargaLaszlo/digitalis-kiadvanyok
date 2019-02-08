---
description: >-
  Ebben a fejezetben áttekintjük a legjellemzőbb HTML elemeket, ez közel sem az
  elemek teljes listája, de ahhoz elegendő ez a gyűjtemény, hogy elkezdjünk
  építkezni belőlük.
---

# HTML elemek

## Gyökérelem

A `html` elem az összes többi elem szülője. Ebbe kerül az oldal teljes tartalma.

```markup
<html>
<!-- Ide kerül az oldal tartalma -->
</html>
```

Jellemző, hogy az oldalak nyelvét a `html` elemen a `lang` \(nyelv\) tulajdonsággal határozhatjuk meg.

```markup
<html lang="hu">
```

## HTML dokumentum fejléce

A `head` a dokumentum fejléce, ezt nem jeleníti meg a böngésző, a dokumentum **metaadatait** \(általános információk\) tartalmazza.

```markup
<html>
    <head>
        ...
    </head>
</html>
```

A `head` elemet közvetlenül a `html` elemben kell elhelyezni.

## HTML elemek a fejlécben

### **Az oldal címe**

A `title` elemben megadott szöveg azonosítja a HTML dokumentumot, és ez jelenik meg a böngészőablak címsorában. Kötelezően szerepelnie kell a `head` elemben.

```markup
<title>Az oldal címe</title>
```

![](../.gitbook/assets/browser-tab.png)

{% hint style="info" %}
A `title` fontos azonosítója az adott oldalnak, az internetes keresők ezt jelenítik meg kiemelve a találati listájukban. Ha lementünk a böngészőnkbe, vagy a számítógépünkre egy weboldal linket, a `title` alapján jön létre a mentett link neve.
{% endhint %}

### **Az oldal meta adatai**

A `meta` elemben helyezhetünk el információkat a weboldalunkról \(ez nem jelenik meg a látható tartalomban\). A `meta` elemeknek egy `name` \(név\) és egy `content` \(tartalom\) tulajdonsága van. A `name` határozza meg a **meta** információ típusát, a `content` pedig a hozzá rendelt információt.

```markup
<meta name="description" content="Oldal rövid leírása">
```

Kivétel a `charset` amivel az oldal karakter kódolását határozhatjuk meg, ez csak egy `charset` tulajdonsággal rendelkezik.

```markup
<meta charset="UTF-8">
```

**Példák meta információra:**

| meta `name` | Leírás |
| :--- | :--- |
| `description` | Rövid leírás az oldalról |
| `keywords` | Az oldalhoz kapcsolódó kulcsszavak |
| `author` | Az oldal szerzője |
| `viewport` | Utasítás a böngészőnek az oldal megjelenítésének módjáról |

```markup
<meta name="description" content="Oldal rövid leírása">
<meta name="keywords" content="Kulcsszavak, vesszővel, elválasztva">
<meta name="author" content="Szerző Krisztina">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### **Linkek**

A `link` elemmel hivatkozhatunk külső állományokra, ezek egy részét be fogja tölteni a böngésző. A `link` elemmel köthetünk be például egy CSS állományt a dokumentumunkba.

```markup
<link rel="shortcut icon" type="image/png" href="favicon.ico" />
<link rel="stylesheet" type="text/css" href="style.css" />
```

## HTML dokumentum törzse

A `body` a dokumentum törzse, ezt jeleníti meg a böngésző vizuálisan, ennek az elemnek a gyermeke az összes böngészőben megjelenő elem. A `body` elemet közvetlenül a `html` elemben a `head` elem után kell elhelyezni.

```markup
<html>
    <head>
        ...
    </head>
    <body>
        ...
    </body>    
</html>
```

## Szöveges elemek

### **Címek**

A HTML dokumentum tartalmát 6 cím mélységig lehet fejezetekre, alfejezetekre bontani, ezt a `h1` `h2` `h3` `h4` `h5` `h6` elemekkel tehetjük meg.

```markup
<h1>1-es cím</h1>
<h2>2-es cím</h2>
<h3>3-as cím</h3>
<h4>4-es cím</h4>
<h5>5-ös cím</h5>
<h6>6-os cím</h6>
```

### **Bekezdések**

Az oldal szöveges tartalmát bekezdésekben `p` helyezhetjük el.

```markup
<p>Lorem ipsum dolor sit amet, consectetur 
adipiscing elit. Praesent et ligula magna. 
Aliquam vestibulum fringilla tincidunt. 
Etiam in leo mi. Nunc magna quam, 
consectetur eget elit in, cursus lacinia 
justo. Aenean condimentum suscipit lectus 
sit amet pharetra. Maecenas varius ac 
libero nec varius. Praesent aliquam 
tincidunt tortor, nec imperdiet nisi 
pharetra a.</p>
```

### **Listák**

Két típusát különböztetjük meg, számozott lista `ol`, és pontozott lista `ul`, mindkettőnek gyermekei a lista elemek `li`.

#### **Számozott lista:**

```markup
<ol>
    <li>Ez egy lista elem</li>
    <li>Ez is egy lista elem</li>
    <li>És ez is</li>
</ol>
```

#### **Pontozott lista:**

```markup
<ul>
    <li>Ez egy lista elem</li>
    <li>Ez is egy lista elem</li>
    <li>És ez is</li>
</ul>
```

A listákat egymásba is lehet ágyazni, így lehet több szintű listákat létrehozni.

```markup
<ol>
    <li>Ez egy lista elem</li>
    <li>Ez is egy lista elem</li>
    <li>És ez is, de ennek vannak gyermekei
        <ul>
            <li>Ez egy lista elem</li>
            <li>Ez is egy lista elem</li>
            <li>És ez is</li>
        </ul>
    </li>
</ol>
```

{% hint style="info" %}
[ Kódpélda](https://codepen.io/_lacus/pen/qPXBjQ)
{% endhint %}

## Képek

Képeket a HTML dokumentumba az `img` \(kép\) elem segítségével tudunk beilleszteni. Két _kötelező_ tulajdonsága van, az `src` \(forrás\), ami a behivatkozott kép elérési útvonala, és az `alt` \(alternatív szöveg\), a kép tartalmának szöveges leirata.

```markup
<img src="images/kutya.jpg" alt="6 hetes alvó labradorkölyök">
```

Ha a képünk csak dekorációs célokat szolgál, és nem kapcsolódik szorosan a dokumentum szöveges tartalmához, akkor is kötelező az `alt` tulajdonság, de üresen hagyhatjuk az értékét.

```markup
<img src="page-decoration.png" alt="">
```

A képeket a böngésző megpróbálja eredeti méretükben megjeleníteni, amennyiben a megfelelő ablakméret rendelkezésre áll. A `width` \(szélesség\) és a `height` \(magasság\) tulajdonságokkal ezt felülbírálhatjuk. Ha csak az egyik értéket adjuk meg a böngésző az oldalarányok megtartásával számolja ki a másikat. Az értékek pixelben értendőek.

```markup
<img
    src="puppy.png"
    width="360"
    height="240"
    alt="3 hónapos labradorkölyök"
>
```

{% hint style="warning" %}
Fontos kitölteni a képek alternatív leírását, mert ha a kép nem tud betöltődni ez a szöveg fog megjelenni a felhasználóknak, illetve a gyengén látó felhasználók csak ezt "látják", ezt olvassa fel nekik a szövegfelolvasó programjuk. Az internetes keresők \(a szövegkörnyezet mellett\) az `alt` tulajdonság alapján kategorizálják be a honlapokon található képeket \(ennek hiányában nem fog megjelenni a kép a képkeresőkben\).
{% endhint %}

## Szövegközi elemek

A HTML elemekben lévő szöveget szövegközi \(inline\) elemekkel módosíthatjuk.

```markup
<p>A <strong>Web</strong> alapelveit <em>Tim Berners-Lee</em>, a
CERN részecskefizikai kutatóközpont munkatársa dolgozta ki
1989-ben. Eredeti  célja a különböző intézményekben világszerte 
dolgozó kutatók közötti  automatizált <em>információmegosztás</em> 
volt.</p>
```

A fenti példakódban a bekezdés egyes szakaszai fontosként \(&lt;strong&gt;\), vagy hangsúlyosként \(&lt;em&gt;\) vannak megjelölve.

| elem | leírás |
| :--- | :--- |
| `b` | Vastagon szedett szöveg, szemantikus jelentése nincs. |
| `strong` | Fontos szövegrészlet, vastagon jelenik meg. |
| `i` | Dőlt betűs szöveg, szemantikus jelentése nincs. |
| `em` | Hangsúlyos szöveg, dőlt betűvel jelenik meg. |
| `mark` | Megjelölt szöveg, sárga háttérrel jelenik meg |

```markup
<p>
    <b>Vastagon szedett szöveg</b> <br>
    <strong>Fontos szöveg</strong> <br>
    <i>Dőlt betűs szöveg</i> <br>
    <em>Hangsúlyos szöveg</em> <br>
    <mark>Kiemelt szöveg</mark>
</p>
```

![](../.gitbook/assets/inline_01.png)

| **elem** | leírás |
| :--- | :--- |
| `small` | Csökkenti a font méretet. |
| `time` | Időt, dátumot jeleníthetünk meg vele. |
| `sup` | Felső index, megemeli a szöveget |
| `sub` | Alsó index, lesüllyeszti a szöveget |
| `s` | Elavult információt jelöl, vonallal áthúzva jelenik meg. |

```markup
<p>
    <small>Kis méretű szöveg</small> <br>
    <time>20:00</time> <br>
    E=mc<sup>2</sup> <br>
    H<sub>2</sub>O <br>
    <s>Elavult imformáció</s>
</p>
```

![](../.gitbook/assets/inline2.png)

{% hint style="info" %}
Egyes szövegközi elemek csak vizuális hatást érnek el, egyes elemek jelentésbeni külömbséget is hordoznak. Például a `strong` elemben található szöveget nagyobb súllyal veszi figyelembe a Google kereső, vagy az `em` elemben lévő szöveget más hangsúllyal ejtik ki a szövegfelolvasó programok. Ezek az elemek elsősorban a webalkalmazás szövegét feldolgozó programoknak szolgáltatnak fontos információkat.
{% endhint %}

{% hint style="info" %}
[Kódpélda](https://codepen.io/_lacus/pen/aLyybM)
{% endhint %}

### Span

Van egy szövegközi elem, ami nem hordoz jelentéstartalmat, és nem módosítja a bele foglalt szöveget vizuálisan, ez a `span` elem \(szabad fordításban dirib-darab\).

```markup
<p>Ebben a szövegben van egy <span>szakasz</span>, aminek 
nem módosul a kinézete, és a szemantikai jelentése</p>
```

{% hint style="info" %}
Felmerül a kérdés, hogy mi az értelme egy elemnek, ami nem ad jelentést konteksztustól függően, és megjelenésben sem okoz érzékelhető változást. Több okból is előnyös lehet: segíti a dokumentum tartalmának strukturálását, illetve CSS segítségével módosíthatjuk a megjelenését.
{% endhint %}

## Dekorációs elemek

### **Sortörés**

A `br` \(sortörés\) elem új sorba töri a szöveget, amiben elhelyezzük, úgy hogy a `br` elem után következő szöveg már új sorba törik.

```markup
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.<br>
Donec facilisis sit amet nisi nec mattis.</p>
```

![](../.gitbook/assets/br.png)

### **Vízszintes vonal**

A `hr` \(vízszintes vonal\) elem egy vízszintes vonalat hoz létre. Célja a tartalom tagolása.

```markup
<hr>
```

## Strukturális elemek

### **Általános konténer elem**

A `div` \(csoport, rész\) elemmel hozhatunk létre általános gyűjtőelemeket, úgynevezett konténereket. A `div` nem hordoz semmilyen jelentéstartalmat, és a megjelenése is teljesen semleges, hasonlóan a korábban tárgyalt `span` elemhez, csak amíg a `span` szövegközi elem, addig a `div` blokkos elem.

Ezzel az elemmel foghatunk össze egy csoportba több elemet \(ha úgy tetszik részekre bonthatjuk `div` elemekkel egy oldal tartalmát\). A `div`-ekben bármilyen _tartalom típusú_ elemet elhelyezhetünk, például címeket, szöveget, listákat, képet, linket, más `div`-eket, vagy egyéb strukturális elemeket.

```markup
<div>
    <!-- Ide kerülnek azok az elemek, amiket össze kell fogni egy csoportba -->
</div>
```

### **A div szemantikus variációi**

A HTML korábbi verzióiban a `div` elemet ruháztuk fel szerepekkel a `role` \(szerep\) tulajdonság segítségével, ez a lehetőség most is megvan, de megjelentek a HTML5-ben új elemek amik kiváltják ezt az igényt.

#### Navigáció

A `nav` elem kifejezetten egy weboldalon belüli \(aloldalak közötti\) navigációra szolgál, így linkeket helyezhetünk el benne.

```markup
<nav>
    <a href="/homepage">Home</a>
    <a href="/contact">Contact</a>
</nav>
```

Bonyolultabb navigáció, például egy weboldal főmenüje esetében a linkeket lista elemekben csoportosíthatjuk a `nav` elemen belül.

```markup
<nav>
    <ul>
        <li><a href="/homepage">Home</a></li>
        <li><a href="/products">Products</a></li>
        <li><a href="/blog">Blog</a></li>
        <li><a href="/about">About us</a></li>
        <li><a href="/contact">Contact us</a></li>
    </ul>
</nav>
```

A menü linkek listába helyezése lehetővé teszi több szintű almenü struktúra létrehozását.

```markup
<nav>
    <ul>
        <li><a href="/homepage">Home</a></li>
        <li><a href="/products">Products</a>
            <ul>
                <li><a href="/products/books">Books</a></li>
                <li><a href="/products/magazines">Magazines</a></li>
                <li><a href="/products/comic">Comic</a></li>
                <li><a href="/products/albums">Albums</a></li>
                <li><a href="/products/guides">Pocket guides</a></li>
            </ul>
        </li>
        <li><a href="/contact">Contact us</a></li>
    </ul>
</nav>
```

#### Fejléc elem

A `header` elem használható egy weboldal fejléceként \(ebbe kerül például az oldal logója, főmenüje\), vagy kisebb tartalmi egységek fejléceként is szolgálhat. Nem összekeverendő a `head` elemmel!

#### Fő tartalmi egység

A `main` elembe kerül a lényegi tartalom egy oldalon, minden ami nem a tartalommal közvetlenül kapcsolatos \(például navigáció\), az ezen az elemen kívül helyezendő el. Egy **HTML** dokumentumban csak egy `main` elem helyezhető el.

#### **Másodlagos tartalom**

Másodlagos, a fő tartalomhoz csak kapcsolódó tartalmaz az `aside` elemben helyezhetünk el. Jellemző, hogy a weboldalak oldalsávjait \(sidebar\) `aside` elemekből építjük.

#### **Lábléc elem**

A `footer` elem a `header` elem párja, értelemszerűen vizuálisan a dokumentum \(vagy a dokumentum egy alegységének\) alján alkalmazandó.

#### **Szekció**

Egy nagyobb szerkezeti egységet tagolhatunk a `section` elemekkel kisebb egységekre.

#### **Cikk**

Az `article` egy nagyobb _összefüggő_ szöveges tartalmi egység. Egy ilyen tartalmi egység lehet egy blogbejegyzés, hír, recept, fórum hozzászólás, közlemény... Egy HTML dokumentumban több `article` is lehet.

![](../.gitbook/assets/structural.png)

## Űrlapok

### **Az űrlap elem**

Űrlapokat a `form` elemmel hozhatunk létre, az összes kitölthető űrlap mező \(pár kivételtől eltekintve\) ebben az elemben helyezendő el. A `form` elem képes a tartalmát elküldeni a webszervernek.

```markup
<form>
    ...
</form>
```

### **A beviteli elem**

Az űrlap mezőit az `input` \(beviteli mező\) elemmel hozhatjuk létre. Az `input` elem viselkedését, kinézetét meghatározza a `type` \(típus\) tulajdonsága.

```markup
<form>
    <input id="name" type="text" placeholder="Your name">
</form>
```

```markup
<form>
    <label>Szövegbeviteli mező</label> <input type="text"> <br>
    <label>E-mail</label> <input type="email"> <br>
    <label>Jelszó</label> <input type="password"> <br>
    <label>Állomány feltöltés</label> <input type="file"> <br>
    <label>Rádiógomb</label> <input type="radio"> <br>
    <label>Jelölőnégyzet</label> <input type="checkbox"> <br>
    <label>Gomb</label> <input type="button" value="Elküldés">
</form>
```

![](../.gitbook/assets/form_01.png)

### **Címke elem**

Az űrlap beviteli mezőit a `label` elem látja el feliratokkal. A `label` elem `for` tulajdonságában megadott egyedi azonosító összeköti a `label`-t az azonosítóval ellátott beviteli mezővel. Ekkor ha a címkére kattintunk, a kurzor automatikusan beáll a beviteli mezőbe.

```markup
<form>
    <label for="name">Your Name</label>
    <input id="name" type="text">
</form>
```

Ez a kötés létrejön akkor is, ha a beviteli mező a `label` gyermeke:

```markup
<form>
    <label>
        Your Name
        <input id="name" type="text">
    </label>
</form>
```

### **Szövegdoboz**

A `textarea` hasonló a szöveges beviteli mezőhöz, csak ez egy több soros, és átméretezhető beviteli eszköz.

A `rows` és `cols` \(sorok és oszlopok\) tulajdonságaival meghatározhatjuk a kiinduló méretét is.

```markup
<form>
    <textarea rows="4" cols="50"></textarea>
</form>
```

### **Lenyíló lista**

A `select` elem `option` elemeket tartalmaz, ezek a lenyíló lista választható opciói.  
Az `option` elemek közül az lesz az alapértelmezett, amelyik rendelkezik a kiválasztott \(selected\) tulajdonsággal.

```markup
<select>
    <option selected>Almafa</option>
    <option>Körtefa</option>
    <option>Barackfa</option>
</select>
```

![](../.gitbook/assets/select.png)

## Táblázatok

### **Táblázat**

A `table` elem a táblázat szülőeleme, a sorokat a `tr` elemek képzik, az oszlopokat, vagy cellákat a `td` elemek.

```markup
<table>
    <tr>
        <td>Első sor, első oszlop</td>
        <td>Első sor, második oszlop</td>
        <td>Első sor, harmadik oszlop</td>
    </tr>
    <tr>
        <td>Második sor, első oszlop</td>
        <td>Második sor, második oszlop</td>
        <td>Második sor, harmadik oszlop</td>
    </tr>
</table>
```

![](../.gitbook/assets/table.png)

Minden sorban egyező számú oszlopot kell elhelyezni.

### **Táblázat fejléc**

Táblázat cella helyett lehet táblázat fejléc cellát alkalmazni, ez a `th` elem. A táblázat fejléc cellában lévő tartalom vizuálisan hangsúlyosabban jelenik meg.

```markup
<!-- Fejléc cellák vízszintesen. -->
<table>
    <tr>
        <th>Fejléc</th>
        <th>Fejléc</th>
        <th>Fejléc</th>
    </tr>
    <tr>
        <td>Cella</td>
        <td>Cella</td>
        <td>Cella</td>
    </tr>
</table>


<!-- Fejléc cellák függőlegesen. -->
<table>
    <tr>
        <th>Fejléc</th>
        <td>Cella</td>
        <td>Cella</td>
    </tr>
    <tr>
        <th>Fejléc</th>
        <td>Cella</td>
        <td>Cella</td>
    </tr>
</table>
```

## Felsorolt elemek listája

| Elem | Hosszú név | Megjelenítési mód |
| :--- | :--- | :--- |
| `html` | Root element | block |
| `head` | Document header | none |
| `title` | Title | none |
| `meta` | Metadata | none |
| `link` | Link | none |
| `body` | Document body | block |
| `h1` `h2` `h3` `h4` `h5` `h6` | Heading | block |
| `p` | Paragraph | block |
| `ul` | Unordered list | block |
| `ol` | Ordered list | block |
| `li` | List item | list-item |
| `a` | Hiperlink | inline |
| `img` | Image | inline |
| `b` | Bold | inline |
| `strong` | Strong | inline |
| `i` | Italic | inline |
| `em` | Emphasis | inline |
| `small` | Small text | inline |
| `time` | Time | inline |
| `sup` | Superscript | inline |
| `sub` | Subscript | inline |
| `s` | Strikethrough | inline |
| `span` | Span | inline |
| `br` | Break line | inline |
| `hr` | Horisontal line | block |
| `div` | Division | block |
| `nav` | Navigation | block |
| `header` | Header | block |
| `main` | Main content | block |
| `aside` | Aside | block |
| `footer` | Footer | block |
| `section` | Section | block |
| `article` | Article | block |
| `form` | Form | block |
| `input` | Input field | inline-block |
| `textarea` | Text area | inline-block |
| `button` | Button | inline-block |
| `label` | Label | inline |
| `table` | Table | table |
| `tr` | Table row | table-row |
| `td` | Table cell | table-cell |
| `th` | Table cell header | table-cell |

