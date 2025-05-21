
# Asynchronous JavaScript untuk Pemula

## Pendahuluan

JavaScript secara default adalah **single-threaded** dan berjalan secara **synchronous**, yang berarti kode dieksekusi satu per satu — setiap baris harus selesai sebelum baris berikutnya dapat dijalankan.

Namun, dalam banyak situasi, kita **tidak ingin program berhenti menunggu operasi selesai**, seperti saat mengambil data dari server atau membaca file besar. Untuk mengatasi hal ini, JavaScript menyediakan cara untuk menangani **operasi secara asynchronous**, sehingga tugas-tugas berat dapat diproses di latar belakang **tanpa menghentikan eksekusi kode lainnya**.

---

## Kenapa Asynchronous?

JavaScript adalah bahasa pemrograman **synchronous dan blocking** secara default. Artinya, ia menjalankan kode dari atas ke bawah, satu baris demi satu baris, dan tidak akan melanjutkan ke baris berikutnya sampai baris saat ini selesai dieksekusi.

```javascript
console.log('Start');
for (let i = 0; i < 1000000; i++) {} // Loop berat
console.log('End');
```

### Output:
```
Start
End
```

> **Penjelasan**: Program akan mencetak `'Start'`, kemudian menjalankan loop berat (yang memakan waktu), lalu baru mencetak `'End'`. Tidak ada operasi lain yang bisa dilakukan selama loop berlangsung.

---

## Apa itu Blocking?

**Blocking** terjadi ketika sebuah operasi **menghalangi eksekusi kode lain sampai operasi tersebut selesai**. Karena JavaScript bersifat synchronous, operasi berat seperti **permintaan data dari server atau membaca file besar** bisa memblokir eksekusi kode lainnya.

Contoh:

```javascript
console.log('Start');
for (let i = 0; i < 1000000; i++) {} // Operasi blocking
console.log('End');
```

### Output:
```
Start
End
```

> Selama loop berjalan, semua eksekusi lain akan **tertunda** hingga loop selesai.

---

## Apa itu Single-threaded?

JavaScript menggunakan model **single-threaded**: hanya satu jalur (thread) untuk mengeksekusi semua kode. Artinya, hanya satu tugas yang bisa dijalankan pada satu waktu.

**Konsekuensi dari single-threaded:**

1. **UI menjadi tidak responsif** jika ada kode berat.
2. **Efisiensi rendah**, karena semua tugas dijalankan satu per satu.

---

## Mengapa Menggunakan Asynchronous JavaScript?

Untuk mengatasi keterbatasan single-threaded dan blocking, kita dapat menggunakan **asynchronous JavaScript**.

Asynchronous memungkinkan:
- Menjalankan tugas berat **di latar belakang**.
- **Kode lain tetap berjalan** sementara menunggu operasi asynchronous selesai.

> Contoh masalah: Jika aplikasi web mengambil data dari server secara synchronous, browser akan **"freeze"** dan pengguna tidak dapat berinteraksi hingga data selesai diambil.

---

## Asynchronous JavaScript

Dengan asynchronous, JavaScript bisa menjalankan operasi **tanpa memblokir thread utama**. Ini dilakukan menggunakan:

- **Callback**
- **Promises**
- **async / await**

Contoh penggunaan `setTimeout` (asynchronous):

```javascript
console.log('Start');

setTimeout(() => {
  console.log('This is asynchronous code');
}, 2000); // Menunggu 2 detik

console.log('End');
```

### Output:
```
Start
End
This is asynchronous code
```

> Penjelasan: Meskipun `setTimeout` menunggu 2 detik, kode `'End'` tetap dieksekusi **tanpa menunggu**.

---

## Kesimpulan

- JavaScript bersifat **single-threaded** dan **synchronous** secara default.
- Operasi berat bisa menyebabkan **blocking** dan membuat aplikasi tidak responsif.
- **Asynchronous JavaScript** memungkinkan kode berat dijalankan di latar belakang.
- Gunakan teknik seperti **callback**, **Promises**, dan **async/await** untuk membuat aplikasi tetap responsif.

