# Rangsor

## Mi az a rangsor?

Egy elemre jellemzően több CSS szabály is vonatkozhat, ezek közül több is felülbírálhatja egymást, a böngészők rangsorolással döntik el, hogy mely szabály lesz érvényes az adott elemre.

## Eredet

Három forrásból származhat stílus:  
A böngésző alapértelmezett készlete, a felhasználó által definiált, és a webalkalmazás saját CSS-e, ez utóbbi felülbírálja a többit.

![](../.gitbook/assets/rangsor.png)

## Sorrend

A korábbi szabályokat  felülírják a későbbiek. Minél később van egy stílus, annál erősebb. Ez az állományok bekötési sorrendjére is érvényes.

```css
div {
    color: red;
    color: blue; /* a későbbi érvényesül */
}

span {
    color: green;
}

span {
    color: purple; /* a későbbi érvényesül */
}
```

## Szűkítés

4 szinten hoz létre minden szabály kiválasztója alapján a böngésző egy rangsort, a magasabb értékkel rendelkező szabály fog érvényesülni, felülbírálva a sorrendet. A szűkítés értékét a kijelölő alapján határozza meg a böngésző.

| Kijelölő típusa | Súlyozás értéke |
| :--- | :--- |
| Szövegközi stílusok | **1.0.0.0** |
| Egyedi azonosító | **0.1.0.0** |
| Osztály, álosztály | **0.0.1.0** |
| Elemazonosító | **0.0.0.1** |
| Általános kijelölő | **0.0.0.0** |

A szűkítés értékei összeadódnak, és a kapott érték alapján a rangsorolja a böngésző a CSS szabályokat. Ezek nem helyi értékek, egy darab id a kijelölőben bármennyi osztályt felülbírál.

```css
div                    /* értéke: 0.0.0.1 */
label.name             /* értéke: 0.0.1.1 */
.name                  /* értéke: 0.0.1.0 */
#contact               /* értéke: 0.1.0.0 */
div#contact            /* értéke: 0.1.0.1 */
div#contact .name      /* értéke: 0.1.1.1 */
div#contact label.name /* értéke: 0.1.2.1 */
```

## Fontosság \(!important\)

**!important** jelöléssel ellátott szabály mindíg erősebb a nem important szabálynál, két important közözött a további rangsorolási szabályok érvényesülnek. Az fontosság felülbírálja az eredetet, a sorrendet, és a szűkítést is.

```css
div {
    color: red !important;
}
```

