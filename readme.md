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


### CSS Layouting in a Nutshell
#### Box Model
#### Flex
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