# HTML állomány felépítése

## HTML állomány felépítése

### HTML állomány kiterjesztése

A HTML állományok kiterjesztése **.html** vagy **.htm** lehet.

A böngészők, és a fejlesztésre használt szövegszerkesztők automatikusan felismerik, és statikus weboldalként kezelik ezeket az állományokat.

### Doctype

A HTML dokumentum a típusmeghatározással kezdődik, ez a **!DOCTYPE**.

Ez alapján azonosítja be a böngésző a dokumentum típusát, ettől függ az elemek megjelenítésének módja.

Kötelezően a HTML állomány **első sorában, a többi elem előtt** kell elhelyezni.

A !DOCTYPE **nem** érzékeny a kis- és nagybetűk különbözőségére

**XHTML 1.0**:

```markup
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" ".../xhtml1-transitional.dtd">
```

```markup
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" ".../xhtml1-strict.dtd">
```

```markup
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN" ".../xhtml1-frameset.dtd">
```

Régebbi verzióknál a !DOCTYPE tartalmazta a **DTD** \(Document Type Definition\) állományokra mutató hivatkozást, a **HTML 5** esetében ez az elem is egyszerűsödött.

#### HTML 5

```markup
<!DOCTYPE html>
```



### Megjegyzések \(Comment\)

A HTML állományban elhelyezhetők megjegyzések:

```markup
<!-- Ez egy megjegyzés -->
```

A megjegyzés nyitó \(&lt;!--\), és záró \(--&gt;\) karaktersorozata közötti részt a böngésző figyelmen kívül hagyja.

A megjegyzés lehet kód magyarázat, jelölhetjük vele szekciók elejét és végét, ez a forráskód olvashatóságát könnyíti.

Elrejthetünk vele HTML elemeket is:

```markup
<ul>
    <li>Alma</li>
    <!--<li>Körte</li>-->
    <li>Barack</li>
</ul>
```



### HTML Címkék \(Tag\)

A HTML dokumentum **tag**-ekből \(címke\) épül fel, ezekből képezi le a böngésző a HTML **elemeket**, miután beolvasta a dokumentumot. 

Egy lehetséges HTML elem:

```markup
<elem tulajdonsag="ertek">tartalom</elem>
```

A HTML elemek **nyitó** és **záró** **tagből** állnak, amennyiben lehet tartalmuk:

![](.gitbook/assets/html-code-1.png)



Az elemek egymásba ágyazhatóak:

```markup
<ul>
    <li>Ez egy lista elem</li>
    <li>Ez egy másik lista elem</li>
    <li>Ez pedig egy harmadik!</li>
</ul>
```

A fenti példában az &lt;ul&gt; egy lista, amiben lista elemek  \(&lt;li&gt;\) vannak, ez a **tartalma**. Az &lt;li&gt;-k az &lt;ul&gt; **gyermek elemei**, és egymásnak **testvér elemei**.

Vannak HTML elemek, amiknek nem lehet tartalma, így záró tag-re nincs szükség:

```markup
<br> <!-- Sortörés -->

<hr> <!-- Vízszintes vonal -->

<img src=kep.jpg> <!-- Kép -->
```



### Tulajdonságok \(Atributes\)



