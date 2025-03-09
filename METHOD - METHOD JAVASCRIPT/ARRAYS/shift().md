# Dokumentasi: Metode `shift()` pada Array JavaScript

## Pengantar
Metode `shift()` adalah salah satu metode bawaan (built-in method) dalam JavaScript yang digunakan untuk menghapus elemen pertama dari sebuah array dan mengembalikan elemen yang dihapus tersebut. Setelah elemen pertama dihapus, indeks dari elemen-elemen yang tersisa akan bergeser ke kiri.

---

## Sintaks
```javascript
array.shift()
```

### Parameter
Metode `shift()` tidak memiliki parameter.

### Nilai Kembalian
Metode ini mengembalikan elemen pertama dari array sebelum dihapus. Jika array kosong, maka nilai yang dikembalikan adalah `undefined`.

---

## Contoh Penggunaan
### Contoh 1: Menghapus Elemen Pertama dari Array
```javascript
let fruits = ["Apel", "Mangga", "Pisang"];
let removedFruit = fruits.shift();

console.log(removedFruit); // Output: "Apel"
console.log(fruits);       // Output: ["Mangga", "Pisang"]
```

### Contoh 2: Menggunakan `shift()` pada Array Kosong
```javascript
let numbers = [];
let removedNumber = numbers.shift();

console.log(removedNumber); // Output: undefined
console.log(numbers);       // Output: []
```

---

## Perbedaan `shift()` dan `pop()`
Metode `shift()` mirip dengan `pop()`, tetapi dengan perbedaan utama:

| Metode  | Fungsi                                      |
|---------|---------------------------------------------|
| `shift()` | Menghapus elemen pertama dari array       |
| `pop()`   | Menghapus elemen terakhir dari array      |

Contoh perbedaan:
```javascript
let arr = [1, 2, 3, 4];
arr.shift();
console.log(arr); // Output: [2, 3, 4]

let arr2 = [1, 2, 3, 4];
arr2.pop();
console.log(arr2); // Output: [1, 2, 3]
```

---

## Kesimpulan
- `shift()` digunakan untuk menghapus elemen pertama dari array.
- Mengembalikan elemen yang dihapus atau `undefined` jika array kosong.
- Menggeser indeks elemen-elemen yang tersisa ke kiri.
- Berbeda dengan `pop()` yang menghapus elemen terakhir.

Metode `shift()` sangat berguna ketika bekerja dengan struktur data seperti queue (FIFO - First In First Out).
