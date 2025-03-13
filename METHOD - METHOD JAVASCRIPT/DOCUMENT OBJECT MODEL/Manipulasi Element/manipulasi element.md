# Manipulasi DOM - Mengubah Elemen HTML

## Mengubah Konten Elemen

### 1. Menggunakan `textContent`
```js
const paragraph = document.getElementById('paragraph');
paragraph.textContent = 'ini new paragraph';
```
> `textContent` hanya mengubah teks dalam elemen tanpa memproses HTML di dalamnya.

### 2. Menggunakan `innerHTML`
```js
paragraph.innerHTML = 'ini ubahan dengan innerHTML';
```
> `innerHTML` memungkinkan penggunaan tag HTML di dalam elemen.

### Perbedaan `textContent` dan `innerHTML`
```js
const container = document.getElementById('container');
console.log(container.innerHTML);
/*
  Output:
  <h1>Ini title</h1>
  <p>ini text</p>
*/

console.log(container.textContent);
/*
  Output:
  Ini title
  Ini text
*/
```

### Contoh Perubahan Elemen
```js
container.innerHTML = '<h1>Ini berubah menjadi content baru dengan tagname baru</h1>';
container.textContent = '<h1>Ini berubah menjadi content baru dengan tagname baru</h1>';
```
> `innerHTML` akan menampilkan `<h1>` sebagai elemen HTML, sedangkan `textContent` hanya menampilkan teks secara mentah.

---

## Mengubah Atribut Elemen

### Menggunakan `setAttribute()`
```js
paragraph.setAttribute('class', 'bg-red');
```
> `setAttribute(attribute, value)` digunakan untuk mengubah atau menambahkan atribut dalam bentuk string.

---

## Mengubah Gaya atau Style Elemen

### Menggunakan `style` pada elemen
```js
const li = document.querySelectorAll('li');
li[1].style.color = 'blue';
li[2].style.fontSize = '32px';
```
> Properti `style` memungkinkan perubahan langsung pada elemen HTML melalui JavaScript.

---

## Kesimpulan
- `textContent` digunakan untuk mengubah teks tanpa memproses HTML.
- `innerHTML` memungkinkan pemakaian elemen HTML dalam perubahan konten.
- `setAttribute()` digunakan untuk mengubah atribut elemen.
- Properti `style` digunakan untuk mengubah tampilan elemen secara langsung.



