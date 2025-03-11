# Looping dengan While di JavaScript

## Pengertian
`while` adalah salah satu bentuk perulangan (loop) dalam JavaScript yang digunakan untuk mengeksekusi blok kode selama kondisi yang diberikan bernilai `true`. Perulangan ini cocok digunakan ketika jumlah iterasi belum diketahui dengan pasti.

## Sintaks
```javascript
while (kondisi) {
    // Blok kode yang akan dieksekusi selama kondisi bernilai true
}
```

## Contoh Penggunaan

### 1. Looping Sederhana
Berikut adalah contoh penggunaan `while` untuk mencetak angka dari 1 hingga 5:

```javascript
let angka = 1;
while (angka <= 5) {
    console.log("Angka: ", angka);
    angka++; // Increment agar loop tidak berjalan terus-menerus
}
```

**Output:**
```
Angka: 1
Angka: 2
Angka: 3
Angka: 4
Angka: 5
```

**Penjelasan:**
- Variabel `angka` dimulai dari `1`.
- Selama `angka` kurang dari atau sama dengan `5`, blok kode akan dijalankan.
- `angka++` digunakan untuk menambah nilai variabel agar kondisi menjadi `false` setelah lima iterasi.

### 2. Looping dengan Kondisi yang Tidak Diketahui
Looping `while` sering digunakan saat kita tidak tahu berapa banyak iterasi yang diperlukan, misalnya menunggu input valid dari pengguna.

```javascript
let input = "";
while (input !== "ok") {
    input = prompt("Masukkan 'ok' untuk berhenti: ");
    console.log("Anda memasukkan: ", input);
}
```

**Output (contoh interaksi pengguna):**
```
Masukkan 'ok' untuk berhenti: hai
Anda memasukkan: hai
Masukkan 'ok' untuk berhenti: test
Anda memasukkan: test
Masukkan 'ok' untuk berhenti: ok
Anda memasukkan: ok
```

**Penjelasan:**
- Program meminta input dari pengguna.
- Jika pengguna tidak memasukkan `ok`, loop akan terus berjalan.
- Begitu pengguna mengetik `ok`, loop berhenti.

### 3. Looping dengan `break`
Terkadang kita perlu menghentikan perulangan secara paksa menggunakan `break`.

```javascript
let angka = 1;
while (true) { // Loop tak terbatas
    console.log("Angka: ", angka);
    if (angka >= 5) {
        break; // Menghentikan loop jika angka sudah 5
    }
    angka++;
}
```

**Output:**
```
Angka: 1
Angka: 2
Angka: 3
Angka: 4
Angka: 5
```

**Penjelasan:**
- Loop dibuat tanpa batas (`while (true)`).
- Jika `angka` mencapai `5`, loop dihentikan dengan `break`.

### 4. Looping dengan `continue`
Gunakan `continue` jika ingin melewati iterasi tertentu tanpa menghentikan loop.

```javascript
let angka = 0;
while (angka < 5) {
    angka++;
    if (angka === 3) {
        console.log("Lewati angka 3");
        continue; // Langsung ke iterasi berikutnya
    }
    console.log("Angka: ", angka);
}
```

**Output:**
```
Angka: 1
Angka: 2
Lewati angka 3
Angka: 4
Angka: 5
```

**Penjelasan:**
- Jika `angka` sama dengan `3`, maka `console.log("Lewati angka 3")` akan dieksekusi.
- `continue` menyebabkan eksekusi melewati `console.log("Angka: ", angka)` untuk angka 3.

## Kesimpulan
- `while` digunakan ketika jumlah iterasi tidak pasti.
- Gunakan `break` untuk menghentikan loop secara paksa.
- Gunakan `continue` untuk melewati iterasi tertentu tanpa keluar dari loop.
- Pastikan kondisi bisa berubah untuk menghindari infinite loop.



