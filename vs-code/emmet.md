# Emmet

## Mi az az Emmet?

Az **Emmet** egy automatikus kódkiegészítő, ami megkönnyíti a munkát **HTML** és **CSS** dokumentumokkal, úgy hogy drasztikusan csökkenti a gépelés mennyiségét \(és a gépelési hibákat\). 

Számos fejlesztői eszközbe alapértelmezetten be van integrálva, köztük a **VS Code** szövegszerkesztőbe, és a **Codepen.io** online szövegszerkesztőbe is.

Az **Emmet**[ **rövidítéseket**](https://docs.emmet.io/abbreviations/syntax/) \(abbreviation\) használ, amiket begépelve komplex HTML struktúrákat kapunk vissza.

Például ha VS Code-ban megnyitunk egy HTML dokumentumot, és új sorban leütjük a p betűt, és entert nyomunk egy HTML bekezdést kapunk:

```markup
<p></p>
```

## Emmet példák

### html:5 vagy !

Az alapvető HTML elemeket tehetjük be vele egy üres dokumentumba.  
Eredménye: 

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>

</body>
</html>
```

### h1

Egy üres főcím.  
Eredménye:

```markup
<h1></h1>
```

### h1&gt;lorem3

Főcím 3 töltelékszóval.  
Eredménye:

```markup
<h1>Lorem, ipsum dolor.</h1>
```

{% hint style="info" %}
A **&gt;** jel a jel előtt lévő elembe beleteszi a jel után következő elemet.  
Például ennél a rövidítésnél: **div&gt;p** a szövegszerkesztő létrehoz egy div elemet, és elhelyez benne egy bekezdést.
{% endhint %}

{% hint style="info" %}
A **lorem** rövidítés egy bekezdésnyi töltelékszöveget hoz létre. Meghatározhatjuk hogy hány szóból álljon a töltelékszöveg, ehhez írjuk a **lorem** kulcsszó után közvetlenül a létrehozni kívánt szavak számát: **lorem15** ez a rövidítés egy 15 szóból álló töltelékszöveget hoz létre.
{% endhint %}

### p

Egy üres bekezdést hoz létre.  
Eredménye:

```markup
<p></p>
```

### p&gt;lorem

Egy bekezdést hoz létre egy bekezdésnyi töltelékszöveggel.  
Eredménye:

```markup
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. 
Officiis, eos? Iste deleniti cum ullam explicabo deserunt 
eius at fugiat, itaque rem? Consequuntur molestiae enim sequi
provident molestias inventore praesentium odio?</p>
```

### p{Tarka kutya tarka felfelé kucsorodó farka!}

Egy bekezdést hoz létre konkrét szöveges tartalommal.  
Eredménye:

```markup
<p>Tarka kutya tarka felfelé kucsorodó farka!</p>
```

### \(p&gt;lorem\)\*3

3 bekezdés töltelékszöveggel.  
Eredménye:

```markup
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. 
Voluptatem ducimus similique architecto numquam eum, sunt 
error quasi quas deserunt et. Neque dolorem, veritatis 
suscipit cum magni magnam veniam ducimus facilis!</p>
<p>Earum consequuntur tempora non incidunt voluptatem sit 
quibusdam recusandae facilis? At, tenetur odit fugiat error
vero perspiciatis assumenda praesentium dolores perferendis
nostrum ut expedita officia quidem quae labore repellat
voluptates?</p>
<p>Voluptates voluptate architecto, qui quas saepe cumque 
reiciendis alias cupiditate et! Sint unde nisi dolorem 
voluptates id laudantium perspiciatis reprehenderit, vitae 
atque architecto amet, eos eligendi veniam, facere autem 
nesciunt!</p>
```

{% hint style="info" %}
A **\*** jellel sokszorozni tudunk, például a **p\*5** rövidítés 5 üres bekezdést hoz létre.  
Ha több egymásba ágyazott elemet akarunk sokszorozni, például 5 üres bekezdés helyett 5 bekezdést töltelékszöveggel, a sokszorozni kívánt elemeket tegyük zárójelbe: **\(p&gt;lorem\)\*5**
{% endhint %}

### h1+h2+p

Egy üres főcím, utána üres alcím, végül egy üres bekezdés  
Eredménye:

```markup
<h1></h1>
<h2></h2>
<p></p>
```

{% hint style="info" %}
A + jellel egymás után tudunk elhelyezni elemeket, például a **div+div** két div-et hoz létre. Ezzel a módszerrel egy oldal fő strukturális elemeit egy menetben létre tudjuk hozni: **header+main+aside+footer**
{% endhint %}

### \(h1&gt;lorem1\)+\(\(h2&gt;lorem3\)+p&gt;lorem\)\*2

Egy főcím, utána két alcím egy-egy bekezdéssel. Mindegyik elemben megfelelő mennyiségű töltelékszöveg.  
Eredménye:

```markup
<h1>Lorem.</h1>
<h2>Lorem, ipsum dolor.</h2>
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. 
A cupiditate atque assumenda vel iusto. Veritatis, excepturi 
temporibus aut facilis itaque, expedita dolor voluptate porro 
harum iure quasi odio quibusdam. Repudiandae?</p>
<h2>Laboriosam, earum expedita.</h2>
<p>Voluptas dolores eos excepturi explicabo porro maxime 
distinctio et hic similique.Iure voluptas, deleniti asperiores
porro quibusdam aliquam fugit voluptatibus quia officiis
consectetur atque ad alias saepe, veritatis beatae. Amet.</p>
```

### ul&gt;li

Egy lista egy üres lista elemmel  
Eredménye:

```markup
<ul>
    <li></li>
</ul>
```

### ul&gt;li\*3

Egy lista három üres lista elemmel  
Eredménye:

```markup
<ul>    
    <li></li>
    <li></li>
    <li></li>
</ul>
```

### ul&gt;\(li&gt;lorem3\)\*6

Egy lista 6 lista elemmel, mindegyik lista elemben három töltelék szóval.  
Eredménye:

```markup
<ul>
    <li>Lorem, ipsum dolor.</li>
    <li>Saepe, ea unde!</li>
    <li>Quasi, ipsum rerum?</li>
    <li>Odio, est dignissimos.</li>
    <li>Natus, quaerat velit.</li>
    <li>Pariatur, in! Perferendis!</li>
</ul>
```

### nav&gt;ul&gt;\(li&gt;a&gt;lorem3\)\*5

Navigáció listátával, 5 darab lista elemmel, a list elemekben linkekkel.  
Eredménye:

```markup
<nav>
    <ul>
        <li><a href="">Lorem, ipsum dolor.</a></li>
        <li><a href="">Esse, soluta numquam!</a></li>
        <li><a href="">Ullam, eligendi impedit!</a></li>
        <li><a href="">Quod, tempora iusto.</a></li>
        <li><a href="">Quas, at in!</a></li>
    </ul>
</nav>
```

