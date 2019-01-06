# Pozícionálás

## Dokumentumfolyam

A _dokumentumfolyam_ az elemek sorozata, ennek a sorozatnak a sorrendje alapján rajzolja ki a böngésző a HTML elemeket.

A pozicionálás az elemek a böngésző által, a dokumentumfolyam alapján meghatározott eredeti helyét módosítja.

## Statikus pozició \(static\)

Ez az alapállapot, ebben az estben az elem _statikus_, _nem_ változik a pozíciója \(nincs pozicionálva\).

```css
div {
    position: static;
}
```

## Eltolás

A nem statikus helyzetű elemek helyzetét tudjuk módosítani a következő tulajdonságokkal:

* _left_ - eltolás balról
* _right_ - eltolás jobbról
* _top_ - eltolás fentről
* _bottom_ - eltolás lentről

Az eltolás alapértéke _auto_ ez nem befolyásolja az elem helyzetét. Megadhatjuk hosszmértékben, vagy százalékban. Százalékos érték esetén a szülőkonténer mérete érvényesül. Felvehet negatív értéket is.

```css
top: 33px;      /* Felső eltolás */
right: 55%;     /* Bal eltolás */
bottom: -5em;   /* Alsó eltolás */
left: 9px;      /* Bal eltolás */
```

## Viszonylagos pozició \(relative\)

Viszonylagos pozicionálás esetén az elem eredeti helyéhez képest eltolódik a megadott mértékben.

Az elem eredeti helye megmarad a dokumentum- folyamban, az utána következő elemeket eltolja, ugyanúgy, mintha statikus helyzetű lenne.  


