# W3C Validator

## Mi az a W3C Validator?

A [**W3C Validator**](https://validator.w3.org/) a [W3C](https://www.w3.org/) nemzetközi szervezet \(World Wide Web Consortium\) jelölőnyelv ellenőrző eszköze. Ezzel az eszközzel lehet weboldalak vagy beküldött **HTML** állományok kódját ellenőrizni, hogy azok megfelelnek e a **HTML** szabványnak. A **HTML** mellett **XML** és **XHTML** dokumentumokat is lehet vele ellenőrizni.

A **W3C Validator** elérhetősége: [**https://validator.w3.org/**](https://validator.w3.org/)\*\*\*\*

![W3C Validator munka k&#xF6;zben](../.gitbook/assets/w3cvalidator00.png)

## W3C Validator használata

### Kód beküldése ellenőrzésre

![](../.gitbook/assets/validator01.png)

Három módon küldhetünk be HTML kódot ellenőrzésre, a nekünk megfelelő módot a [validator űrlapjának tetején](https://validator.w3.org/) a tabokon választhatjuk ki.

1. Megadhatunk egy URL-t vagy webcímet ellenőrzésre.
2. Feltölthetünk egy állományt a számítógépünkről, a feltöltött állományt fogja ellenőrizni a validator.
3. Copy/paste-el bevághatunk egy teljes, vagy részleges HTML állomány tartalmat ellenőrzésre.

![Webc&#xED;m ellen&#x151;rz&#xE9;s&#xE9;hez haszn&#xE1;ljuk az Address mez&#x151;t.](../.gitbook/assets/w3cvalidator04.png)

![&#xC1;llom&#xE1;ny felt&#xF6;lt&#xE9;shez v&#xE1;lasszunk ki egy HTML &#xE1;llom&#xE1;nyt a sz&#xE1;m&#xED;t&#xF3;g&#xE9;p&#xFC;nkr&#x151;l.](../.gitbook/assets/w3cvalidator02.png)

![K&#xF3;dr&#xE9;szlet ellen&#x151;rz&#xE9;shez Ctrl + C, Ctrl + V seg&#xED;ts&#xE9;g&#xE9;vel illeszthet&#x151; be a W3C Validatorba.](../.gitbook/assets/w3cvalidator03.png)

### További beállítások

![](../.gitbook/assets/w3cvalidator05.png)

A további beállítások a **More Options** menüből érhetőek el:

#### Karakter kódolás \(Character encoding\)

A validator alapbeállításnál megpróbálja felismerni a dokumentum karakter kódolását, de mi is beállíthatunk egy konkrét karakter kódolási táblát a legördülő menüből.

#### Dokumentum tipus \(Document Type\)

A !doctype meghatározás alapján próbálja meg értelmezni a dokumentumot a validator, ennek hiányában HTML 4.01 Transitional dokumentum típust fogja használni. A legördülő menüből mi is kiválaszthatjuk a megfelelő típust.

#### Hiba üzenetek csoportosítása

Két lehetőség van, az első esetben sorrendben jeleníti meg az üzeneteket, ahogy halad végig a dokumentumon a validator \(List Messages Sequentially\), a második eset, amikor kategóriánként csoportosítja a hiba üzeneteket \(Group Error Messages by Type\).

#### Forráskód mutatása \(Show Source\)

A validator mutatja a forráskódot, és kiemeli benne a hibás elemeket.

#### Forráskód tisztítása \(Clean up Markup with HTML-Tidy\)

A validátor a HTML-Tidy segítségével megkisérli javítani az esetleges hibákat.

#### Cím hierarchia mutatása \(Show Outline\)

Ebben az esetben kapunk egy visszajelzést a dokumentum cím szerkezetéről.

#### Bőbeszédű kimenet \(Verbose Output\)

Bizonyos esetekben részletesebb visszajelzést kapunk így a hibákról.

### Visszajelzések

Ha megvannak a kívánt beállítások, és a Check gombbal beküldtük az ellenőrizendő kódot, a validator összeállítja nekünk a jelentését.

![Szerencs&#xE9;s eset, nincs hiba.](../.gitbook/assets/w3cvalidator06.png)

![Szerencs&#xE9;tlen eset, a forr&#xE1;sk&#xF3;d tele van hib&#xE1;val.](../.gitbook/assets/w3cvalidator07.png)

#### Hibaüzenet felépítése

![](../.gitbook/assets/w3cvalidator08.png)

1. Hiba sorszáma
2. Hiba tipusa, hiba \(error\), vagy warning \(figyelmeztetés\)
3. Hiba konkrét leírása
4. Hiba helye a kódban \(line: sor, column: oszlop\)
5. A hibás kódszakasz kiemelve.



