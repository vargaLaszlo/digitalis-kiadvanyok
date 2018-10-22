# Mértékegységek

## Százalék

A legtöbb értéket megadhatjuk százalékban, hosszmértékként értelmezve ezt általában a szülő konténer mérete alapján számolja a böngésző.

```css
div {
    width: 60%;
    height: 60%;
    right: 20%;
    top: 20%;
}
```

## Képpont - pixel

Tekinthetjük alap mértékegységnek, egy képpontja a magjelenítő eszköznek. A böngészők minden egyéb hosszmértéket erre számítanak át. Ez eltérhet a nagyobb képpont sűrűségű eszközökön, például retina eszközön egy pixel egy 3\*3 képpontos négyzet.

```css
div {
    font-size: 18px;
    width: 350px;
    padding: 30px 25px;
}
```

## Tipográfiai mértékegységek

A tipográfiai mértékegységek jellemzően egy bizonyos betű magasságát veszik egy egységnek.

### **Em - M magasság**

A nagy **M** betű magassága alapján számolja a távolságokat. Ez a legelterjedtebb tipográfiai mértékegység. A szülőhöz képest állítja be a fontméretet, ha a szülőnek 2em a font mérete, a gyermeknek pedig 1em, a szülő és a gyermek számított font mérete megegyező lesz.

```text
p {
    font-size: 1em;
    line-height: 1.2em;
}
```

### **Rem - Relatív M magasság**

Az **em** párja, de ez nem öröklődik, a body fontmérete alapján számítja ki a böngésző.

```css
p {
    font-size: 1rem;
    line-height: 1.2rem;
}
```

### **Egyéb tipográfiai mértékegységek**

**Ex**

Az **ex** a kis x magassága alapján számolt egység, az **em** érték fele pixelben

#### ch

A **ch** a 0 karakter szélessége alapján számolt egység.

## Fizikai hosszmértékek

A méreteket megadhatjuk fizikai kiterjedés alapján, ez a HTML dokumentum nyomtatása estén használatos.

**cm** - centiméter  
**mm** - miliméter  
**in** - incs  
**pc** - nyomdai pica  
**pt** - nyomdai pont

## Képernyőméret

### **Képernyőmező szélesség - viewport width**

A **vw** egy egysége a képernyő szélességének századrésze. vagyis egy 100vw szélességű elem a képernyő teljes szélességét kitölti.

### **Képernyő magasság - viewport height**

A **vh** egy egysége a képernyő magasságának századrésze. vagyis egy 100vh magasságú elem a képernyő teljes szélességét kitölti.

### **Kisebb képernyő dimenzió - viewport min**

A **vmin** egy egysége a vh és a vw értéke közül a kisebbel lesz egyenlő.

### **Nagyobb képernyődimenzió - viewport max**

A **vmax** egy egysége a vh és a vw értéke közül a nagyobbal lesz egyenlő.

```css
.container1 {
    width: 55vw;
    height: 66vh;
}

.container2 {
    max-width: 99vmin;
    width: 20vmax;
}
```

## Idő

Animációk, átmenetek vagy hang időzítése esetén az időfaktor beállítására használhatjuk.

```css
transition: all 0.3s ease 0.1s;
```

## Szögek

Elemek forgatása esetén használatos mértékegységek:

**deg** - fok  
**grad** - újfok \(derékszög század része\)  
**rad** - radiáns  
**turn** - teljes fordulat \(360°\)

