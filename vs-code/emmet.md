# Emmet

## Mi az az emmet?

...

## Emmet használata

...

## Emmet példák

### !

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

### P

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

### \(h1&gt;lorem1\)+\(\(h2&gt;lorem3\)+p&gt;lorem\)\*2

Egy főcím, utána két alcím egy-egy bekezdéssel.  
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

  


