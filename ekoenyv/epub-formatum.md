# ePub formátum

## Mi is az az ePub?

Az ePub egy ingyenes, nyílt forráskódú elektronikus könyv szabvány, ami a tartalmak optimális megjelenítését teszi lehetővé a legkülönfélébb olvasó eszközökön.

Az ePub szabvány az elterjedt webes technológiákra épül, a könyv adatait XML dokumentumokban, a tartalmakat HTML-ben tárolja, a szöveg formázását padig CSS állományok biztosítják.

![](../.gitbook/assets/epub_logo_color.jpg)



## ePub dokumentum felépítése

Az ePub állomány egy tömörített dokumentum, ami zip tömörítést használ, bár a kiterjesztése .epub, ezeket az állományokat kitömöríthetjük, ha átnevezzük .zip kiterjesztésűre. 

### mimetype állomány

Ez az állomány segít felismerni az ePub dokumentumot, az operációs rendszerek, és az olvasó programok ennek az állománynak a tartalma alapján azonosítják az ePubhoz hasonló formátumú állományokat. Tartalma ennek megfelelően:

```text
application/epub+zip
```

Csak ezt az egy sort tartalmazhatja \(szóköz enter nélkül\).

**mimetype** kötelezően a neve ennek az állománynak, és nincs kiterjesztése.

Minden más állományt és dokumentumot könyvtárakban helyezünk el, vagyis az ePub dokumentumunk gyökérkönyvtárában csak ez az egy állomány lehet.

### container.xml állomány

Az ePub kompatibilis olvasók először ezt az állományt keresik, ebben kell feltüntetni a dokumentum meta  adatait tartalmazó állomány pontos helyét \(rootfile\).

```text
<?xml version="1.0"?>
<container version="1.0" xmlns="urn:oasis:names:tc:opendocument:xmlns:container">
  <rootfiles>
    <rootfile full-path="content/content.opf" media-type="application/oebps-package+xml" />
  </rootfiles>
</container>
```

**OPF állomány**

Ez az állomány tartalmazza az ePub dokumentum meta adatait.

...

