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

### Automatikus oszlopméretezés \(auto layout\)

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

A `col` osztállyal létrehozott oszlopok sorba rendeződnek, egyenlő arányban töltik ki a rendelkezésre álló helyet:

![](../.gitbook/assets/3xcol.png)

A következő példában különböző számú oszlopokat tartalmazó sorokat hasonlíthatunk:

```markup
<div class="container">
    <!-- Egy oszlopos sor -->
    <div class="row">
        <div class="col">1</div>
    </div>
    
    <!-- Két oszlopos sor -->
    <div class="row">
        <div class="col">1</div>
        <div class="col">2</div>
    </div>
    
    <!-- Öt oszlopos sor -->
		<div class="row">
        <div class="col">1</div>
        <div class="col">2</div>
        <div class="col">3</div>
        <div class="col">4</div>
        <div class="col">5</div>
    </div>
</div>
```

![](../.gitbook/assets/rows.png)

### Rögzített oszlop méretek

A Grid rendszerben lehetőség van egy 12 oszlopos modulhálónak megfeleltetni az oszlopokat szélességben, ezt a `col-x` osztályokkal tehetjük meg, ahol az x helyére az elfoglalt oszlopok száma kerül. Ez alapján a `col-1` egy oszlop széles, ez a legkisebb oszlop méret, a `col-12` pedig a legnagyobb oszlopméret, ami a teljes rendelkezésre álló helyet kitölti.  Például ha 3 egyforma széles oszlopot szeretnénk egymás mellett megjeleníteni mindegyiken a `col-4` osztályt kell alkalmaznunk \(12/3=4\):

```markup
<div class="container">
		<div class="row">
				<div class="col-4">col-4</div>
				<div class="col-4">col-4</div>
				<div class="col-4">col-4</div>
		</div>
</div>
```

![](../.gitbook/assets/col-4.png)

Egy soron belül az oszlop méreteket kombinálhatjuk:

```markup
<div class="container">
	<div class="row">
		<div class="col-6">col-6</div>
		<div class="col-4">col-4</div>
		<div class="col-2">col-2</div>
	</div>
</div>
```

![](../.gitbook/assets/cols.png)

