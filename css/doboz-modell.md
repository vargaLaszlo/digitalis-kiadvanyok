# Doboz modell

## Tömbszerű \(vagy blokkos\) elemek jellemzői

A **blokkos** elemek kitöltik, a rendelkezésre álló helyet, mellettük más elem nem lehet \(az elem maga előtt és után töri a sort\). Magasságuk a tartalmuktól függ, a tartalom tolja szét a **blokkos** elemeket függőlegesen.

A böngészők blokkos elemként jelenítik meg az ebbe a kategóriába tartozó  
HTML elemeket.

CSS-el fel lehet ruházni ezzel a megjelenítési móddal  a nem blokkos elemeket is.

```css
span {
    display: block;
}
```

## Tartalom - content

Tartalmuknak megadhatjuk a szélességét, magasságát. Alapestben a böngésző határozza meg ezt az értéket \(kezdő értéke _auto_\).

```css
div {
    width: 60%; /* szélesség */
    height: 640px; /* magasság */
}
```

A szélességnek, és a magasságnak megadhatunk minimum és maximum értéket is. \(Kezdőértéke _none\)_

```css
div {
    min-width: 15%;     /* legkissebb szélesség */
    min-height: 15em;   /* legkisebb magasság */
    max-width: 125px;   /* legnagyobb szélesség */
    max-height: 55%;    /* legnagyobb magasság */
}
```

## Belső margó - padding

A blokkos elemeknek meg lehet adni belső margót, ez felveszi a háttér színét, és belső eltartása hozzáadódik a tartalom szélességéhez és magasságához. \(Kezdőértéke nincs\)

```css
div {
    padding-top: 10px;     /* Felső padding */
    padding-right: 10px;   /* Jobb padding */
    padding-bottom: 10px;  /* Alsó padqding */
    padding-left: 10px;    /* Bal padding */
    padding: 10px 5px 3px 1px;   /* Gyorsírásos padding */
}
```

## Keret - border

A blokkos elemeknek lehet kerete, a keret megjelenik vizuálisan, és hozzáadódik az elem magasságához és szélességéhez. Ha a keretnek vannak átlátszó részei az elem háttere látszódik ezeken a területeken.

### **Keret stílus**

A keret stílussal határozhatjuk meg a keret vizuális megjelenését. \(Kezdő értéke a none, vagyis nincs keret\)

**none, hidden** - nincs keret  
__**solid** - folytonos vonal  
**dotted** - pontozott  
**dashed** - szaggatott vonal  
**double** - dupla vonal  
**outset** - kiemelkedő  
**inset** - süllyesztett  
**groove** - bemélyített  
**ridge** - kidomborodó

```css
div {
    border-top-style: none;      /* Felső keret stílus */ 
    border-right-style: so lid;  /* Jobb keret stílus */
    border-bottom-style: dotted; /* Alsó keret stílus */
    border-left-style: dashed;   /* Bal keret stílus */
    border-style: solid none;    /* Gyorsírásos keret stílus */
}
```

### **Keret szélesség**

A keret szélesség tulajdonságnak az értéke adja a keret vastagságát. Negatív értéket nem vehet fel. Kezdő értéke _medium_, vagyis közepes.

```css
div {
    border-top-width: 1px;     /* Felső keret szélesség */
    border-right-width: 1em;   /* jobb keret szélesség */
    border-bottom-width: 5px;  /* Alsó keret szélesség */
    border-left-width: 1.2rem; /* Bal keret szélesség */
    border-width: 1px 2px 3px 4px;   /* Gyorsírásos keret szélesség */
}
```

### **Keret szín**

A keret színét határozza meg. Értéke lehet bármely CSS színrendszer beni szín. Alapértéke felveszi a szövegszínt \(color\).

```css
div {
    border-top-color: transparent;        /* Felső keret szín */
    border-right-color: red;              /* Jobb keret szín */
    border-bottom-color: rgb(65, 65, 89); /* Alsó keret szín */
    border-left-color: #448383;           /* Bal keret szín */
    border-color: #444;             /* Gyorsírásos keret szín */
}
```

### **Gyorsírásos keret**

```css
div {
    border-top: 5px solid black;       /* Gyorsírásos felső keret */
    border-right: none;                /* Gyorsírásos jobb keret */
    border-bottom: 3px double #449b44; /* Gyorsírásos alsó keret */
    border-left: 1px dashed red;       /* Gyorsírásos bal keret */
    border: 1px solid purple;          /* Gyorsírásos keret */
}
```

## Külső margó - margin

A külső margó az elemek közötti eltartást határozza meg. Értéke lehet negatív, ebben az esetben egymásra csúsznak az elemek.

```css
div {
    margin-top: 1.25em;     /* Felső margó */
    mergin-right: auto;     /* Jobb margó */
    margin-bottomm: 33px;   /* Alsó margó */
    margin-left: -25px;     /* Bal margó */
    margin: 0 auto 15px auto;   /* Gyorsírásos margó */
}
```

## Doboz méretezése - ****box-sizing

A box-sizing tulajdonság alapján számolja a böngésző az elemek méretét.

Két lehetséges értéke lehet, az alapérték a **content-box** ebben az estben az elem tartalmának szélességéhez, magasságához **hozzáadódik** a belső margó és a keret szélessége, magassága.  
  
A második lehetséges érték a **content-box**, amikor a szélességbe, és magasságba **beleszámít** a belső margó és a keret szélessége, magassága.

```css
div {
    box-sizing: content-box;
}

div {
    box-sizing: border-box;
}
```

## Ábra

![](../.gitbook/assets/box-modell.png)

