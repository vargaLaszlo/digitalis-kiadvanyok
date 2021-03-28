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

Ez a rész opcionális, el is lehet hagyni, a segítségével az eKönyv olvasó program saját menüjében tudunk ugrópontokat létrehozni.

Az alábbi példában a borítóhoz biztosítunk egy ugrópontot a felhasználó számára:

```text
<guide>
    <reference href="coverpage.html" type="cover" title="Ugrás a borítóhoz"/>
</guide>
```

### **Tartalomjegyzék \(toc.ncx\)**

Kiterjesztése \(.ncx\) ellenére ez is egy XML dokumentum. Az eKönyv olvasó programok ennek az állománynak a tartalma alapján építik fel a könyv tartalomjegyzékét. 

```text
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE ncx PUBLIC "-//NISO//DTD ncx 2005-1//EN" "http://www.daisy.org/z3986/2005/ncx-2005-1.dtd">
<ncx xmlns="http://www.daisy.org/z3986/2005/ncx/" xml:lang="hu" version="2005-1">
    <head>
        <meta name="dtb:uid" content="1234567890 "/>
        <meta name="dtb:depth" content="1"/>
        <meta name="dtb:totalPageCount" content="0"/>
        <meta name="dtb:maxPageNumber" content="0"/>
    </head>
    <docTitle>
        <text>Első ePub könyvem</text>
    </docTitle>
    <navMap>
        <navPoint id="navpoint-1" playOrder="1">
            <navLabel>
                <text>Borító</text>
            </navLabel>
            <content src="coverpage.html"/>
        </navPoint>
        <navPoint id="navpoint-2" playOrder="2">
            <navLabel>
                <text>Első fejezet</text>
            </navLabel>
            <content src="content1.html"/>
        </navPoint>
        <navPoint id="navpoint-3" playOrder="3">
            <navLabel>
                <text>Második fejezet</text>
            </navLabel>
            <content src="content2.html"/>
        </navPoint>
    </navMap>
</ncx>
```

#### **A tartalomjegyzék állomány** 

#### **Fejléc szekció \(head\)**

A fejléc a tartalomjegyzék mélységét, illetve az oldalak számát tartalmazza \(ez lehet nulla\).

```text
 <head>
        <!-- Könyv egyedi azonosítója (ugyanaz mont az OPF-ben) -->
        <meta name="dtb:uid" content="1234567890 "/>
        
        <!-- Tartalomjegyzék mélysége -->
        <meta name="dtb:depth" content="1"/>
        
        <!-- Lapozó és oldalszám beállítás (lehet 0) -->
        <meta name="dtb:totalPageCount" content="0"/>
        <meta name="dtb:maxPageNumber" content="0"/>
 </head>
```

#### **Könyv címe \(docTitle\)**

Kötelező megadni, az olvasó program ezt tünteti fel a tartalomjegyzékben.

```text
<docTitle>
    <text>Első ePub könyvem</text>
</docTitle>

```

#### **Navigációs térkép \(navMap\)**

A navigációs térkép segíti a felhasználót, ugrópontokat ad a fejezetekhez:

```text
<navMap>
        <navPoint id="navpoint-1" playOrder="1">
            <navLabel>
                <text>Borító</text>
            </navLabel>
            <content src="coverpage.html"/>
        </navPoint>
        <navPoint id="navpoint-2" playOrder="2">
            <navLabel>
                <text>Első fejezet</text>
            </navLabel>
            <content src="content1.html"/>
        </navPoint>
        <navPoint id="navpoint-3" playOrder="3">
            <navLabel>
                <text>Második fejezet</text>
            </navLabel>
            <content src="content2.html"/>
        </navPoint>
</navMap>
```

Minden bekezdésnek, vagy hivatkozott szövegrészletnek létre lehet hozni egy navigációs pontot \(`navPoint`\). Minden egyes navigációs pont tartalmaz egy egyedi azonosítót \(nem lehet két pontnak ugyanaz az azonosítója\), egy sorrend számozást \(`playOrder`\), ez alapján megy végig az eKönyvolvasó a navigációs pontokon. Tartalmaz egy felirator \(`navLabel`\), ez lesz a tartalomjegyzékben a navigációs pont címkéje, vagy felirata, végül egy hivatkozást, ami lehetegy HTML állomány, vagy egy elem is a HTML állományon belül \(`id` azonosító alapján\) erre hivatkozik az adott navigációs pont.

### **Tartalmi állományok \(HTML\)**

**Az ePub könyvekben a tartalom HTML dokumentumokban található, ezk a mostanság megszokott HTML 5-ös verziótól némileg eltérő, annál szigorúbb XHTML  1.1 szabvány szerint készülnek.**

```text
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="hu">
<head>
    <meta http-equiv="Content-Type" content="application/xhtml+xml; charset=utf-8"/>
    <link rel="stylesheet" type="text/css" href="style.css"/>
    <title>Első fejezet</title>
</head>
<body>
    <h1>Első eKönyvem első fejezete</h1>
    <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Hic fugit sint et tempora accusantium odit vel eius itaque, quasi maxime, laborum repellat natus laboriosam omnis sit eligendi unde blanditiis libero!</p>
</body>
</html>
```

{% hint style="warning" %}
Az XHTML szigorúbb, minden elemnek kötelező a záró elemét kitenni, illetve azok az elemek, amiknek nincs záró eleme \(`hr`, `br`, `img`, ...\) kötelezően egy / jellel kell végződjenek:  
&lt;hr /&gt;  &lt;br /&gt; &lt;img src="..." alt="..." /&gt;
{% endhint %}

A HTML-től eltérően kell egy XML deklaráció az első sorba, illetve az utána következő doctype is eltér a HTML 5 -ben megszokottól:

```text
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
```

A tratalmi rész, vagyis a HTML dokumentum törzse viszont a megszokott módon épül fel, elhelyezhetünk benne szöveges vagy képi elemeket.

### **Stílus állományok \(CSS\)**

```text
/* Font beállítások */
@font-face {
    font-family: 'Open Sans';
    src: url('fonts/OpenSans-Regular.ttf') format('truetype');
    font-weight: normal;
}

@font-face {
    font-family: 'Lobster';
    src: url('fonts/Lobster-Regular.ttf') format('truetype');
    font-weight: normal;
}

body {
    font-family: 'Open Sans';
    font-size: 1em;
}

h1,
h2,
h3,
h4,
h5,
h6 {
    font-family: 'Lobster';
    font-weight: 400;
}

h1 {
    text-align: center;
    font-size: 4em;
}

h2 {
    font-size: 3em;
}

h3 {
    font-size: 2.3em;
}

h4 {
    font-size: 1.7em;
}

/* Kép beállítások */

p img {
    width: 33.333%;
    float: left;
    margin-top: 0.285em;
    margin-bottom: 1em;
    margin-right: 1em;
}

/* Borító oldal beállításai */

#cover {
    margin: 0;
}

#cover img {
    display: block;
    height: 100vh;
    width: 100vw;
    object-fit: contain;
}

/* Oldal margó beállításai */

@page {
    margin: 5em;
}
```

### **Képek**

...

