# Dokumentasi JavaScript Array pop()

## Deskripsi
`pop()` adalah metode bawaan JavaScript yang digunakan untuk menghapus elemen terakhir dari sebuah array dan mengembalikan elemen yang dihapus tersebut. Jika array kosong, metode ini akan mengembalikan `undefined`.

## Sintaks
```javascript
array.pop()
```

## Parameter
Metode `pop()` tidak memiliki parameter.

## Nilai Kembalian
- Jika array memiliki elemen, `pop()` akan mengembalikan elemen terakhir yang dihapus dari array.
- Jika array kosong, `pop()` mengembalikan `undefined`.

## Contoh Penggunaan

### Contoh 1: Menghapus Elemen Terakhir dari Array
```javascript
let fruits = ["Apel", "Pisang", "Mangga"];
let removedFruit = fruits.pop();

console.log(removedFruit); // Output: "Mangga"
console.log(fruits);       // Output: ["Apel", "Pisang"]
```

### Contoh 2: Menggunakan `pop()` pada Array Kosong
```javascript
let emptyArray = [];
let removedElement = emptyArray.pop();

console.log(removedElement); // Output: undefined
console.log(emptyArray);     // Output: []
```

## Perbedaan dengan Metode Lain
| Metode      | Deskripsi |
|------------|-----------|
| `pop()`    | Menghapus elemen terakhir dan mengembalikannya |
| `push()`   | Menambahkan elemen di akhir array |
| `shift()`  | Menghapus elemen pertama dan mengembalikannya |
| `unshift()` | Menambahkan elemen di awal array |

## Catatan
- `pop()` mengubah array secara langsung (mutasi).
- Tidak memerlukan parameter.
- Berguna ketika ingin menghapus elemen terakhir secara dinamis dalam struktur data berbasis array.

## Referensi
- [MDN Web Docs: Array.prototype.pop()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)
