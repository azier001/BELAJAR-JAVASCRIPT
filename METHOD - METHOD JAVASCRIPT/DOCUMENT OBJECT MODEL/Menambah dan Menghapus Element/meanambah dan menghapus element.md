# Dokumentasi: Menambah dan Menghapus Elemen di DOM

## Deskripsi
Kode ini menjelaskan bagaimana cara menambahkan dan menghapus elemen dalam DOM (Document Object Model) menggunakan JavaScript.

---

## **Menambah Elemen**

### **1. Membuat dan Menambahkan Elemen Baru ke dalam Body**

#### **Kode HTML**
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Menambah Elemen</title>
  </head>
  <body>
    <h1 id="title">DOM Menambah Elemen</h1>
  </body>
</html>
```

#### **Kode JavaScript**
```js
// Membuat elemen div baru
const newDiv = document.createElement('div');
newDiv.textContent = 'Ini div dibuat dari script';

// Menambahkan newDiv ke dalam body
document.body.appendChild(newDiv);

console.log(newDiv); // Output: <div>Ini div dibuat dari script</div>
```

📌 **Penjelasan Method:**
- `document.createElement('div')` → Membuat elemen `<div>` baru secara dinamis.
- `textContent` → Mengisi teks dalam elemen yang baru dibuat.
- `appendChild(newDiv)` → Menambahkan elemen sebagai anak dari elemen induknya (dalam hal ini `body`).

---

### **2. Menyisipkan Elemen Sebelum Elemen Lain**

#### **Kode JavaScript**
```js
// Mengambil elemen title
const title = document.getElementById('title');
console.log(title); // Output: <h1 id="title">DOM Menambah Elemen</h1>

// Menyisipkan newDiv sebelum elemen title
document.body.insertBefore(newDiv, title);
```

📌 **Penjelasan Method:**
- `document.getElementById('title')` → Mengambil elemen dengan `id` tertentu dari DOM.
- `insertBefore(newDiv, title)` → Menyisipkan elemen `newDiv` sebelum `title` dalam `body`.

---

### **3. Menambahkan Elemen Baru ke dalam List**

#### **Kode HTML**
```html
<ul id="list">
  <li>Item 1</li>
  <li id="item2">Item 2</li>
  <li>Item 3</li>
</ul>
```

#### **Kode JavaScript**
```js
// Membuat elemen li baru
const newLi = document.createElement('li');
newLi.textContent = 'Ini adalah li baru';

// Mengambil elemen list dan item2
const list = document.getElementById('list');
console.log(list); // Output: <ul id="list">...</ul>
const itemDua = document.getElementById('item2');
console.log(itemDua); // Output: <li id="item2">Item 2</li>

// Menyisipkan elemen li baru sebelum item2
list.insertBefore(newLi, itemDua);
```

📌 **Penjelasan Method:**
- `createElement('li')` → Membuat elemen `<li>` baru.
- `insertBefore(newLi, itemDua)` → Menyisipkan elemen baru sebelum elemen `item2` dalam list.

---

## **Menghapus Elemen**

### **1. Menghapus Elemen Secara Langsung**

#### **Kode JavaScript**
```js
// Mengambil elemen title
const title = document.getElementById('title');

// Menghapus elemen title
title.remove();
console.log(title); // Output: null (elemen telah dihapus)
```

📌 **Penjelasan Method:**
- `remove()` → Menghapus elemen yang dipilih langsung dari DOM.

---

### **2. Menghapus Elemen Anak dari Elemen Induk**

#### **Kode JavaScript**
```js
// Mengambil elemen list dan item2
const list = document.getElementById('list');
const itemDua = document.getElementById('item2');

// Menghapus item2 dari list
list.removeChild(itemDua);
console.log(list); // Output: <ul id="list">Item 1, Item 3</ul>
```

📌 **Penjelasan Method:**
- `removeChild(itemDua)` → Menghapus elemen anak (`itemDua`) dari elemen induknya (`list`).

---

## **Kesimpulan**
Kode ini membantu memahami cara menambah dan menghapus elemen DOM dengan JavaScript secara terpisah dengan contoh yang lebih jelas dan hasil keluaran (`console.log`).

### **Ringkasan Method yang Digunakan:**
| Method | Fungsi |
|--------|--------|
| `document.createElement(tagName)` | Membuat elemen HTML baru. |
| `textContent` | Menambahkan teks ke dalam elemen. |
| `appendChild(node)` | Menambahkan elemen sebagai anak dari elemen lain. |
| `insertBefore(newNode, existingNode)` | Menyisipkan elemen sebelum elemen tertentu. |
| `getElementById(id)` | Mengambil elemen berdasarkan `id` tertentu. |
| `remove()` | Menghapus elemen langsung dari DOM. |
| `removeChild(childNode)` | Menghapus elemen anak dari elemen induk. |

