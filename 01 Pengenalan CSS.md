## Objective
- [Apa itu CSS?](#apa-itu-css)
- [Inline, Internal dan Eksternal CSS](#inline-internal-dan-eksternal-css)
- [CSS Rule dan Selector](#css-rule-dan-selector)
- [CSS Comment](#css-comment)

## Apa itu CSS?
CSS kepanjangan dari Cascading Style Sheets.
- Cascading mengacu pada cara CSS menerapkan suatu style di atas yang lain (top-down). Elemen child akan mendapatkan karakteristik style dari elemen parent.
- Style Sheets mengontrol tampilan dari halaman web

CSS dan HTML
- HTML digunakan untuk struktur halaman web
- CSS menentukan tampilan atau style dari elemen HTML

CSS dapat digunakan untuk menerapkan spesifik style untuk spesifik elemen HTML. Manfaat utama dari CSS adalah dapat memisahkan style dari konten HTML.

Agar dapat mengerti CSS disarankan terlebih dahulu agar mempelajari pengetahuan dasar mengenai HTML di repository https://github.com/tedydarmawan/HTML

## Inline, Internal dan Eksternal CSS
Ada beberapa cara untuk menerapkan CSS dalam dokumen HTML yaitu: inline, internal dan eksternal

### Inline CSS
Inline style digunakan untuk menerapkan style pada single elemen HTML.
Untuk menerapakan inline style tambahkan atribut style pada suatu elemen atau tag HTML.
``` html
<p style="color:white; background-color:gray;">
  Contoh penerapan inline style
</p>
```

Output:

![alt text][inline_css]

### Internal CSS
Internal CSS didefinisikan pada tag <style> didalam bagian head dari halaman HTML.
``` html
<!DOCTYPE html>
<html>
  <head>
    <title>Halaman Pertama</title>
    <style>
      p{
        color: white;
        background-color: gray;
      }
    </style>
  </head>
  <body>
    <p>Contoh paragraf 1</p>
    <p>Contoh paragraf 2</p>
  </body>
</html>
```

Output:

![alt text][internal_css]

### Eksternal CSS
Dengan menggunakan eksternal CSS semua style pada dokumen HTML akan dipisahkan ke file terpisah .css. 

Untuk mereferensikan file CSS pada HTML dapat menggunakan tag `<link>`. Tag `<link>` dituliskan didalam bagian head dari halaman HTML.

#### index.html
``` html
<!DOCTYPE html>
<html>
  <head>
    <title>Halaman Pertama</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <p>Contoh paragraf 1</p>
    <p>Contoh paragraf 2</p>
  </body>
</html>
```

#### style.css
``` css
p{
  color: white;
  background-color: gray;
}
```

## CSS Rule dan Selector
sintaksis CSS terdiri dari tiga bagian yakni: selector, property dan value. 
Sintaksis tersebut akan diterjemahkan oleh browser dan diterapkan ke elemen-elemen HTML yang terkait.

Contoh sintaksis CSS
``` css
h1{
  color: orange;
}
```
- h1 = selector
- color = property
- orange = value

> Setiap blok CSS berisi satu atau lebih deklarasi style, dipisahkan menggunakan titik koma (;). Setiap deklarasi meliputi nama property dan valuenya.

Ada beberapa jenis selector yaitu:
1. Type Selector
2. id dan class Selector
3. Descendant Selector

### Type Selector
Selector yang paling umum dan mudah dipahami adalah type selector. Selector ini menggunakan elemen atau tag HTML sebagai target.
Contoh type selector pada tag `<p>`:
``` css
p{
  color: green;
  font-size: 120%;
}
```

### id dan class Selector
id selector meyediakan style pada elemen HTML dengan memanfaatkan atribut id sedangkan class selector menyediakan style pada elemen HTML dengan memanfaatkan atribut class.

Contoh selector dengan menggunakan id
#### HTML
``` html
<div id="intro">
  <p>Contoh paragraf 1</p>
</div>
<p>Contoh paragraf 2</p>
```

#### CSS
``` css
#intro{
  color: white;
  background-color: red;
}
```

Contoh selector dengan menggunakan class
#### HTML
``` html
<div class="intro">
  <p>Contoh paragraf 1</p>
</div>
<p>Contoh paragraf 2</p>
```

#### CSS
``` css
.intro{
  color: white;
  background-color: red;
}
```

Output id dan class selector:

![alt text][id_class_selector]

> Untuk memilih elemen dengan spesifik id, gunakan karakter hash (#) diikuti dengan nama dari id tersebut. Sedangkan untuk memilih elemen dengan spesifik class, gunakan karakter titik (.) diikuti dengan nama dari class tersebut.

### Descendant Selector
Descendant selector digunakan untuk memilih elemen yang merupakan turunan dari elemen yang lain.

Contoh memilih tag `<em>` sebagai target
#### HTML
``` html
<div id="intro">
  <p class="pertama">Contoh <em>paragraf</em> 1</p>
  <p>Contoh paragraf 2</p>
</div>
<p class="pertama">Contoh paragaf 3</p>
<p>Contoh paragraf 4</p>
```

#### CSS
``` css
#intro .pertama em{
  color: white;
  background-color: red;
}
```

Output:

![alt text][descendant_selector]

## CSS Comment
Comment digunakan untuk menjelaskan kode dan bermanfaat pada saat mengedit kode dimasa yang akan datang. Comment juga dapat diterapkan untuk single-line comment ataupun multi-line comment.
``` css
/* ini adalah komentar */
```

Contoh:
``` css
p{
  color: white;
  /* font-size: 150%; */
  background-color: red;
}
```

[inline_css]: https://scontent.fcgk9-1.fna.fbcdn.net/v/t1.0-9/18920408_10212793690467702_3353852526657708350_n.jpg?oh=032357b265669c03d87876dfade498cc&oe=59AFA3AD "Inline CSS"
[internal_css]: https://scontent.fcgk8-1.fna.fbcdn.net/v/t1.0-9/18839239_10212793732668757_2354856348339005560_n.jpg?oh=1bd5d6563cfa77f9522cc878dd8324cc&oe=59A25477 "Internal CSS"
[id_class_selector]: https://scontent.fcgk8-1.fna.fbcdn.net/v/t1.0-9/18893286_10212794201840486_3606640922863385699_n.jpg?oh=d4fa34ff2555fd506ba8bdeb4b304a2b&oe=59A1B914 "ID Class Selector"
[descendant_selector]: https://scontent.fcgk8-1.fna.fbcdn.net/v/t1.0-9/18881864_10212794201880487_2563473811610647690_n.jpg?oh=a63f051153f10da597dfecbb2cf5fa85&oe=59A0D8ED "Descendant Selector"

