# Switch-Case di JavaScript

## Pengertian
Switch-case adalah pernyataan kondisional di JavaScript yang digunakan untuk membandingkan sebuah ekspresi dengan beberapa kemungkinan nilai dan mengeksekusi blok kode tertentu berdasarkan kecocokan nilai tersebut. Switch-case sering digunakan sebagai alternatif dari beberapa pernyataan if-else yang berturut-turut ketika kita ingin mengevaluasi sebuah variabel terhadap banyak kemungkinan nilai.

## Sintaks
```javascript
switch (ekspresi) {
    case nilai1:
        // Kode yang dijalankan jika ekspresi === nilai1
        break;
    case nilai2:
        // Kode yang dijalankan jika ekspresi === nilai2
        break;
    // Tambahkan lebih banyak case sesuai kebutuhan
    default:
        // Kode yang dijalankan jika tidak ada case yang cocok
}
```

## Contoh Penggunaan
### 1. Menentukan Nama Hari Berdasarkan Angka
```javascript
let hari = 8;
let namaHari;

switch (hari) {
    case 1:
        namaHari = 'Senin';
        break;
    case 2:
        namaHari = 'Selasa';
        break;
    case 3:
        namaHari = 'Rabu';
        break;
    case 4:
        namaHari = 'Kamis';
        break;
    case 5:
        namaHari = "Jum'at";
        break;
    case 6:
        namaHari = 'Sabtu';
        break;
    case 7:
        namaHari = 'Minggu';
        break;
    default:
        namaHari = 'Nama hari tidak valid';
}

console.log(namaHari);
```
### 2. Switch-Case dengan Ekspresi atau Operasi Logika
```javascript
let nilai = 51;

switch (true) {
    case nilai >= 90:
        console.log('Nilai A');
        break;
    case nilai >= 80:
        console.log('Nilai B');
        break;
    case nilai >= 70:
        console.log('Nilai C');
        break;
    case nilai >= 60:
        console.log('Nilai D');
        break;
    default:
        console.log('Nilai E');
}
```

## Catatan Penting
### 1. **Eksekusi Tanpa Break**
Jika kamu tidak menempatkan `break` setelah setiap case, maka semua case di bawahnya akan dijalankan (*fall-through*) hingga menemukan `break` atau akhir dari switch-case.

### 2. **Switch-Case dengan Tipe Data String**
Selain angka, switch-case juga bisa digunakan untuk membandingkan string.
```javascript
let warna = "merah";

switch (warna) {
    case "merah":
        console.log("Warna favorit saya merah!");
        break;
    case "biru":
        console.log("Warna favorit saya biru!");
        break;
    default:
        console.log("Saya tidak memiliki warna favorit!");
}
```

## Kelebihan & Kekurangan
### ✅ **Kelebihan:**
- Lebih mudah dibaca dibandingkan dengan rantai if-else panjang.
- Cocok digunakan saat ada banyak kemungkinan nilai yang harus diperiksa.

### ❌ **Kekurangan:**
- Kurang fleksibel dibandingkan if-else saat membandingkan dengan kondisi kompleks.
- Rentan terhadap kesalahan jika `break` terlewat.

## Kesimpulan
Switch-case adalah cara yang lebih terstruktur dan mudah dibaca untuk menangani banyak kemungkinan nilai dari sebuah variabel. Namun, harus digunakan dengan hati-hati agar tidak mengalami kesalahan akibat lupa menambahkan `break` atau salah dalam membandingkan ekspresi.

