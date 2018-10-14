# HTML hibák, és javításuk

## Szintaktikai hibák

**Szintaktikai hibának** számít, ha a HTML dokumentum **forráskódja hibás**.

Ezt rendszerint nem vesszük észre, a hibák egy részének jelenléte nem okoz vizuális eltérést, vagy a böngészők sikeresen javítják a hibát az oldal betöltésénél.

A hibákat [HTML validátorral](https://validator.w3.org/), vagy fejlesztőeszközeink beépített [hibakeresőjével](https://marketplace.visualstudio.com/items?itemName=mkaufman.HTMLHint) tudjuk felderíteni.

### **Miért kell elkerülni a szintaktikai hibákat?**

Nem minden böngésző tudja kijavítani, egy kevésbé elterjet böngészőben, amiben nem teszteltük jelentkezhet a hiba.

A fejlesztés későbbi fázisát akadályozza, eleve biztosabb mindent szabványosan felépíteni, hogy egy esetleges hiba miatt később ne ütközzünk nem várt akadályokba.  
  
Akadályozza a keresőket az oldal feldolgozásában.

### **Jellemző hibák**

#### Kötelező elemek hiányoznak a dokumentumból. 

Pédául nincs **!DOCTYPE** vagy **&lt;title&gt;**. Vagy hiányoznak az alapvető elemek: **&lt;html&gt; &lt;head&gt; &lt;body&gt;**.

{% hint style="info" %}
A dokumentum típus meghatározásának hiányában a böngésző pontos "tervrajz" nélkül próbálja összerakni a weboldalt, ez a **quirks mode**, ami egy erőforrás igényes működés, feleslegesen lassítja a felhasználó gépét.
{% endhint %}

#### Blokkos elem van ****[szövegközi](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements#Elements) elembe ágyazva.

```markup
<!-- Hibás: -->
<a href="#"><h1>Körtefa</h1></a>

<!-- Helyes: -->
<h1><a href="#">Körtefa</a></h1>
```

{% hint style="info" %}
A blokkos \(block\) és a szövegközi \(inline\) elemek megjelenítése nagyban eltér egymástól. A blokkos elemek 100%-ban kitöltik vízszintesen a böngésző ablakot, és maguk előtt, és után törést képeznek \(mellettük nem lehet semmi\). A szövegközi elemek úgy jelennek meg mint egy szó a folyóírásban, így ha szövegközi elembe ágyazunk blokkos elemet arra nincs egyértelmű és praktikus megjelenítési recept, így ezt a HTML szabványok tiltják.
{% endhint %}

#### Lezáró tag hiányzik, vagy a lezáró tag-ből hiányzik a "/".

```markup
<!-- Hibás: -->
<div>
    <p>Almafa
</div>

<!-- Helyes: -->
<div>
    <p>Almafa</p>
</div>
```

#### Elemek rosszul vannak egymásba ágyazva

```markup
<!-- Hibás: -->
<h1><span>Szilvafa</h1></span>

<!-- Helyes: -->
<h1><span>Szilvafa</span></h1>
```

**Kötelezően megadandó tulajdonságok hiányoznak a HTML elemekből.**

```markup
<!-- Hibás: -->
<img src="fa.jpg">

<!-- Helyes: -->
<img src="fa.jpg" alt="Virágos kőris, pompás lombkoronával">
```

[**Elavult elemek**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Obsolete_and_deprecated_elements) **használata.**

```markup
<!-- Hibás: -->
<center>Középre igazított szöveg</center>

<!-- Hibás: -->
<blink>Villogó szöveg</blink>
```

{% hint style="info" %}
A HTML szabvány korai fejlődési szakaszában számos elem, és tulajdonság szolgált dekorációs, megjelenési célt, ma már szinte teljesen elszeparálódott a megjelenés a HTML-től, erre a célra a CSS szolgál, így egyes elemek elavulttá váltak. Lista az elavult elemekről: [MDN - ](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Obsolete_and_deprecated_elements)[Obsolete and deprecated elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Obsolete_and_deprecated_elements)
{% endhint %}

## Szemantikai "hibák"

**Szemantikai hiba,** ha adott célra nem az annak megfelelő elemeket használjuk.

Például **szemantikus** jelentéstartalommal rendelkező elemek helyett jelentés, vagy szerepkör nélküli elemekből építkezünk.

Nem kapunk rá hibát a validátorban, viszont egyéb szempontokból tekintve nem optimális a megoldás. 

### **Mik lehetnek ezek a szempontok?**

**SEO - Search Engine Optimalization**  
Legfontosabb a keresőprogramok megítélése, a szemantikus elemek megkönnyítik a tartalom feldolgozását a keresők számára, ezért honorálják a számukra könnyen olvasható tartalmakat.

**Usability - Akadálymentesítés**  
Szemantikus elemek könnyítik a tartalom gépi feldolgozását, így például a felolvasóprogramok is képesek értelmezni azt.

**Kód olvashatóság**  
Szemantikus elemekkel könnyebben olvasható a forráskód \(tudjuk, minek mi a feladata\), ami ebben a lényeges, hogy nem csak a szerző, de egy másik fejlesztő is érteni fogja az elemek szerepét.

### **Jellemző hibák**

#### Bekezdések helyett sortöréssel ****van tagolva a szöveg.

```markup
<!-- Hibás: -->
<p>Körtefa.
<br>
<br>
Almafa</p>

<!-- Helyes: -->
<p>Körtefa.</p>
<p>Almafa</p>
```

#### Lista elemek helyett sortörésekkel létrehozott lista.

```markup
<!-- Hibás: -->
<p>* Körtefa<br>
* Almafa<br>
* Barackfa<br>
* Narancsfa</p>
​
<!-- Helyes: -->
<ul>
    <li>Körtefa</li>
    <li>Almafa</li>
    <li>Barackfa</li>
    <li>Narancsfa</li>
</ul>
```

#### Nem szemantikus elemekkel létrehozott kiemelések a szövegben.

```markup
<!-- Hibás: -->
<p>Ez egy <b>fontos</b> szöveg.</p>
​
<!-- Helyes: -->
<p>Ez egy <strong>fontos</strong> szöveg.</p>
```

#### Címek nem cím elemekből felépítve, CSS-el cím szerűre formázva.

```markup
<!-- Hibás: -->
<div class="fo-cim">Ez a főcím</div>
​
<!-- Helyes: -->
<h1>Ez a főcím</h1>
```



