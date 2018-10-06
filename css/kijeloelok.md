# Kijelölők

![](../.gitbook/assets/selector.png)

## Mire szolgál a CSS kijelölő?

A **kijelölők** segítenek kiválasztani azokat az elemeket, amelyekre bizonyos stílus szabályokat szeretnénk alkalmazni. Minden stílusnak tartalmaznia kell egy kijelölőt.

## Általános kijelölő

Az **általános kijelölő** az összes elemre általánosan vonatkozik.

```css
* {
    ...
}
```

## Elem kijelölő

Az **elem kijelölő** ez elemeket típusuk alapján azonosítja. Az alábbi példában a bekezdésekre \(p\) célzunk:

```markup
<p>Lorem ipsum dolor sit amet</p>
```

```css
p {
    ...
}
```

## Osztály kijelölő

Az **osztály kijelölő** az elemet az **class** \(osztály\) ****tulajdonsága alapján célozza be.

```markup
<p class="first-paragraph">Lorem ipsum dolor sit amet</p>
```

```css
.first-paragraph {
    ...
}
```

Ugyanazzal az osztállyal több elem is rendelkezhet, és egy elem rendelkezhet több osztállyal is. Így lehetőség van elemeinket rugalmasan csoportosítani.

## Azonosító kijelölő

Az **azonosító kijelölő** az elemet az **id** \(egyedi azonosító\) tulajdonsága alapján célozza be.

```markup
<p id="introduction">Lorem ipsum dolor sit amet</p>
```

```css
#introduction {
    ...
}
```

Egy HTML dokumentumban egy elem rendelkezhet egy adott egyedi azonosítóval, és ezt az elemet az azonosítókijelölővel tudjuk célozni.

## Leszármazott kijelölő

Ezzel a kijelölővel szülő elem alapján tudunk szűkíteni egy leszármazottra.

```markup
<section>
    <div>
        <p>Lorem ipsum dolor sit amet</p>
    </div>
</section>
```

```css
section p {
    ...
}
```

## Szomszédostestvér kijelölő

Ezzel a kijelölővel egy bizonyos elem után következő elemet célozhatunk meg.

```markup
<p>Lorem ipsum dolor sit amet</p>
<p>Dolor sit amet</p>
```

```css
p + p {
    ...
}
```

...

