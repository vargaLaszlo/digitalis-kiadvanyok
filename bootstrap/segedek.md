# Segédek

A segédek \(utilities\) CSS osztályok, amik segítségével egyszerű stílusokat tudunk alkalmazni a HTML elemeinkre, például be tudjuk állítani nekik háttér vagy szövegszínt.

## Szövegszín

## Háttérszínek

Az elemeknek a `bg-` osztályokkal lehet háttérszínt adni az előre definiált színkészletből.

| CSS osztály | megnevezés |
| :--- | :--- |
| `bg-primary` | elsődleges háttérszín |
| `bg-secondary` | másodlagos háttérszín |
| `bg-success` | sikeres háttérszín |
| `bg-danger` | veszélyes háttérszín |
| `bg-warning` | figyelmeztető háttérszín |
| `bg-info` | információs háttérszín |
| `bg-light` | világos háttérszín |
| `bg-dark` | sötét háttérszín |
| `bg-white` | fehér háttérszín |
| `bg-transparent` | átlátszó háttérszín |

A háttérszínt beállító segéd osztályok nem állítják be a szövegszínt, ezt adott esetben külön meg kell tennünk.

{% tabs %}
{% tab title="HTML" %}
```markup
<div class="bg-primary text-white">.bg-primary</div>
<div class="bg-secondary text-white">.bg-secondary</div>
<div class="bg-success text-white">.bg-success</div>
<div class="bg-danger text-white">.bg-danger</div>
<div class="bg-warning text-dark">.bg-warning</div>
<div class="bg-info text-white">.bg-info</div>
<div class="bg-light text-dark">.bg-light</div>
<div class="bg-dark text-white">.bg-dark</div>
<div class="bg-white text-dark">.bg-white</div>
<div class="bg-transparent text-dark">.bg-transparent</div>
```
{% endtab %}

{% tab title="CSS" %}
```css
div {
	float: left;
	margin: 10px;
	padding: 10px;
	width: 150px;
	height: 150px;
}
```
{% endtab %}
{% endtabs %}

![](../.gitbook/assets/background-color.png)

## Térközök

## Keretek

Keretet adhatunk a HTML elemeknek a `border` osztállyal, ebben az esetben az elem mind a négy oldalán megjelenik a keret. Külön-külön oldalanként is megadhatjuk a keretet a `border-top`, `border-right`, `border-bottom`, és a `border-left` osztályokkal \(ezekből többet is megadhatunk egy elemnek\).

{% tabs %}
{% tab title="HTML" %}
```markup
<div class="border">.border</div>
<div class="border-top">.border-top</div>
<div class="border-right">.border-right</div>
<div class="border-bottom">.border-bottom</div>
<div class="border-left">.border-left</div>
```
{% endtab %}

{% tab title="CSS" %}
```css
div {
	width: 150px;
	height: 150px;
	float: left;
	margin: 10px;
	padding: 10px;
	background-color: #f9f9f9;
}
```
{% endtab %}
{% endtabs %}

![](../.gitbook/assets/border.png)

### Keret színek

Az elemek keretszíne a `border-` osztályokkal állítható az előre definiált színpaletta alapján:

| CSS osztály | megnevezés |
| :--- | :--- |
| `border-primary` | elsődleges keretszín |
| `border-secondary` | másodlagos keretszín |
| `border-success` | sikeres keretszín |
| `border-danger` | veszélyes keretszín |
| `border-warning` | figyelmeztető keretszín |
| `border-info` | információs keretszín |
| `border-light` | világos keretszín |
| `border-dark` | sötét keretszín |
| `border-white` | fehér keretszín |

{% tabs %}
{% tab title="HTML" %}
```markup
<div class="border border-primary">.border-primary</div>
<div class="border border-secondary">.border-secondary</div>
<div class="border border-success">.border-success</div>
<div class="border border-danger">.border-danger</div>
<div class="border border-warning">.border-warning</div>
<div class="border border-info">.border-info</div>
<div class="border border-light">.border-light</div>
<div class="border border-dark">.border-dark</div>
<div class="border border-white">.border-white</div>
```
{% endtab %}

{% tab title="CSS" %}
```css
div {
	width: 150px;
	height: 150px;
	float: left;
	margin: 10px;
	padding: 10px;
	background-color: #F5F5F5;
}
```
{% endtab %}
{% endtabs %}

![](../.gitbook/assets/border-color%20%281%29.png)

