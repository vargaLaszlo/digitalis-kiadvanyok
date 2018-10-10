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

Kötelező elemek hiányoznak a dokumentumból. Pédául nincs **!DOCTYPE** vagy **&lt;title&gt;**. Vagy hiányoznak az alapvető elemek: **&lt;html&gt; &lt;head&gt; &lt;body&gt;**.



Blokkos elem van ****[szövegközi](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements#Elements) elembe ágyazva.

```markup
<a href="#"><h1>Körtefa</h1></a>
```

Lezáró tag hiányzik, vagy a lezáró tag-ből hiányzik a "/".

```markup
<div>
    <p>Almafa
</div>
```

Elemek rosszul vannak egymásba ágyazva

```markup
<h1><span>Szilvafa</h1></span>
```

Kötelezően megadandó tulajdonságok hiányoznak a html elemekből.

```markup
<img src="fa.jpg">
```

[Elavult elemek](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#Obsolete_and_deprecated_elements) használata.

```markup
<center>Középre igazított szöveg</center>

<blink>Villogó szöveg</blink>
```

