# Dokumentasi: Array.prototype.find()

## Pengantar
`find()` adalah metode dalam JavaScript yang digunakan untuk mencari elemen pertama dalam array yang memenuhi kondisi tertentu yang ditentukan oleh sebuah fungsi callback.

## Sintaks
```javascript
array.find(callback(element, index, array), thisArg)
```

## Parameter
- `callback` (required): Fungsi yang akan dijalankan pada setiap elemen dalam array.
  - `element` (required): Elemen array yang sedang diperiksa.
  - `index` (optional): Indeks dari elemen yang sedang diperiksa.
  - `array` (optional): Array yang sedang diperiksa.
- `thisArg` (optional): Nilai yang akan digunakan sebagai `this` saat mengeksekusi `callback`.

## Nilai Kembalian
Metode `find()` mengembalikan **elemen pertama** yang memenuhi kondisi yang diberikan dalam `callback`. Jika tidak ada elemen yang cocok, maka `undefined` akan dikembalikan.

## Contoh Penggunaan

### Mencari Angka dalam Array
```javascript
const numbers = [10, 20, 30, 40, 50];
const found = numbers.find(num => num > 25);
console.log(found); // Output: 30
```

### Mencari Objek dalam Array
```javascript
const users = [
  { id: 1, name: "Alice" },
  { id: 2, name: "Bob" },
  { id: 3, name: "Charlie" }
];

const user = users.find(user => user.id === 2);
console.log(user); // Output: { id: 2, name: "Bob" }
```

### Menggunakan `thisArg`
```javascript
const threshold = { min: 25 };
const numbers = [10, 20, 30, 40, 50];

const found = numbers.find(function(num) {
  return num > this.min;
}, threshold);

console.log(found); // Output: 30
```

## Perbedaan dengan `filter()`
- `find()` hanya mengembalikan **satu elemen pertama** yang cocok.
- `filter()` mengembalikan **semua elemen** yang cocok dalam bentuk array.

Contoh:
```javascript
const numbers = [10, 20, 30, 40, 50];
console.log(numbers.find(num => num > 25)); // Output: 30
console.log(numbers.filter(num => num > 25)); // Output: [30, 40, 50]
```

## Kesimpulan
- `find()` berguna untuk mendapatkan satu elemen pertama yang sesuai dengan kondisi.
- Jika tidak ditemukan elemen yang cocok, hasilnya `undefined`.
- Perbedaan utama dengan `filter()` adalah jumlah elemen yang dikembalikan.

Dokumentasi ini membantu memahami cara kerja `find()` dengan contoh yang mudah dipahami.
