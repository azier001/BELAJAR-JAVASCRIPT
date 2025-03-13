## Soal Tantangan

Buatlah sebuah arrow function bernama `pangkat` yang menerima dua parameter `base` dan `exponent`, kemudian mengembalikan hasil perpangkatan dari `base` dengan `exponent`. Panggil function tersebut dengan memberikan dua angka sebagai argumen.

### Implementasi Kode

```javascript
// Fungsi arrow untuk menghitung perpangkatan
const pangkat = (base, exponent) => {
  return base ** exponent;
};

// Memanggil fungsi pangkat dengan contoh nilai
let hasil = pangkat(5, 3);
console.log(hasil); // Output: 125
```

### Penjelasan Kode
1. Fungsi `pangkat` dibuat menggunakan arrow function (`=>`).
2. Parameter `base` adalah bilangan pokok yang akan dipangkatkan.
3. Parameter `exponent` adalah pangkat yang dikenakan pada `base`.
4. Menggunakan operator `**` untuk menghitung perpangkatan.
5. Fungsi dipanggil dengan nilai `5` sebagai `base` dan `3` sebagai `exponent`.
6. Hasil dari `5 ** 3` adalah `125`, yang kemudian ditampilkan dengan `console.log()`.

