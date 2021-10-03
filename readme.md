## Table of Content
1. [What is CSS](#what-is-css)
1. [How to CSS](#how-to-css)
    - Inline Style
    - Internal Style
    - External Style
1. [CSS Layouting In a Nutshell](#css-layouting-in-a-nutshell)
    - [Box Model](#box-model)
    - [Flex](#flex)
    - [Grid](#grid)
1. [CSS Preprocessors](#css-preprocessors)
    - [SASS](#sass)
1. [Additional](#additional)
1. [References](#references)

### What is CSS
CSS, merupakan kependekan dari *Cascading Style Sheets* adalah suatu "bahasa"  
yang mendeskripsikan bagaimana Elemen dari HTML akan ditampilkan pada layar,  
kertas, ataupun media lainnya.

CSS ini tanpa kita sadari, kita sering mengkonsumsinya dan apabila kita  
sebagai developer *mengerti* menggunakannya, akan mempermudah hidup, karena  
dapat mengontrol tampilan layout dari berbagai ukuran situs web dalam satu  
kali pembuatan css.

Mari sekarang kita mencoba untuk melihat cara penggunaan cssnya

### How to CSS
Cara untuk menggunakan css ini sebenarnya terbagi menjadi beberapa cara:
- Inline style
- Internal style
- External style

#### Inline Style
Inline style, adalah dimana kita menggunakan / mendefinisikan css di dalam  
tag HTML itu sendiri
```html
<body>
  <!-- Ada style di dalam tag h1, inilah inline style -->
  <h1 style="color: #666;">Ini adalah inline style</h1>
</body>
```

Terlihat pada kode di atas, kita mendefinisikan css di dalam tag h1 itu sendiri.

Ini disebut dengan `inline style`.

Selanjutnya kita akan melihat `internal style`

#### Internal Style
Internal style, adalah dimana kita mendefinisikan style di dalam file html   
itu sendiri

```html
<head>
  <!-- Ini adalah internal style -->
  <style>
    .internal-style-h1 {
      color: blueviolet;
    }
  </style>
</head>
<body>
  <!-- Perhatikan di sini kita menggunakan class yang ada pada style -->
  <!-- yang didefinisikan pada tag style di atas -->
  <h1 class="internal-style-h1">Ini adalah internal style</h1>
</body>
```

Terlihat pada kode di atas, kita menggunakan tag "style" di dalam head,  
kemudian kita mendefinikan style di dalam tag style itu sendiri.

Ini disebut dengan `internal style`

Selanjut kita akan melihat `external style`

#### External Style
External style, adalah dimana kita mendefinisikan style di luar file html itu  
sendiri.

```html
<!-- File: index.html -->
<head>
  <!-- Perhatikan di sini kita menggunakan sebuah file css terpisah -->
  <!-- File ini terletak di src/index.css -->

  <!-- Ini adalah external style -->
  <!-- Perhatikan peletakannya sebelum internal style -->
  <link rel="stylesheet" href="src/index.css">
</head>
<body>
  <!-- Perhatikan di sini kita menggunakan class yang ada pada -->
  <!-- file css external -->

  <!-- Perhatikan di sini kita menggunakan class yang ada pada -->
  <!-- file: public/index.css -->
  <h1 class="external-style-h1">Ini adalah external style</h1> 
</body>
```

```css
/* File: src/index.css */
.external-style-h1 {
  color: burlywood;
}
```

Terlihat bahwa pada kode di atas, kita menggunakan sebuah file css terpisah  
dari file html yang ada. 

Ini disebut dengan `external style`

Selanjutnya setelah mengenal tentang cara penulisan CSS kita akan belajar  
mengenai bagaimana melakukan layouting dengan CSS

### CSS Layouting in a Nutshell
Pada bagian ini kita akan mempelajari bagaimana cara melakukan layoting dengan  
CSS menggunakan `flex` dan `grid`.

Namun sebelum mempelajari itu, ada sedikit aturan css yang harus diketahui  
terlebih dahulu yah, khususnya mengenai `box model` pada CSS.

#### Box Model
Dalam CSS, sebenarnya apapun bentuknya, SELURUH hal / elemen yang dimunculkan  
oleh CSS bentuknya adalah sebuah `kotak` atau disebut dengan `box model`.

Cara kita mendeskripsikan ini adalah fondasi utama dari pembelajaran CSS itu  
sendiri !

Misalkan kita memiliki sebuah tag html sebagai berikut

```html
<p>Saya adalah sebuah paragraf yang hanya memiliki sebuah kalimat saja</p>
```

Kemudian kita akan membuat css untuk p nya adalah seperti ini
```css
p {
  width:100px;
  height: 50px;
  padding: 20px;
  border: 1px solid;
}
```

Maka, apabila kode ini dijalankan dan dilihat, konten (tulisannya) akan bablas  
ke bawah, mengapa demikian? karena pada tahap ini kita belum mengerti tentang  
`box model`, bagaimana `box model` ini dipengaruhi oleh aspek lainnya dalam  
CSS, dan bagaimana dalam mengontrol `box model` ini bisa membuat kita membuat  
CSS yang lebih bisa dipahami !

Lalu bagaimanakah cara kita menyelesaikan ini supaya border yang dibuat sesuai  
dengan konten yang ada saja?
```
hint: gunakan width dan height untuk set content yang flexible !
```

Pada pembelajaran ini kita tidak mendiskusikan bagaimana cara kita  
menyelesaikan solusi di atas, hanya saja, kita akan mempelajari area dalam  
box model ini ada apa saja.

![image01](assets/image01.png)

Semuanya dimulai dari `content box` yang ada di sini, dimana merupakan area  
dimana konten (isi dari tag html) itu berada, dan `content box` ini, SANGAT  
bisa mengontrol ukuran dari tag html orang tua dari tag html ini, jadi  
`content box` ini merupakan area dimana ukurannya PALING variatif.

`padding box` mengelilingi `content box` dan ini adalah ruang dimana property  
`padding` diterapkan. Karena `padding` ini adalam di dalam kotak, latar  
belakang dari kotak akan terlihat di dalam ruang yang dibuat ini.

`border box` akan mengelilingi `padding box` dan ruang ini akan tergantung  
dari nilai `border` yang dibuat. umumnya digunakan untuk memvisualisikan  
bingkai di dalam sebuah element.

area terakhir `margin box` adalah ruang keliling di seluruh kotak yang ada,  
didefinisikan berdasarkan aturan `margin` yang ada di kotak. Property css  
seperti `outline` ataupun `box-shadow` akan memengaruhi `margin box` ini.

Sepertinya ribet yah untuk memahami `box model` ini?

Jadi mari kita coba pelajari ini lebih lanjut dengan analogi berdasarkan  
gambar berikut:

![image02](assets/image02.png)

Berdasarkan gambar di atas, kita memiliki 3 foto berbingkai, yang di-*templok*  
pada tembok, dengan jarak satu sama lain.

Pada gambar ini terlihat bahwa:
- `content box` merupakan gambar seninya
- `padding box` merupakan ruang putih, antara bingkai dengan gambar seninya
- `border box` merupakan bingkai dari gambar seni tersebut
- `margin box` merupakan ruang jarak antar bingkai satu dengan yang lainnya
- `shadow` yang memiliki ruang yang sama dengan si `margin box` yang ada

Nah setelah kita mengetahui `box model` ini, barulah kita masuk ke materi  
utama kita, yaitu Layouting, dengan Flex dan Grid !

#### Flex
`Flexbox Layout` atau dikenal dengan Flex, merupakan mekanisme layout yang  
didesain untuk mengelompokkan sekumpulan barang di dalam wadah dengan bentuk  
satu dimensi yang sama, misalnya semua di sumbu yang sama (horizontal atau  
vertical), TANPA mengetahui ukuran yang ada a.k.a dinamis (sehingga dinamakan  
Flex / flexbible).



#### Grid

### CSS Preprocessors
#### SASS

### Additional
#### CSS Specificity

### References
- https://www.w3schools.com/css/css_intro.asp
- https://www.hostinger.com/tutorials/difference-between-inline-external-and-internal-css
- https://web.dev/learn/css/
- https://sass-lang.com/
- https://css-tricks.com/snippets/css/a-guide-to-flexbox/
- https://css-tricks.com/snippets/css/complete-guide-grid/