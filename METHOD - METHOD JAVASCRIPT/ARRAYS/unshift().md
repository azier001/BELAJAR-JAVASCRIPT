# Metode `unshift()` dalam Array JavaScript

## Pengantar
Metode `unshift()` adalah metode bawaan dalam JavaScript yang digunakan untuk menambahkan satu atau lebih elemen ke awal array dan mengembalikan panjang array yang baru.

## Sintaks
```javascript
array.unshift(element1, element2, ..., elementN)
```

### Parameter
- `element1, element2, ..., elementN` (opsional): Elemen-elemen yang akan ditambahkan ke awal array.

### Nilai yang Dikembalikan
- Mengembalikan panjang array setelah elemen-elemen baru ditambahkan.

## Contoh Penggunaan

### Contoh 1: Menambahkan Satu Elemen ke Awal Array
```javascript
let fruits = ["apel", "mangga", "pisang"];
let newLength = fruits.unshift("jeruk");

console.log(fruits); // ["jeruk", "apel", "mangga", "pisang"]
console.log(newLength); // 4
```

### Contoh 2: Menambahkan Beberapa Elemen ke Awal Array
```javascript
let numbers = [3, 4, 5];
numbers.unshift(1, 2);

console.log(numbers); // [1, 2, 3, 4, 5]
```

## Perbedaan dengan `push()`
| Metode    | Deskripsi |
|-----------|-----------|
| `unshift()` | Menambahkan elemen di awal array |
| `push()` | Menambahkan elemen di akhir array |

## Efek Performa
`unshift()` memiliki kompleksitas waktu O(n) karena setiap elemen dalam array harus digeser ke indeks yang lebih tinggi. Jika sering menambahkan elemen ke awal array dalam array besar, pertimbangkan untuk menggunakan struktur data lain seperti `LinkedList`.

## Kesimpulan
Metode `unshift()` adalah cara praktis untuk menambahkan elemen ke awal array dalam JavaScript. Namun, perlu diperhatikan bahwa metode ini bisa berdampak pada performa jika digunakan dalam array yang sangat besar.

---

### Referensi
- [MDN Web Docs - Array.prototype.unshift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)
