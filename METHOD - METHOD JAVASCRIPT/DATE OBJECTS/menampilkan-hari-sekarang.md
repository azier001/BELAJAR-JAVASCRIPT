# Menampilkan Hari Sekarang dengan JavaScript

Dokumentasi singkat untuk menampilkan nama hari (contoh: "Hari ini hari Rabu") menggunakan JavaScript.

## 📌 Tujuan

Mengetahui dan menampilkan hari sekarang dalam format teks yang mudah dibaca.

## 💡 Kode JavaScript

```javascript
// Ambil tanggal hari ini
const hariIni = new Date();

// Array nama-nama hari
const namaHari = ["Minggu", "Senin", "Selasa", "Rabu", "Kamis", "Jumat", "Sabtu"];

// Ambil indeks hari dan tampilkan
const indeksHari = hariIni.getDay();
console.log("Hari ini hari " + namaHari[indeksHari]);
```

## 📝 Contoh Output

Jika dijalankan pada hari Jumat:

```
Hari ini hari Jumat
```

## 🧠 Penjelasan

- `new Date()` membuat objek tanggal saat ini.
- `getDay()` mengambil indeks hari dalam minggu (0 = Minggu, 6 = Sabtu).
- Array `namaHari` digunakan untuk mengubah angka ke nama hari yang sesuai.
- `console.log` digunakan untuk menampilkan hasil ke konsol.

