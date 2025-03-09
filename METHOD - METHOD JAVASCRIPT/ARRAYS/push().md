# Dokumentasi: Array.prototype.push()

## Deskripsi

Metode `push()` digunakan untuk menambahkan satu atau lebih elemen ke akhir sebuah array. Metode ini mengubah array asli dan mengembalikan panjang array yang baru.

## Sintaksis

```javascript
array.push(elemen1, elemen2, ..., elemenN)
```

## Parameter

- **elemen1, elemen2, ..., elemenN** (Opsional) - Elemen yang akan ditambahkan ke akhir array.

## Nilai yang Dikembalikan

Metode `push()` mengembalikan nilai berupa **angka** yang menunjukkan panjang array setelah elemen baru ditambahkan.

## Contoh Penggunaan

### 1. Menambahkan satu elemen ke array

```javascript
let buah = ["apel", "mangga"];
let panjangBaru = buah.push("pisang");

console.log(buah); // Output: ["apel", "mangga", "pisang"]
console.log(panjangBaru); // Output: 3
```

### 2. Menambahkan beberapa elemen ke array

```javascript
let angka = [1, 2, 3];
let panjangBaru = angka.push(4, 5, 6);

console.log(angka); // Output: [1, 2, 3, 4, 5, 6]
console.log(panjangBaru); // Output: 6
```

### 3. Menggunakan `push()` pada array kosong

```javascript
let daftar = [];
daftar.push("Item 1", "Item 2");

console.log(daftar); // Output: ["Item 1", "Item 2"]
```

### 4. Menggunakan `push()` dengan array bersifat `const`

```javascript
const hewan = ["kucing", "anjing"];
hewan.push("kelinci");

console.log(hewan); // Output: ["kucing", "anjing", "kelinci"]
```

> **Catatan:** Meskipun `const` digunakan, kita masih bisa mengubah isi array, tetapi tidak bisa mengganti referensi array itu sendiri.

## Bagaimana `push()` Mengembalikan Panjang Array?

Metode `push()` mengembalikan panjang baru dari array setelah elemen baru ditambahkan.

Misalnya:

```javascript
let angka = [1, 2, 3]; 
let panjangBaru = angka.push(4, 5, 6);
console.log(angka); // Output: [1, 2, 3, 4, 5, 6]
console.log(panjangBaru); // Output: 6
```

### Penjelasan:
1. **Array awal** adalah `[1, 2, 3]` dengan panjang **3**.
2. **Metode `push(4, 5, 6)`** menambahkan tiga elemen ke akhir array, sehingga menjadi `[1, 2, 3, 4, 5, 6]`.
3. **Panjang array setelahnya adalah 6**, dan inilah yang dikembalikan oleh `push()`.

Jika hanya menambahkan **satu elemen**:

```javascript
let angka = [1, 2, 3];
let panjangBaru = angka.push(4);
console.log(panjangBaru); // Output: 4
```

Jika **tidak menambahkan elemen sama sekali**:

```javascript
let angka = [1, 2, 3];
let panjangBaru = angka.push();
console.log(panjangBaru); // Output: 3
```

## Perbedaan dengan Metode Lain

| Metode       | Deskripsi |
|-------------|------------------------------------------------|
| `push()`    | Menambahkan elemen di akhir array. |
| `pop()`     | Menghapus elemen terakhir dari array. |
| `unshift()` | Menambahkan elemen di awal array. |
| `shift()`   | Menghapus elemen pertama dari array. |

## Kesimpulan

Metode `push()` sangat berguna untuk menambahkan elemen ke dalam array secara langsung. Karena metode ini mengubah array asli, pastikan penggunaannya sesuai dengan kebutuhan untuk menghindari perubahan yang tidak diinginkan.
