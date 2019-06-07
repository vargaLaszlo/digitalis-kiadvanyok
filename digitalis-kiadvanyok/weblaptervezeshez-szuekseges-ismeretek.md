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

![A Visual Studio Code sz&#xF6;vegszerkeszt&#x151;](../.gitbook/assets/vscode.png)

{% page-ref page="../vs-code/mi-a-vs-code.md" %}

## Drótváz

A **drótváz** készítés egy módszer, amely segítségével kialakíthatjuk egy weboldal felépítését. A drótvázat elsősorban olyan weboldalak tartalmának és funkcionalitásának meghatározására használjuk, melyek figyelembe veszik a felhasználói igényeket és a felhasználói viselkedést. A drótvázakat a fejlesztési folyamat korai szakaszában használjuk az oldal alapvető kialakítása előtt, megelőzi a tényleges online grafikai tervezést, és a \(szöveges\) tartalmak kialakítását. A drótváz kiváló eszköz arra, hogy költséges fejlesztés nélkül megismerjük az ügyfél igényeit, a fejlesztők pontos képet kapjanak az elkészítendő alkalmazás működéséről, ezen felül teret ad a kisérletezésnek, segítségével alacsony költségen kipróbálhatóak a projektekkel kapcsolatos ötletek.

A drótváz készülhet kézi rajzzal papíron, táblán, de vannak speciálisan erre a célra szolgáló szoftverek, mint példáula a [Scetch](https://www.sketch.com/), vagy az [Adobe XD](https://www.adobe.com/hu/products/xd.html), egy jó ingyenes nyílt forráskódú alternatíva a [Pencil Projekt](https://pencil.evolus.vn/). Jellemző még ezen a területen az [Adobe Illustrator](https://www.adobe.com/hu/products/illustrator.html) használata.

![C&#xE9;lprogrammal k&#xE9;sz&#xFC;lt dr&#xF3;tv&#xE1;z.](../.gitbook/assets/wireframe.jpeg)

![Webalkalmaz&#xE1;s mobilos dr&#xF3;tv&#xE1;za k&#xE9;zi rajzzal.](../.gitbook/assets/wireframe2.jpeg)

![A Pencil dr&#xF3;tv&#xE1;z szerkeszt&#x151; fel&#xFC;lete egy egyszer&#x171; dr&#xF3;tv&#xE1;zzal.](../.gitbook/assets/wireframe-pencile.png)

A **prototípus** a következő lépés a drótváz után, ez már kattintható, bár a funkcionalitás csak mímelt \(angol kifejezéssel mock, magyarosítva mokkolt\). Jellemzően  HTML, és CSS segítségével készül, erre a feladatra kiválóan alkalmas a [Bootstrap](https://getbootstrap.com/) keretrendszer is, ezzel gyorsan és hatékonyan lehet felületeket kialakítani. Egyes drótváz készítő programokból lehet kattintható prototípust előállítani.

![Bootstrap-ban k&#xE9;sz&#xFC;lt protot&#xED;pus.](../.gitbook/assets/wireframe-bootstrap.png)

Bővebbebb cikk a témáról: [Using wireframes to streamline your development process](https://www.webdesignerdepot.com/2009/07/using-wireframes-to-streamline-your-development-process/)

## Grid rendszerek, vagy modulháló

A **grid**, vagy **modulháló** a tervezés legalapabb alapja, nem újkeletű dolog \(többszáz éve használja a nyomtatott grafika\), de új értelmet nyert a reszponzív webdizájnban, ahol fix szélességek helyett dinamikusan alkamazkodó arányokat célszerű használni.

### A modulháló \(grid system\) részei

#### Sorok \(row\)

![A grid rendszerek a tartalmakat k&#xFC;l&#xF6;n&#xE1;ll&#xF3; sorokba tagolj&#xE1;k.](../.gitbook/assets/grid-row.png)

#### Oszlopok \(column\)

![A sorok tov&#xE1;bb tagolhat&#xF3;ak oszlopokra.](../.gitbook/assets/grid-column.png)

#### Csatornák \(Gutter vagy Gap\)

![A sorok &#xE9;s oszlopok k&#xF6;z&#xF6;tt a h&#xE9;zagot a csatorn&#xE1;k alkotj&#xE1;k.](../.gitbook/assets/grid-gap.png)

#### Margók

![A k&#xFC;ls&#x151; eltart&#xE1;st a marg&#xF3;k szab&#xE1;lyozz&#xE1;k.](../.gitbook/assets/grid-container.png)

#### Régiók/területek

![A r&#xE9;gi&#xF3;k t&#xF6;bb egym&#xE1;s melletti oszlopot &#xF6;lelhetnek fel.](../.gitbook/assets/grid-region%20%281%29.png)

#### Modulháló használata

![A weboldal r&#xE9;szegys&#xE9;gei r&#xE9;gi&#xF3;kba tagolva.](../.gitbook/assets/grid-use.png)

Weboldalunkhoz nem kell megírni külön a grid rendszert, számos kész rendszer a rendelkezésünkre áll: [960 Grid System](https://960.gs/), [csswizardry-grids](https://csswizardry.com/csswizardry-grids/), [Neat Grid](https://neat.bourbon.io/docs/latest/)

Grid rendszert készen beépítve megtaláljuk a jelentősebb CSS/HTML keretrendszerekben: [Bootstrap - Grid System](https://getbootstrap.com/docs/4.0/layout/grid/), [Zurb Foundation - The Grid](https://foundation.zurb.com/grid.html)

A [Bootstrap Grid System](https://getbootstrap.com/docs/4.0/layout/grid/) érdekessége, hogy a Bootstrp egyép funkciói nélkül is beépíthetjük, és használhatjuk.

![Bootstrap Grid System-el k&#xE9;sz&#xFC;lt fel&#xFC;let.](../.gitbook/assets/bs-grid-system.png)

![A fenti Boodstrap Grid System fel&#xFC;let a 12-es oszlop kiemel&#xE9;s&#xE9;vel.](../.gitbook/assets/bs-grid-system-h.png)

