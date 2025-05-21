
# Jenis-Jenis Error dalam JavaScript

Dalam proses pengembangan aplikasi JavaScript, sangat umum bagi pemula (bahkan profesional) untuk menemui berbagai macam error. Berikut adalah beberapa jenis error yang sering muncul beserta contoh dan penjelasannya.

---

## 1. SyntaxError

**Penjelasan**  
`SyntaxError` terjadi ketika terdapat kesalahan dalam penulisan sintaks JavaScript. Biasanya error ini muncul saat tanda kurung, kurung kurawal, tanda kutip tidak ditutup, atau kesalahan penempatan simbol.

**Contoh:**
```javascript
console.log('Halo'; // Uncaught SyntaxError: missing ) after argument list
```

**Output:**
```
Uncaught SyntaxError: missing ) after argument list
```

**Solusi:**
Pastikan seluruh tanda kurung dan simbol ditutup dan ditulis dengan benar.
```javascript
console.log('Halo');
```

**Output:**
```
Halo
```

---

## 2. TypeError

**Penjelasan**  
`TypeError` terjadi saat Anda mencoba mengakses atau memanipulasi nilai dengan tipe data yang tidak sesuai. Contohnya, memanggil method pada `null` atau `undefined`.

**Contoh:**
```javascript
let kosong = null;

console.log(kosong.toString()); // Uncaught TypeError: kosong is null
```

**Output:**
```
Uncaught TypeError: kosong is null
```

**Solusi:**
Periksa apakah nilai sudah terdefinisi dan bukan `null` atau `undefined` sebelum memanggil properti atau method-nya.
```javascript
let kosong = null;

if (kosong !== null) {
  console.log(kosong.toString());
}
```

**Output:**
(tidak ada output karena kondisi tidak terpenuhi)

---

## 3. ReferenceError

**Penjelasan**  
`ReferenceError` terjadi saat mencoba menggunakan variabel yang belum dideklarasikan.

**Contoh:**
```javascript
let empty;

console.log(empt); // Uncaught ReferenceError: empt is not defined
```

**Output:**
```
Uncaught ReferenceError: empt is not defined
```

**Solusi:**
Pastikan nama variabel sudah dideklarasikan dan tidak typo.
```javascript
let empty = 'data';

console.log(empty);
```

**Output:**
```
data
```

---

## 4. RangeError (Tambahan)

**Penjelasan**  
`RangeError` terjadi saat nilai berada di luar rentang yang dapat diterima. Contohnya, memberikan angka negatif pada method yang membutuhkan angka positif.

**Contoh:**
```javascript
let angka = new Array(-5); // Uncaught RangeError: Invalid array length
```

**Output:**
```
Uncaught RangeError: Invalid array length
```

**Solusi:**
Pastikan nilai berada dalam rentang yang sesuai dengan konteksnya.
```javascript
let angka = new Array(3);

console.log(angka.length);
```

**Output:**
```
3
```

---

## 5. EvalError (Jarang Terjadi)

**Penjelasan**  
`EvalError` terkait dengan penggunaan `eval()`, meskipun sekarang error ini jarang muncul karena `eval()` sendiri jarang digunakan dalam praktik modern.

**Contoh:**
```javascript
// eval('alert("Halo");'); // Biasanya aman, tapi penggunaan yang salah bisa memicu EvalError
```

**Output:**
```
(jika dijalankan, akan menampilkan alert "Halo")
```

---

## Tips Menghindari Error di JavaScript

- Gunakan editor seperti **Visual Studio Code** yang memiliki fitur linting.
- Gunakan `try...catch` untuk menangani error secara elegan.
- Aktifkan **Strict Mode** (`'use strict';`) untuk membantu mendeteksi kesalahan lebih awal.
- Gunakan **console.log()** untuk melakukan debug.

---
