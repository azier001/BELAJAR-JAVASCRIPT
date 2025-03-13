# DOM Access pada JavaScript

Dokumentasi ini menjelaskan secara detail mengenai cara mengakses dan memanipulasi DOM (Document Object Model) menggunakan JavaScript.

## 1. Pengenalan DOM

DOM (Document Object Model) adalah representasi struktur dokumen HTML dalam bentuk pohon yang memungkinkan kita untuk mengakses dan memanipulasi elemen-elemen di dalamnya secara dinamis.

## 2. Metode Akses Elemen DOM

### 2.1. `getElementById()`
Digunakan untuk mengambil elemen berdasarkan atribut `id`. Mengembalikan elemen tunggal (`HTMLElement`).

```html
<div id="content">Hello, World!</div>
```
```javascript
const contentDiv = document.getElementById("content");
console.log(contentDiv.innerText); 
// Output: Hello, World!
```

### 2.2. `getElementsByClassName()`
Mengambil semua elemen dengan kelas tertentu. Mengembalikan `HTMLCollection` yang bersifat live (berubah jika DOM berubah).

```html
<div class="item">Item 1</div>
<div class="item">Item 2</div>
```
```javascript
const items = document.getElementsByClassName("item");
console.log(items); 
// Output: HTMLCollection(2) [div.item, div.item]

for (let i = 0; i < items.length; i++) {
    console.log(items[i].innerText);
}
// Output:
// Item 1
// Item 2
```

### 2.3. `getElementsByTagName()`
Mengambil semua elemen berdasarkan nama tag. Mengembalikan `HTMLCollection`.

```html
<p>Paragraf pertama.</p>
<p>Paragraf kedua.</p>
```
```javascript
const paragraphs = document.getElementsByTagName("p");
console.log(paragraphs);
// Output: HTMLCollection(2) [p, p]

for (let i = 0; i < paragraphs.length; i++) {
    console.log(paragraphs[i].innerText);
}
// Output:
// Paragraf pertama.
// Paragraf kedua.
```

### 2.4. `querySelector()` dan `querySelectorAll()`
Menggunakan selector CSS untuk memilih elemen.

- `querySelector()` mengembalikan elemen pertama yang cocok (`HTMLElement`).
- `querySelectorAll()` mengembalikan `NodeList` yang bisa di-loop dengan `forEach()`.

```html
<div class="container">
  <p class="text">Paragraf pertama</p>
  <p class="text">Paragraf kedua</p>
</div>
```
```javascript
const firstParagraph = document.querySelector(".container .text");
console.log(firstParagraph.innerText);
// Output: Paragraf pertama

const allParagraphs = document.querySelectorAll(".container .text");
console.log(allParagraphs);
// Output: NodeList(2) [p.text, p.text]

allParagraphs.forEach(p => console.log(p.innerText));
// Output:
// Paragraf pertama
// Paragraf kedua
```

## 3. Manipulasi DOM

### 3.1. Mengubah Konten

```html
<h1 id="title">Judul Lama</h1>
```
```javascript
const title = document.getElementById("title");
title.innerText = "Judul Baru";
console.log(title.innerText);
// Output: Judul Baru
```

### 3.2. Menambahkan Elemen

```javascript
const newDiv = document.createElement("div");
newDiv.innerText = "Elemen Baru";
document.body.appendChild(newDiv);
console.log(newDiv);
// Output: <div>Elemen Baru</div>
```

### 3.3. Menghapus Elemen

```html
<div id="removeMe">Hapus saya</div>
```
```javascript
const element = document.getElementById("removeMe");
if (element) {
    element.parentNode.removeChild(element);
    console.log("Elemen telah dihapus");
}
// Output: Elemen telah dihapus
```

## 4. Event Handling

```html
<button id="myButton">Klik Saya!</button>
```
```javascript
const button = document.getElementById("myButton");
button.addEventListener("click", function() {
    alert("Button diklik!");
    console.log("Button diklik!");
});
```

## 5. Kesimpulan

- DOM Access memungkinkan kita mengubah struktur dan konten halaman web.
- Gunakan metode yang sesuai seperti `getElementById`, `querySelector`, dan lainnya.
- Event handling digunakan untuk membuat interaksi pengguna lebih dinamis.
- `getElementsByClassName()` dan `getElementsByTagName()` mengembalikan `HTMLCollection`, sedangkan `querySelectorAll()` mengembalikan `NodeList`.
- Gunakan `const` atau `let` daripada `var` untuk deklarasi variabel yang lebih aman.

