# Dokumentasi Method `findIndex()` dalam JavaScript

## 📌 Pengantar
Method `findIndex()` dalam JavaScript digunakan untuk mencari indeks elemen pertama dalam array yang memenuhi kondisi tertentu yang ditentukan oleh fungsi callback.

## 📜 Sintaks
```javascript
array.findIndex(callback(element, index, array), thisArg);
```

### 🎯 Parameter
1. `callback(element, index, array)`
   - **element** → Elemen array yang sedang diproses.
   - **index** → Indeks dari elemen yang sedang diproses.
   - **array** → Array yang sedang diperiksa.
2. `thisArg` *(opsional)* → Nilai yang akan digunakan sebagai `this` saat eksekusi fungsi callback.

### 🔍 Nilai Kembalian
- Mengembalikan **indeks** dari elemen pertama yang memenuhi kondisi dalam fungsi callback.
- Jika tidak ditemukan, maka mengembalikan **-1**.

---

## 🎯 Contoh Penggunaan

### ✅ Mencari Indeks Elemen yang Memenuhi Kondisi
```javascript
const angka = [10, 20, 30, 40, 50];
const indeks = angka.findIndex((elemen) => elemen > 25);
console.log(indeks); // Output: 2 (karena 30 adalah elemen pertama yang lebih besar dari 25)
```

### ❌ Jika Tidak Ada yang Memenuhi Kondisi
```javascript
const angka = [5, 10, 15];
const indeks = angka.findIndex((elemen) => elemen > 20);
console.log(indeks); // Output: -1 (karena tidak ada elemen yang lebih besar dari 20)
```

### 🏷️ Menggunakan `thisArg`
```javascript
const data = {
  batas: 15
};

const angka = [10, 12, 18, 22];
const indeks = angka.findIndex(function(elemen) {
  return elemen > this.batas;
}, data);

console.log(indeks); // Output: 2 (karena 18 adalah elemen pertama yang lebih besar dari 15)
```

---

## 🔥 Kapan Menggunakan `findIndex()`?
- Saat perlu mendapatkan **indeks** elemen pertama yang memenuhi syarat tertentu.
- Berguna dalam operasi seperti **pembaruan data** dalam array dengan metode berbasis indeks.

---

## 🎯 Perbedaan dengan `find()`
| Method       | Nilai Kembalian |
|-------------|----------------|
| `find()`    | Mengembalikan elemen yang ditemukan |
| `findIndex()` | Mengembalikan indeks dari elemen yang ditemukan |

Contoh:
```javascript
const angka = [10, 20, 30, 40];
console.log(angka.find((elemen) => elemen > 25)); // Output: 30
console.log(angka.findIndex((elemen) => elemen > 25)); // Output: 2
```

---

## 🎯 Kesimpulan
- `findIndex()` berguna untuk mencari indeks elemen dalam array berdasarkan kondisi tertentu.
- Jika elemen ditemukan, mengembalikan indeksnya; jika tidak, mengembalikan `-1`.
- Alternatifnya, gunakan `find()` jika ingin mendapatkan elemen langsung.

---
📚 **Referensi:** [MDN Web Docs - findIndex()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex)
