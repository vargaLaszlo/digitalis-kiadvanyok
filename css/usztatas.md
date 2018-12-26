# Úsztatás

## Úsztatás \(float\)

Az úsztatott elemek a tartalmazó konténerük felső sarkába igyekeznek, az úsztatás irányában. Az előttük lévő tartalom alá úsznak be, az utánuk következő tartalom pedig körülfolyja őket.

Az úsztatott elemek nem hoznak létre sortörést, és nem tolják szét a tartalmazó konténerüket.

Ha nincs közöttük nem úsztatott elem vízszintesen egy vonalba rendeződnek az úsztatás  
irányának megfelelően.

```css
.img-left {
    float: left;
}

.img-right {
    float: right;
}
```

![A sz&#xF6;vegben az els&#x151; sorban egy balra &#xFA;sztatott k&#xE9;p, a bekezd&#xE9;s k&#xF6;zep&#xE9;n egy jobbra &#xFA;sztatott n l&#xE1;that&#xF3;.](../.gitbook/assets/float.png)

## Úsztatás törése \(clear\)

A `clear` értékkel rendelkező elem mellé nem kerülhet úsztatott elem \(abban az esetben sem, ha maga úsztatott elem\). Beállíthatjuk, hogy csak az elem bal, vagy jobb oldalán `left`, `right`,  
vagy mindkét oldalán `both` akadályozza az úsztatott elemeket. Alapérték a `none`, vagyis nincs.

```css
div {
   clear: none;
}

span {
    clear: left;
}
```

