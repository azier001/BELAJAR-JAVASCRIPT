# Dokumentasi JavaScript: Array.prototype.indexOf()

## Deskripsi
`indexOf()` adalah metode bawaan dalam JavaScript yang digunakan untuk mencari indeks pertama dari elemen tertentu dalam sebuah array. Jika elemen ditemukan, metode ini mengembalikan indeksnya. Jika tidak ditemukan, maka mengembalikan `-1`.

## Sintaks
```javascript
array.indexOf(searchElement, fromIndex)
```

## Parameter
- **searchElement** *(wajib)*: Elemen yang ingin dicari dalam array.
- **fromIndex** *(opsional)*: Indeks awal pencarian. Default adalah `0`. Jika bernilai negatif, dihitung dari akhir array.

## Nilai Kembali
Metode ini mengembalikan indeks pertama dari `searchElement` dalam array. Jika elemen tidak ditemukan, akan mengembalikan `-1`.

## Contoh Penggunaan
### 1. Mencari Elemen dalam Array
```javascript
const angka = [10, 20, 30, 40, 50];
console.log(angka.indexOf(30)); // Output: 2
console.log(angka.indexOf(60)); // Output: -1
```

### 2. Menggunakan `fromIndex`
```javascript
const huruf = ['a', 'b', 'c', 'd', 'a', 'e'];
console.log(huruf.indexOf('a', 1)); // Output: 4
```

### 3. `fromIndex` dengan Nilai Negatif
```javascript
const angka = [10, 20, 30, 40, 50, 30];
console.log(angka.indexOf(30, -3)); // Output: 5
```

## Perbedaan dengan `includes()` dan `findIndex()`
| Metode       | Fungsi |
|-------------|--------|
| `indexOf()` | Mengembalikan indeks pertama dari elemen yang ditemukan atau `-1` jika tidak ada. |
| `includes()` | Mengembalikan `true` jika elemen ditemukan, `false` jika tidak. |
| `findIndex()` | Mengembalikan indeks elemen pertama yang memenuhi kondisi fungsi callback. |

## Catatan
- `indexOf()` melakukan pencarian **dengan perbandingan ketat (`===`)**.
- Tidak bekerja dengan objek atau array kompleks karena membandingkan referensi, bukan nilai.

## Kesimpulan
Metode `indexOf()` sangat berguna untuk mencari posisi elemen dalam array. Namun, jika perlu mencari elemen berdasarkan kondisi tertentu, lebih baik menggunakan `findIndex()`.
