# HTML állomány felépítése

## HTML állomány kiterjesztése

A HTML állományok kiterjesztése **.html** vagy **.htm** lehet.

A böngészők, és a fejlesztésre használt szövegszerkesztők automatikusan felismerik, és statikus weboldalként kezelik ezeket az állományokat.

### Doctype

A HTML dokumentum a típusmeghatározással kezdődik, ez a **!DOCTYPE**.

Ez alapján azonosítja be a böngésző a dokumentum típusát, ettől függ az elemek megjelenítésének módja.

Kötelezően a HTML állomány **első sorában, a többi elem előtt** kell elhelyezni.

A !DOCTYPE **nem** érzékeny a kis- és nagybetűk különbözőségére

#### **XHTML 1.0**:

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

## Megjegyzések \(Comment\)

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

## HTML Címkék \(Tag\)

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

## Tulajdonságok \(Atributes\)

A HTML elemeket fel lehet ruházni tulajdonságokkal, illetve egyes HTML elemeknek kötelező megadni bizonyos tulajdonságokat.

Korábbi példa:

```markup
<elem tulajdonsag="ertek">tartalom</elem>
```

A tulajdonságok a nyitó tag-ben helyezhetőek el, szóközökkel elválasztva egymástól, és HTML tag nevétől.

![](.gitbook/assets/html-code-2.png)

Minden tulajdonság egy **név-érték** pár, balra a tulajdonság neve, jobbra az értéke, egyenlőségjellel elválasztva.

![](.gitbook/assets/html-code-3.png)

Az értéket idézőjelbe kell tenni, ha tartalmaz szóközt. Bár nem kötelező, az olvashatóság megkönnyítése érdekében ezt érdemes minden esetben kitenni.

Egyes tulajdonságok a HTML elemünk azonosítását könnyítik meg.

Az azonosító \(id\) tulajdonsággal egyedi nevet adhatunk elemeinknek:

```markup
<h1 id="main-title">Ez a főcím</h1>
```

Az osztály \(class\) tulajdonság csoportokba szervezi az elemeket:

```markup
<p class="red">Én a pirosak közé tartozom?</p>
<p class="blue">Igen, én kék vagyok, de ettől még lehetünk barátok...</p>
```

További példák tulajdonságokra:

```markup
<input type="text">      <!-- Szövegbeviteli mező -->
<input type="button">    <!-- Gomb --> 
<input type="checkbox">  <!-- Pipa --> 
<input type="password">  <!-- Jelszó --> 
```

A beviteli mező \(input\) elem megjelenése és viselkedése a **type** tulajdonságától függ.

Következő példában egy kép, az **src** a képállományra mutató hivatkozás, a **title** a kép címe, az **alt** pedig a kép tartalmának szöveges leírata:

```markup
<img 
    src="images/kutya.jpg"
    title="Alvó labradorkölyök"
    alt="A képen egy 6 hetes alvó labradorkölyök látható.">
```



