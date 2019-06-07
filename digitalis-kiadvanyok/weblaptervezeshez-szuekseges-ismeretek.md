# Weblaptervezéshez szükséges ismeretek

## Alapfogalmak

A **HTML** \(**H**yper**T**ext **M**arkup **L**anguage\) a weboldal alapja, olyan, mint egy ház alapja, csupasz falai, teteje.

{% page-ref page="../html/bevezetes-a-html-be.md" %}

 A **CSS** \(**C**ascading **S**tyle **S**heets\) felel a weboldal kinézetéért, olyan, mint a ház színe, dekorációja, bútorzata.

{% page-ref page="../css/mi-a-css.md" %}

A **JavaScript** programozási nyelv felel az oldalak működésért, olyan mint egy ház gépészete, elektromos rendszere \(ha itt megnyomok egy kapcsolót, amott felgyúl a villany\).

## Grafikai szoftverek

Az [Adobe](https://www.adobe.com/) termékei de facto iparági szabványként működnek, a webes grafikusok jelentős része [Adobe Photoshop](https://www.adobe.com/hu/products/photoshop.html)-ot használ, és [PSD](https://en.wikipedia.org/wiki/Adobe_Photoshop#File_format) formátumú állományokkal látja el a fejlesztőket.

Photoshop mellett az [Adobe Illustrator](https://www.adobe.com/hu/products/illustrator.html), és a [Fireworks](https://www.adobe.com/hu/products/fireworks.html) is népszerű. Az Adobe termékek nyílt forráskódú alternatívája a [Gimp](https://www.gimp.org/) ingyenes képszerkesztő, és az [Inkscape](http://www.inkscape.org/) vektorgrafikus szerkesztő.

Animációs területen az Adobe Flash elvesztette a piaci monopóliumát, az Adobe beszüntette a platform támogatását, ezt a piaci rést a HTML5-ös animált bannerek töltik be, ezek szerkesztésére jött létre az ingyenes [Google Web Designer](https://webdesigner.withgoogle.com/).

![Google Web Designer fel&#xFC;lete](../.gitbook/assets/google-web-designer.png)

## Szövegszerkesztők

A grafikai munkákon túl a fejlesztők szövegszerkesztőt \(Text editor\), és integrált fejlesztői környezetet \(Integrated Development Environment azaz IDE\) használnak, ezek a programok fel vannak ruházva a forráskódok irását, szerkesztését segítő funkciókkal, úgy mint intelligens kód kiegészítés \([Emmet](https://emmet.io/), [Intelli Sense](https://code.visualstudio.com/docs/editor/intellisense)\), kód színezés, hibakiemelés, stb. Számos ingyenes és fizetős program létezik, a teljesség igénye nélkül: [Visual Studio Code](https://code.visualstudio.com/), [Atom](https://atom.io/), [Notepad++](https://notepad-plus-plus.org/download/v6.9.2.html), [Brackets](http://brackets.io/), [Sublime Text](s://www.sublimetext.com), [Adobe Dreamweaver](https://www.adobe.com/hu/products/dreamweaver.html)...

{% page-ref page="../vs-code/mi-a-vs-code.md" %}

## Drótváz

A **drótváz** készítés egy módszer, amely segítségével kialakíthatjuk egy weboldal felépítését. A drótvázat elsősorban olyan weboldalak tartalmának és funkcionalitásának meghatározására használjuk, melyek figyelembe veszik a felhasználói igényeket és a felhasználói viselkedést. A drótvázakat a fejlesztési folyamat korai szakaszában használjuk az oldal alapvető struktúrájának kialakítása alatt, még a vizuális és szöveges tartalom kialakítása előtt.A drótváz kiváló eszköz arra, hogy költséges fejlesztés nélkül megismerjük az ügyfél igényeit, a fejlesztők pontos képet kapjanak az elkészítendő alkalmazás működéséről, ezen felül teret ad a kisérletezésnek, segítségével alacsony költségen kipróbálhatóak a projektekkel kapcsolatos ötletek.

A drótváz készülhet kézi rajzzal papíron, táblán, de vannak speciálisan erre a célra készült szoftverek, mint példáula a [Scetch](https://www.sketch.com/), vagy az [Adobe XD](https://www.adobe.com/hu/products/xd.html), egy jó ingyenes nyílt forráskódú alternatíva a [Pencil Projekt](https://pencil.evolus.vn/). Jellemző még ezen a területen az [Adobe Illustrator](https://www.adobe.com/hu/products/illustrator.html) használata.

![C&#xE9;lprogrammal k&#xE9;sz&#xFC;lt dr&#xF3;tv&#xE1;z.](../.gitbook/assets/wireframe.jpeg)

![Webalkalmaz&#xE1;s mobilos dr&#xF3;tv&#xE1;za k&#xE9;zi rajzzal.](../.gitbook/assets/wireframe2.jpeg)

![A Pencil dr&#xF3;tv&#xE1;z szerkeszt&#x151; fel&#xFC;lete egy egyszer&#x171; dr&#xF3;tv&#xE1;zzal.](../.gitbook/assets/wireframe-pencile.png)

A **prototípus** a következő lépés a drótváz után, ez már kattintható, bár a funkcionalitás csak mímelt \(angol kifejezéssel mock, magyarosítva mokkolt\). Jellemzően  HTML, és CSS segítségével készül, erre a feladatra kiválóan alkalmas a [Bootstrap](https://getbootstrap.com/) keretrendszer is, ezzel gyorsan és hatékonyan lehet felületeket kialakítani. Egyes drótváz készítő programokból lehet kattintható prototípust előállítani.

![Bootstrap-ben k&#xE9;sz&#xFC;lt protot&#xED;pus.](../.gitbook/assets/wireframe-bootstrap.png)

Bővebbebb cikk a témáról: [Using wireframes to streamline your development process](https://www.webdesignerdepot.com/2009/07/using-wireframes-to-streamline-your-development-process/)

## Grid rendszerek, vagy modulháló

...

