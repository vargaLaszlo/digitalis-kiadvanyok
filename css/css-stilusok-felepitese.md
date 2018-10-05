# CSS stílusok felépítése

## CSS elhelyezése HTML állományokban

### Szövegközi stílusok \(inline style\)

A CSS stílusokat egy HTML elem **style** tulajdonságában elhelyezve csak arra az egy elemre fognak vonatkozni.

```markup
<p style="color: blue; font-size: 1.5em;">Lorem ipsum dolor sit amet</p>

<input id="form-helper" type="text" style="display: none;">
```

### Beágyazott stíluslapok

A **CSS** stylusokat elhelyezhetjük egy **HTML** állomány fejlécében egy **style** elemben.  
A **style** elemben **CSS** nyelvi szabályok lesznek érvényesek.

```markup
<style>
    p {
        font-size: 1.5em;
    }
    
    p.blue {
        color: blue;
    }
</style>
```

### Külső stíluslapok

A **CSS definícióinkat** elhelyezhetünk **CSS** állományokban, ezeket az állományokat link elemmel kapcsolhatjuk a **HTML** állományunkba.

```markup
<link rel="stylesheet" type="text/css" href="style.css">
```

A külső CSS állomány kiterjesztése **.css** lehet.

{% hint style="info" %}
A külső CSS állomány nagy előnye, hogy több HTML oldalba is be lehet kötni ugyan azt a CSS állományt, így csökken a letöltendő adatmennyiség, és a stílusokat egy központi helyen tudjuk kezelni.
{% endhint %}

### CSS importálása

Egy CSS állományba behívhatunk egy másik CSS állományt **@import** segítségével.

```css
@import url('style.css');
```

