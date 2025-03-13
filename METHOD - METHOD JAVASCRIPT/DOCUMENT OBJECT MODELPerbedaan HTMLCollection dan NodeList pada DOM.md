# Perbedaan HTMLCollection dan NodeList pada DOM

Dalam DOM (**Document Object Model**), **HTMLCollection** dan **NodeList** adalah dua jenis kumpulan (**collections**) node yang sering digunakan untuk menangani elemen-elemen dalam sebuah dokumen HTML. Berikut adalah perbedaan mendetail antara keduanya:

---

## 1. Definisi
### **HTMLCollection**
- Kumpulan elemen yang diambil berdasarkan tag atau properti HTML tertentu.
- Hanya berisi elemen-elemen HTML (tidak termasuk teks atau komentar).
- Contoh metode yang mengembalikan **HTMLCollection**:
  ```javascript
  let elements = document.getElementsByTagName("p");
  let elements2 = document.getElementsByClassName("my-class");
  ```

### **NodeList**
- Kumpulan node yang bisa berisi elemen HTML, teks, komentar, dan lainnya.
- Bisa bersifat **live** (dinamis) atau **static** (tetap).
- Contoh metode yang mengembalikan **NodeList**:
  ```javascript
  let nodes = document.querySelectorAll("p"); // Static NodeList
  let nodes2 = document.childNodes; // Bisa berisi teks dan komentar
  ```

---

## 2. Sifat Live dan Static

| Sifat | HTMLCollection | NodeList |
|--------|--------------|----------|
| **Live (dinamis)** | ✅ Ya | ✅ Bisa (hanya `childNodes`) |
| **Static (tetap)** | ❌ Tidak | ✅ Ya (`querySelectorAll()` mengembalikan static NodeList) |

### **Contoh Perbedaan Live dan Static**
#### **HTMLCollection (Live)**
```javascript
let elements = document.getElementsByTagName("p");
console.log(elements.length); // Misalnya 2

document.body.appendChild(document.createElement("p"));
console.log(elements.length); // Menjadi 3 karena bersifat live
```

#### **NodeList (Static)**
```javascript
let nodes = document.querySelectorAll("p");
console.log(nodes.length); // Misalnya 2

document.body.appendChild(document.createElement("p"));
console.log(nodes.length); // Tetap 2 karena bersifat static
```

---

## 3. Cara Akses Elemen

| Akses | HTMLCollection | NodeList |
|-------|--------------|----------|
| **Menggunakan indeks** | ✅ Bisa (`elements[0]`) | ✅ Bisa (`nodes[0]`) |
| **Menggunakan loop `for`** | ✅ Bisa | ✅ Bisa |
| **Menggunakan `forEach()`** | ❌ Tidak bisa langsung | ✅ Bisa (untuk NodeList dari `querySelectorAll`) |

### **Contoh Looping HTMLCollection**
```javascript
let elements = document.getElementsByTagName("p");

// Tidak bisa menggunakan forEach secara langsung
// elements.forEach(el => console.log(el)); // ❌ Error!

// Harus dikonversi ke array dulu
Array.from(elements).forEach(el => console.log(el)); // ✅ Bisa
```

### **Contoh Looping NodeList**
```javascript
let nodes = document.querySelectorAll("p");
nodes.forEach(node => console.log(node)); // ✅ Bisa langsung
```

---

## 4. Dukungan Metode

| Metode | HTMLCollection | NodeList |
|--------|--------------|----------|
| `length` | ✅ Bisa | ✅ Bisa |
| `item(index)` | ✅ Bisa | ✅ Bisa |
| `namedItem(name)` | ✅ Bisa | ❌ Tidak bisa |
| `forEach()` | ❌ Tidak bisa langsung | ✅ Bisa |

Contoh penggunaan `namedItem(name)` pada **HTMLCollection**:
```html
<input type="text" name="username">
```
```javascript
let inputs = document.getElementsByTagName("input");
console.log(inputs.namedItem("username")); // Mengembalikan elemen <input>
```

---

## 5. Kesimpulan

| Perbedaan | HTMLCollection | NodeList |
|-----------|--------------|----------|
| **Berisi selain elemen HTML?** | ❌ Tidak | ✅ Ya (bisa berisi teks dan komentar) |
| **Live (otomatis berubah saat DOM berubah)?** | ✅ Ya | ❌ Tidak (kecuali `childNodes`) |
| **Dapat menggunakan `forEach()` langsung?** | ❌ Tidak | ✅ Ya |
| **Metode yang mengembalikan?** | `getElementsByTagName()`, `getElementsByClassName()` | `querySelectorAll()`, `childNodes` |

### **Kapan Menggunakan HTMLCollection dan NodeList?**
- Gunakan **HTMLCollection** jika ingin daftar elemen yang selalu berubah sesuai dengan DOM.
- Gunakan **NodeList** jika ingin menangani semua jenis node atau memanfaatkan metode `forEach()` secara langsung.


