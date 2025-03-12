
## Penjelasan High-Order Function
High-order function adalah konsep dalam pemrograman fungsional yang memungkinkan kita untuk menggunakan function sebagai data. Ini berguna untuk abstraksi logika dan meningkatkan reusability kode.

### Contoh 1: Manipulasi Array dengan Callback
Pada contoh ini, `manipulasiArray` adalah sebuah higher-order function karena menerima function `callback` sebagai argumen.

- `manipulasiArray` melakukan iterasi pada array `arr`.
- Setiap elemen array diproses oleh function `callback`.
- Hasil dari pemrosesan disimpan dalam array `hasil`.
- Function `kaliDua` adalah contoh callback yang dikirim ke `manipulasiArray`.

```javascript
function manipulasiArray(arr, callback) {
  let hasil = [];

  for (let i = 0; i < arr.length; i++) {
    hasil.push(callback(arr[i]));
  }

  return hasil;
}

function kaliDua(x) {
  return x * 2;
}

let angka = [1, 2, 3, 4];
let hasil = manipulasiArray(angka, kaliDua);

console.log(hasil); // [2, 4, 6, 8]
```

### Contoh 2: Penggunaan `.map()` sebagai High-Order Function
Method `.map()` adalah salah satu higher-order function bawaan JavaScript.

- `.map()` menerima function sebagai argumen.
- Function tersebut akan dipanggil untuk setiap elemen dalam array.
- Hasil dari function akan membentuk array baru.

```javascript
const angkaBaru = angka.map(kaliDua);
console.log(angkaBaru); // [2, 4, 6, 8]
```

### Contoh 3: Higher-Order Function Mengembalikan Function Lain
Pada contoh ini, `pembuatPengali` adalah higher-order function karena mengembalikan function lain.

- `pembuatPengali` menerima parameter `faktor`.
- Function yang dikembalikan menerima parameter `angka`.
- Hasil akhirnya adalah perkalian antara `angka` dan `faktor`.
- Kita bisa membuat beberapa function dengan faktor berbeda, seperti `kaliTiga`.

```javascript
function pembuatPengali(faktor) {
  return function(angka) {
    return angka * faktor;
  };
}

const kaliTiga = pembuatPengali(3);
console.log(kaliTiga(5)); // 15
```

Dengan memahami konsep ini, kita bisa menulis kode yang lebih modular dan mudah dibaca!
