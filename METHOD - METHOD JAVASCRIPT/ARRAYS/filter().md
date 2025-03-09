# Dokumentasi JavaScript Array filter()

## Pengantar

Metode `filter()` dalam JavaScript digunakan untuk membuat array baru yang berisi elemen-elemen dari array asli yang memenuhi kondisi tertentu. Metode ini tidak mengubah array asli.

---

## Sintaks

```javascript
array.filter(callback(element, index, array), thisArg)
```

### Parameter
- **callback**: Fungsi yang akan dijalankan pada setiap elemen array.
  - **element**: Elemen saat ini yang sedang diproses.
  - **index** *(opsional)*: Indeks elemen saat ini.
  - **array** *(opsional)*: Array yang sedang diproses.
- **thisArg** *(opsional)*: Nilai yang akan digunakan sebagai `this` saat menjalankan `callback`.

---

## Contoh Penggunaan

### 1. Menyaring Bilangan Genap
```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // Output: [2, 4, 6, 8, 10]
```

### 2. Menyaring Data Berdasarkan Kondisi
```javascript
const people = [
  { name: "Alice", age: 25 },
  { name: "Bob", age: 17 },
  { name: "Charlie", age: 30 }
];

const adults = people.filter(person => person.age >= 18);
console.log(adults);
/* Output:
[
  { name: "Alice", age: 25 },
  { name: "Charlie", age: 30 }
]
*/
```

### 3. Menyaring String dalam Array
```javascript
const words = ["apple", "banana", "avocado", "grape"];
const aWords = words.filter(word => word.startsWith("a"));
console.log(aWords); // Output: ["apple", "avocado"]
```

---

## Catatan Penting
1. **Tidak Mengubah Array Asli**: `filter()` tidak mengubah array asli, tetapi menghasilkan array baru.
2. **Callback Harus Mengembalikan Boolean**: Callback harus mengembalikan `true` untuk menyertakan elemen dalam array hasil.
3. **Dapat Digunakan dengan Objek**: `filter()` sangat berguna untuk menyaring data berbasis objek.

---

## Kesimpulan
Metode `filter()` sangat berguna untuk memfilter elemen dalam array berdasarkan kondisi tertentu. Dengan memahami cara kerja metode ini, kita bisa memproses dan menyaring data dengan lebih efisien dalam JavaScript.
