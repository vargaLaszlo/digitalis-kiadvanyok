# Középre rendezés

## Vízszintes középre rendezés külső margóval.

A következő technikával [blokkos megjelenítésű](../css/doboz-modell.md#toembszeru-vagy-blokkos-elemek-jellemzoi) elemeket lehet a szülő elemükben középre rendezni. A vízszintes középre rendezéshez `auto` értéket kell beállítani a jobb és bal oldali [`margin`](../css/doboz-modell.md#kuelso-margo-margin) \(külső margó\) tulajdonságnak. 

```text
div {
    margin-left: auto;
    margin-right: auto;
}
```

![](../.gitbook/assets/center-margin-auto.png)

Az elem [szélességét](../css/doboz-modell.md#tartalom-content) is szükséges megadni, ez lehet relatív szélesség \(százalék, vagy viewport\), vagy fix érték például pixel \(ha nincs megadva szélesség az elem teljesen kitölti a szülő elemet\).

{% code-tabs %}
{% code-tabs-item title="center.html" %}
```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Center block element</title>
    <link rel="stylesheet" href="center.css">
</head>
<body>
    <main>
        <div></div>
    </main>
</body>
</html>
```
{% endcode-tabs-item %}

{% code-tabs-item title="center.css" %}
```css
main {
	padding: 30px 0;
	background-color: #ffec99;
}

div {
	margin-left: auto;
	margin-right: auto;
	
	width: 200px;
	height: 200px;
	background-color: #f03e3e;
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Ez a technika csak [blokkos elemekkel](../css/doboz-modell.md#toembszeru-vagy-blokkos-elemek-jellemzoi) működik, `display: inline` \(szövegközi\) elemekre hatástalan \(nincs külső margójuk\).

A technika úsztatott elemek esetében nem működik.

{% embed url="https://codepen.io/\_lacus/pen/LXrGEK" %}

