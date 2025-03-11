# Looping dengan `do...while` di JavaScript

## Pengantar
Looping atau perulangan dalam JavaScript digunakan untuk mengeksekusi kode secara berulang hingga kondisi tertentu terpenuhi. Salah satu jenis perulangan yang tersedia adalah `do...while` loop.

## Sintaks Dasar
```javascript
 do {
    // Blok kode yang akan dieksekusi
 } while (kondisi);
```

### Penjelasan:
1. Blok kode dalam `do` akan dieksekusi setidaknya satu kali sebelum pengecekan kondisi.
2. Setelah eksekusi pertama, kondisi dalam `while` akan diperiksa.
3. Jika kondisi masih bernilai `true`, maka loop akan terus berjalan.
4. Jika kondisi bernilai `false`, maka loop akan berhenti.

## Contoh Penggunaan

### Contoh 1: Looping dari 1 sampai 5
```javascript
let i = 1;
do {
    console.log("Iterasi ke-" + i);
    i++;
} while (i <= 5);
```
#### Output:
```
Iterasi ke-1
Iterasi ke-2
Iterasi ke-3
Iterasi ke-4
Iterasi ke-5
```

### Contoh 2: Menjalankan Looping Minimal Sekali
```javascript
let angka = 10;
do {
    console.log("Angka saat ini: " + angka);
    angka++;
} while (angka < 10);
```
#### Output:
```
Angka saat ini: 10
```
**Penjelasan:**
Meskipun kondisi `angka < 10` bernilai `false`, perulangan tetap dijalankan satu kali sebelum pemeriksaan kondisi.

### Contoh 3: Meminta Input dari Pengguna hingga Valid
```javascript
let password;
do {
    password = prompt("Masukkan password (minimal 6 karakter):");
    console.log("Input yang dimasukkan: " + password);
} while (password.length < 6);

console.log("Password diterima!");
```
#### Output (jika pengguna memasukkan "abc", lalu "abcdef"):
```
Input yang dimasukkan: abc
Input yang dimasukkan: abcdef
Password diterima!
```

## Kapan Menggunakan `do...while`?
`do...while` cocok digunakan ketika kita ingin memastikan bahwa suatu blok kode dieksekusi setidaknya sekali, terlepas dari kondisi awalnya.

## Kesimpulan
- `do...while` memastikan blok kode dijalankan minimal satu kali.
- Berguna dalam kasus di mana kita ingin pengguna menginput data setidaknya satu kali.
- Hati-hati dengan kondisi yang tidak pernah `false`, karena bisa menyebabkan infinite loop.


