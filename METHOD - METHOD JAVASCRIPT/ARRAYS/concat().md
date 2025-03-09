# Dokumentasi: Array.concat() di JavaScript

## Deskripsi
`concat()` adalah metode dalam JavaScript yang digunakan untuk menggabungkan dua atau lebih array tanpa mengubah array asli. Metode ini mengembalikan array baru yang berisi elemen dari array asli dan elemen tambahan yang diberikan sebagai argumen.

## Sintaks
```javascript
arrayBaru = array1.concat(array2, array3, ...);
```

## Parameter
- `array2, array3, ...` *(opsional)*: Satu atau lebih array atau nilai yang ingin digabungkan dengan `array1`.

## Nilai Kembali
Metode ini mengembalikan array baru yang merupakan hasil penggabungan array asli dengan array atau nilai yang diberikan.

## Contoh Penggunaan

### 1. Menggabungkan Dua Array
```javascript
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const hasil = array1.concat(array2);
console.log(hasil); // Output: [1, 2, 3, 4, 5, 6]
```

### 2. Menggabungkan Lebih dari Dua Array
```javascript
const angka = [1, 2];
const huruf = ['a', 'b'];
const simbol = ['!', '@'];
const gabungan = angka.concat(huruf, simbol);
console.log(gabungan); // Output: [1, 2, 'a', 'b', '!', '@']
```

### 3. Menggabungkan Array dengan Nilai Tunggal
```javascript
const angka = [1, 2, 3];
const hasil = angka.concat(4, 5);
console.log(hasil); // Output: [1, 2, 3, 4, 5]
```

### 4. Tidak Mengubah Array Asli
```javascript
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const hasil = array1.concat(array2);
console.log(array1); // Output: [1, 2, 3] (tetap sama)
console.log(array2); // Output: [4, 5, 6] (tetap sama)
```

## Catatan Penting
- `concat()` tidak mengubah array asli, tetapi mengembalikan array baru.
- Jika elemen dalam array adalah objek, maka referensi objek akan tetap dipertahankan (shallow copy).

### Contoh dengan Objek
```javascript
const obj1 = [{ nama: 'Alice' }];
const obj2 = [{ nama: 'Bob' }];
const hasil = obj1.concat(obj2);

// Mengubah nilai dalam array hasil
hasil[0].nama = 'Charlie';

console.log(obj1[0].nama); // Output: 'Charlie' (karena referensi yang sama)
```

## Kesimpulan
- `concat()` digunakan untuk menggabungkan array atau nilai tunggal tanpa mengubah array asli.
- Mengembalikan array baru dengan elemen-elemen gabungan.
- Untuk menghindari perubahan tak terduga pada objek di dalam array, gunakan teknik deep copy jika diperlukan.
