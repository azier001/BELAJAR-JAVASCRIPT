# Function Declaration dalam JavaScript

## Pengertian
Function declaration adalah salah satu cara untuk mendefinisikan fungsi dalam JavaScript. Fungsi yang dibuat dengan cara ini dapat digunakan sebelum dideklarasikan karena mengalami **hoisting**.

## Hoisting dalam Function Declaration
**Hoisting** adalah mekanisme di JavaScript di mana deklarasi fungsi atau variabel dipindahkan ke atas sebelum kode dieksekusi. Dalam function declaration, ini berarti fungsi dapat dipanggil sebelum dideklarasikan dalam kode.

Contoh hoisting:
```javascript
console.log(sapa("Budi")); // Output: Halo, Budi!

function sapa(nama) {
    return "Halo, " + nama + "!";
}
```

Pada contoh di atas, meskipun fungsi `sapa` dipanggil sebelum dideklarasikan, kode tetap berjalan dengan baik karena JavaScript mengangkat deklarasi fungsi ke atas saat proses interpretasi.

Namun, hoisting ini hanya berlaku untuk function declaration, tidak untuk function expression atau arrow function.

## Sintaks
```javascript
function namaFungsi(parameter1, parameter2) {
    // kode yang akan dijalankan
    return hasil;
}
```

## Contoh Penggunaan
### 1. Fungsi Sederhana
```javascript
function sapa(nama) {
    return "Halo, " + nama + "!";
}

console.log(sapa("Andi")); // Output: Halo, Andi!
```

### 2. Fungsi dengan Beberapa Parameter
```javascript
function tambah(a, b) {
    return a + b;
}

console.log(tambah(5, 3)); // Output: 8
```

### 3. Hoisting pada Function Declaration
Function declaration mengalami **hoisting**, sehingga dapat dipanggil sebelum dideklarasikan.

```javascript
console.log(kali(4, 2)); // Output: 8

function kali(x, y) {
    return x * y;
}
```

## Perbedaan dengan Function Expression
Function declaration berbeda dengan function expression. Berikut perbedaannya:

| Aspek | Function Declaration | Function Expression |
|-------|----------------------|----------------------|
| Hoisting | Ya, bisa dipanggil sebelum deklarasi | Tidak, harus dideklarasikan dulu |
| Sintaks | `function nama() {...}` | `const nama = function() {...}` |

Contoh function expression:
```javascript
const kurang = function(a, b) {
    return a - b;
};

console.log(kurang(10, 4)); // Output: 6
```

## Kesimpulan
- Function declaration adalah cara mendefinisikan fungsi di JavaScript yang mengalami hoisting.
- Bisa dipanggil sebelum dideklarasikan.
- Memiliki sintaks yang lebih sederhana dibanding function expression.
- Berbeda dengan function expression yang tidak mengalami hoisting.



