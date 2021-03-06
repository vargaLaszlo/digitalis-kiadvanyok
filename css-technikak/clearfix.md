# Clearfix

A Clearfix arra a problémára ad megoldást, hogy az [úsztatott elemek](../css/usztatas.md#usztatott-elemek-viselkedese-szoevegben) nem tolják szét a szülő konténerük magasságát, így például ha egy elem csak úsztatott elemeket tartalmaz, a magassága 0-val lesz egyenlő.

 Az alábbi példában a nem úsztatott elem a szülő magasságát széttolja \(a szülő elem vörös kerettel van körbevéve\).

![](../.gitbook/assets/clearfix01.png)

A gyermeket balra vagy jobbra úsztatva a szülő elem magasságára már nem lesz hatással: 

![A gyermek elem jobbra &#xFA;sztatva.](../.gitbook/assets/clearfix02.png)

Ez jellemzően akkor jelent gondot, ha szövegben úsztatunk egy képet, és a kép túllóg a szülő elem határán:

![A sz&#xF6;vegben a k&#xE9;p balra van &#xFA;sztatva.](../.gitbook/assets/clearfix03.png)

Az alábbi CSS-t elhelyezve a szülő elemen az úsztatott gyermekek befolyásolják az elem magasságát:

{% tabs %}
{% tab title="CSS" %}
```css
.cf:before,
.cf:after {
  content: " ";
  display: table;
}


.cf:after {
  clear: both;
}
```
{% endtab %}

{% tab title="HTML" %}
```
<div class="cf">
     <img src="tiger.jpg" alt="Sleaping tiger">
     <p>Lorem ipsum dolor sit amet ...</p>  
</div>

```
{% endtab %}
{% endtabs %}

![](../.gitbook/assets/clearfix04.png)

