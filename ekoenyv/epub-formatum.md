# ePub formátum

## Mi is az az ePub?

Az ePub egy ingyenes, nyílt forráskódú elektronikus könyv szabvány, ami a tartalmak optimális megjelenítését teszi lehetővé a legkülönfélébb olvasó eszközökön.

Az ePub szabvány az elterjedt webes technológiákra épül, az ezzel a szabvánnyal készült könyvek adatait XML dokumentumokban, a tartalmakat HTML-ben tárolja, a szöveg formázását padig CSS állományok biztosítják.

![](../.gitbook/assets/epub_logo_color.jpg)



## ePub dokumentum felépítése

Az ePub állomány egy tömörített dokumentum, ami zip tömörítést használ, bár a kiterjesztése .epub, ezeket az állományokat kitömöríthetjük, ha átnevezzük .zip kiterjesztésűre. Kitömörítve egy könyvtárstruktúrát láthatunk, ami további alkönyvtárakból és állományokból áll.

### mimetype állomány

Ez az állomány segít felismerni az ePub dokumentumot, az operációs rendszerek, és az olvasó programok ennek az állománynak a tartalma alapján azonosítják be az eKönyvet. Tartalma ennek megfelelően:

```text
application/epub+zip
```

Csak ezt az egy sort tartalmazhatja, szóköz és enter nélkül.

**mimetype** kötelezően a neve ennek az állománynak, és nincs kiterjesztése.

Minden más állományt és dokumentumot könyvtárakban helyezünk el, vagyis az ePub dokumentumunk gyökérkönyvtárában csak ez az egy állomány lehet, így szavatoljuk, hogy a különböző programok először ezt az állományt találják meg.

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

### **OPF állomány**

Ez az állomány tartalmazza az ePub dokumentum meta adatait. Formátuma igen kötött \(XML\), és a tartalma jellemzően kötelezően meghatározott elemekből áll.

```text
<?xml version="1.0" encoding="UTF-8"?>
<package xmlns="http://www.idpf.org/2007/opf" version="2.0" unique-identifier="BookId">
  <metadata xmlns:dc="http://purl.org/dc/elements/1.1/" xmlns:opf="http://www.idpf.org/2007/opf">
		<title>
			Első ePub könyvem
		</title>
		<creator opf:file-as="Gipsz Jakab" opf:role="aut">
			Gipsz Jakab
		</creator>
		<date>
			2021-03-06
		</date>
		<identifier id="BookId">
			1234567890
		</identifier>
		<language>
			hu
		</language>
		<meta content="cover" name="cover" />
	</metadata>
	<manifest>
    <item id="ncx" href="toc.ncx" media-type="application/x-dtbncx+xml"/>
    <item id="style" href="style.css" media-type="text/css"/>
		<item id="coverpage" href="coverpage.html" media-type="application/xhtml+xml"/>
    <item id="content1" href="content1.html" media-type="application/xhtml+xml"/>
		<item id="content2" href="content2.html" media-type="application/xhtml+xml"/>
    <item id="lobster" href="fonts/Lobster-Regular.ttf" media-type="application/vnd-ms-opentype"/>
		<item id="opensans" href="fonts/OpenSans-Regular.ttf" media-type="application/vnd-ms-opentype"/>
    <item id="coverimage" href="img/cover.png" media-type="image/png"/>
		<item id="kiskacsa" href="img/kiskacsa.png" media-type="image/png"/> 
  </manifest>
  <spine toc="ncx">
		<itemref idref="coverpage"/>
    <itemref idref="content1"/>
		<itemref idref="content2"/>
  </spine>
  <guide>
    <reference href="coverpage.html" type="cover" title="Ugrás a borítóhoz"/>
  </guide>
</package>
```

#### metadata szekció

Metadata szekcióban találhatóak a könyv adatai, például a könyv címe, szerzője, megjelenési dátuma, egyedi azonosítója, és a könyv nyelvének azonosítója.

Példa képpen a könyv címe így néz ki:

```text
  <title>
	  Első ePub könyvem
	</title>
```

#### manifest szekció

A manifest szekciónak tartalmaznia kell egy hivatkozást a könyv minden állományára \(a mimetype, a container és az OPF kivételével\). Ez a lista segít azonosítani és lokalizálni minden egyes szükséges állományt.

Az alábbi kódrészlet a jellemző állománytipusokhoz tartalmaz egy-egy példát:

```text
<manifest>
    <!-- Tartalomjegyzék állomány: -->
    <item id="ncx" href="toc.ncx" media-type="application/x-dtbncx+xml"/>
    
    <!-- CSS stílus állomány: -->
    <item id="style" href="style.css" media-type="text/css"/>
    
    <!-- HTML állomány: -->
    <item id="content1" href="content1.html" media-type="application/xhtml+xml"/>
    
    <!-- TTF betűtípus: -->
    <item id="opensans" href="fonts/OpenSans-Regular.ttf" media-type="application/vnd-ms-opentype"/>
    
    <!-- Kép: -->
    <item id="coverimage" href="img/cover.png" media-type="image/png"/>
<manifest>
```

Minden manifest hivatkozásnak tartalmaznia kell egy egyedi azonosítót \(`id`\), egy állomány elérési útvonalat \(`href`\) és egy típus tulajdonságot \(`media-tipe`\).  Két elem nem létezhet ugyanazzal az egyedi azonosítóval.

**spine szekció**

A spine egy lista, ami a tartalmi állományok, vagyis a könyv részeinek sorrendjét határozza meg, fel kell benne sorolnunk minden a könyv részeit tartalmazó HTML állományt. Az eKönyv olvasó programok e lista alapján mennek végig a fejezeteken.

Minden HTML dokumentum kap egy `idref` bejegyzést, ami a korábbi a manifest szekcióban meghatározott egyedi azonosítóra \(`id`\) hicatkozik:

```text
<spine toc="ncx">
		<itemref idref="coverpage"/>
    <itemref idref="content1"/>
		<itemref idref="content2"/>
</spine>
```

**guide szekció**

Ez a rész opcionális, el is lehet hagyni. 

\*\*\*\*

### **Tartalomjegyzék \(toc.ncx\)**

\*\*\*\*

**Stílus állományok \(CSS\)**

\*\*\*\*

**Tartalmi állományok \(HTML\)**

