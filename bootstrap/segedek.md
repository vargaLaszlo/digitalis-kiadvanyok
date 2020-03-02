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

