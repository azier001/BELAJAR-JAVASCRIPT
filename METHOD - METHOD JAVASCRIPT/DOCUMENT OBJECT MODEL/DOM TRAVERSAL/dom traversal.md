# Dokumentasi DOM Traversal

## Pengantar
Dokumen ini menjelaskan cara traversal (menelusuri) elemen-elemen dalam DOM menggunakan JavaScript. Traversal DOM sangat berguna untuk mengakses, memanipulasi, atau memahami struktur elemen dalam sebuah halaman web.

---

## Struktur HTML
Kode HTML berikut digunakan untuk percobaan traversal DOM:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Dom Traversal</title>
  </head>
  <body>
    <h1>Ini title</h1>
    <p>Ini text</p>

    <ul id="list-item">
      <li id="item1">item 1</li>
      <li id="item2">item 2</li>
      <li id="item3">item 3</li>
    </ul>

    <script src="script.js"></script>
  </body>
</html>
```

---

## Traversal DOM dengan JavaScript

Kode JavaScript berikut digunakan untuk melakukan traversal DOM:

```js
const item1 = document.getElementById('item1');
const item2 = document.getElementById('item2');
const listItem = document.getElementById('list-item');

// 1. Menelusuri Parent Node
console.log(item1.parentNode); // Output: <ul id="list-item">
console.log(item1.parentElement); // Output: <ul id="list-item">
```
**Perbedaan:**
- `parentNode`: Mengembalikan node induk dari elemen yang dipilih, termasuk teks atau node lainnya.
- `parentElement`: Sama seperti `parentNode`, tetapi hanya mengembalikan elemen sebagai induk.

---

```js
// 2. Menelusuri Child Node
console.log(listItem.childNodes);
// Output: NodeList(7) [ #text, li#item1, #text, li#item2, #text, li#item3, #text ]

console.log(listItem.children);
// Output: HTMLCollection { 0: li#item1, 1: li#item2, 2: li#item3, length: 3 }
```
**Perbedaan:**
- `childNodes`: Mengembalikan semua node anak, termasuk elemen, teks, atau komentar.
- `children`: Mengembalikan hanya elemen anak dalam bentuk HTMLCollection.

---

```js
// 3. Menelusuri Elemen Pertama dan Terakhir
console.log(listItem.firstChild); // Output: #text "\n      "
console.log(listItem.firstElementChild); // Output: <li id="item1">

console.log(listItem.lastChild); // Output: #text "\n      "
console.log(listItem.lastElementChild); // Output: <li id="item3">
```
**Perbedaan:**
- `firstChild` vs `firstElementChild`:
  - `firstChild` dapat mengembalikan teks atau elemen pertama dalam node induk.
  - `firstElementChild` hanya mengembalikan elemen pertama.
- `lastChild` vs `lastElementChild`:
  - `lastChild` dapat mengembalikan teks atau elemen terakhir dalam node induk.
  - `lastElementChild` hanya mengembalikan elemen terakhir.

---

```js
// 4. Menelusuri Saudara (Sibling)
console.log(item1.nextSibling); // Output: #text "\n      "
console.log(item1.nextElementSibling); // Output: <li id="item2">

console.log(item2.previousSibling); // Output: #text "\n      "
console.log(item2.previousElementSibling); // Output: <li id="item1">
```
**Perbedaan:**
- `nextSibling` vs `nextElementSibling`:
  - `nextSibling` mengembalikan node saudara berikutnya, bisa berupa teks atau elemen.
  - `nextElementSibling` hanya mengembalikan elemen saudara berikutnya.
- `previousSibling` vs `previousElementSibling`:
  - `previousSibling` mengembalikan node saudara sebelumnya, bisa berupa teks atau elemen.
  - `previousElementSibling` hanya mengembalikan elemen saudara sebelumnya.

---

## Kesimpulan
Traversal DOM sangat penting untuk mengakses dan memanipulasi elemen dalam sebuah halaman web. Berikut beberapa poin utama yang perlu diperhatikan:
1. `parentNode` dan `parentElement` digunakan untuk mendapatkan elemen induk.
2. `childNodes` mencakup teks dan elemen anak, sedangkan `children` hanya elemen anak.
3. `firstChild` dan `lastChild` bisa mengembalikan teks, gunakan `firstElementChild` dan `lastElementChild` untuk elemen.
4. `nextSibling` dan `previousSibling` bisa mengembalikan teks, gunakan `nextElementSibling` dan `previousElementSibling` untuk elemen.
5. Gunakan metode `Element` daripada `Node` jika hanya ingin mengakses elemen tanpa teks atau komentar.



