# Egyedi megjelenés

A Bootstrap -nek módosíthatjuk a beállításait, így tudun egyedi megjelenést biztosítani a felhasználói felületeknek, a számos lehetőség közül például használhatunk egyedi színeket, betűtípust, vagy módosíthatjuk a moduljháló oszlopainak a számát.

## Stílus forrásállományok fordítása

Ahhoz hogy érvényesíteni tudjuk a beállításainkat, a Bootstrap stílusait az [SCSS](https://sass-lang.com/)  forrás állományaiból kell fordítanunk, ezt rendeszerint egy fejlesztői keretrendszerrel végezzük, de lehetőség van erre a Visual Studio Code-ban is egy bővítmény segítségével. Ehhez töltsük le a _Live Sass Compiler_ bővítményt:

{% embed url="https://marketplace.visualstudio.com/items?itemName=ritwickdey.live-sass" %}

Telepítéshez nyissuk meg a Visual Studio Code bővítmény kezelőjét \(Extensions\), és a keresőbe írjuk be a bővítmény nevét \(_Live Sass Compiler_ \).

![](../.gitbook/assets/vsc-extensions.png)

A találati listában a bővítmény neve mellett nyomjuk meg az `Install` gombot. Telepítés után a következő elem jelenik meg a Visual Studio Code láblécén:

![](../.gitbook/assets/sass-watch.png)

Erre a gombra kattintva a Visual Studio Code le fogja fordítani CSS állományra az SCSS forrás állományokat.

## Bootstrap forrás állományok bekötése

A forrás állományokat a Bootstrap letöltés oldalán találjuk:

{% embed url="https://getbootstrap.com/docs/4.4/getting-started/download/" %}

Kattintsunk a _Download Source_ gombra:

![](../.gitbook/assets/download-source.png)

Egy tömörített zip állomány fog letöltődni tömörítsük ki. Csak az `scss` almappára és teljes tartalmára van szükségünk, ezt helyezzük el a HTML állomány mellett, amiben alkalmazni akarjuk:

![](../.gitbook/assets/vsc.png)

Hozzunk létre egy **style.scss** nevű állományt, amibe behívjuk a Bootstrap forrását \(az `scss` mappában található bootstrap.scss állományt kell hivatkozni\):

{% code title="style.scss" %}
```css
@import 'scss/bootstrap.scss';
```
{% endcode %}

Ha elmentettük az állományt, és megnyomjuk a _Watch Sass_ gombot, a Visual Studio Code legyártja a CSS állományunkat:

![](../.gitbook/assets/vsc-sass.png)

Végül be kell kötnünk a HTML állományba a legyártott CSS állományt, egy szokásos link segítségével:

```markup
<link rel="stylesheet" href="style.css">
```

Ha mindent jól csináltunk, és megnyitjuk az állományunkat egy böngészőben, a Bootstrap komponensei megkapják az alapértelmezett Bootstrap stílusokat. A  gomb elem például a következő képpen fog kinézni:

```markup
<a class="btn btn-primary" href="#" role="button">Gomb</a>
```

![](../.gitbook/assets/button.png)

## Egyedi beállítások alkalmazása

A Bootstrap beállításait az `scss` mappában a **\_variables.scss** állományban találjuk, ezt direkt módon sose módosítsuk, fölül tudjuk írni a beállításait a saját SCSS állományunkban, a `@import` előtt. Például megváltoztathatjuk az elsődleges \(primary\) színt:

{% code title="style.scss" %}
```css
$primary: red !default;

@import './scss/bootstrap.scss';
```
{% endcode %}

Fordítás után ez megváltoztatja többek között a gombunk színét is:

![](../.gitbook/assets/button-red.png)

Minden beállítás változókban van tárolva ezek mindíg `$` jellel kezdődnek az SCSS-ben, az új érték után el kell helyezni egy `!default` kapcsolót ez felülírja a később bekötött Bootstrap beállítás értékét. 

### Példák további beállításokra

#### Alapértelmezett betűtípus felülírása 

Ebben a példában egy Google betűkészlettel írjuk felül az alapértelmezett fontot:

{% tabs %}
{% tab title="CSS" %}
{% code title="style.scss" %}
```css
$font-family-base: 'Open Sans', sans-serif !default;

@import './scss/bootstrap.scss';
```
{% endcode %}
{% endtab %}

{% tab title="HTML" %}
```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bootstrap - Open Sans</title>
    <link
        href="https://fonts.googleapis.com/css?family=Open+Sans&display=swap"
        rel="stylesheet">
    <link rel="stylesheet" href="style.css">
</head>
<body>
  <a class="btn btn-primary m-5" href="#" role="button">Gomb</a>
</body>
</html>
```
{% endtab %}
{% endtabs %}

Ahhoz, hogy a font betöltődjön be kell kötni a HTML állományba.

#### Modulháló beállításainak módosítása

A következő példában a Bootstrap modulháló oszlopainak a számát 12-ről 16-ra módosítjuk, az oszlopok közötti csatornák \(gutter\) szélességét 30 pixelről 20 pixelre csökkentjük:

```css
$grid-columns:                16 !default;
$grid-gutter-width:           20px !default;

@import './scss/bootstrap.scss';
```

## Példa állományok

Az alábbi linken a példa HTML és SCSS állományok letölthetőek:

{% file src="../.gitbook/assets/bootstrap-scss.zip" %}

