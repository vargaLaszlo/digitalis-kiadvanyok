# Grid rendszer

A Bootstrap Grid rendszer egy rugalmas eszköz, amivel a különböző képernyő felbontásokon eltérő modulhálós megjelenést tudunk biztosítani a webalkalmazásainknak.

## Konténer - container

Bár az előző fejezetben taglalt konténer elem önmagában grid nélkül is alkalmazható, a grid rendszer használatához szükséges, ugyanis grid rendszer csak konténer elemben veszi fel az oldalsó eltartásokat, ennek hiányában a böngésző lap széléhez fognak érni az elemeink.

Konténer elemet a `container`, vagy `container-fluid` osztállyal tudunk létrehozni:

```markup
<div class="container">
  ...
</div>
```

## Sor - row

A sor elem fogja össze a modulháló oszlopait, benne rendeződnek beállításaiknak megfelelő szélességű cellákra.

Sor elemet a `row` osztállyal tudunk létrehozni, és jellemzően a sorokat közvetlenül konténer elemekben helyezzük el:

```markup
<div class="container">
    <div class="row">
        ...
    </div>
</div>
```

## Oszlop - column

A modulháló oszlopait a `col` osztállyal hozhatjuk létre, és közvetlenül egy sor elemben kell elhelyezni őket:

```markup
<div class="container">
    <div class="row">
        <div class="col">
            Első oszlop
        </div>
        <div class="col">
            Második oszlop
        </div>
        <div class="col">
            Harmadik oszlop
        </div>
    </div>
</div>
```

