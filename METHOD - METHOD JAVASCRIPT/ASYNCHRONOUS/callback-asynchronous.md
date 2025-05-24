
# Callback Functions dalam JavaScript

## Apa itu Callback Function?

**Callback Function** adalah fungsi yang dikirim sebagai argumen ke fungsi lain dan dipanggil di dalam fungsi tersebut setelah tugas tertentu selesai.

Callback sangat berguna terutama dalam penanganan **asynchronous operation** seperti pengambilan data dari server, membaca file, atau operasi lainnya yang memerlukan waktu.

---

## Contoh Callback Function Sederhana

```javascript
function selesaikanTugas(tugas, callback) {
  console.log(`Menyelesaikan tugas: ${tugas}`);
  callback();
}

function tugasSelesai() {
  console.log(`Tugas sudah selesai`);
}

selesaikanTugas('Belajar JavaScript', tugasSelesai);
```

### Output:
```
Menyelesaikan tugas: Belajar JavaScript
Tugas sudah selesai
```

---

## Contoh Callback Function Asynchronous

Misalkan kita ingin mengambil data pengguna dari server. Karena proses pengambilan data ini memerlukan waktu, kita bisa mensimulasikannya dengan `setTimeout`.

```javascript
function getData(callback) {
  console.log('Fetching data user...');

  // Simulasi pengambilan data dari server yang memerlukan waktu 2 detik
  setTimeout(() => {
    const userData = {
      id: 1,
      name: 'Ahmad',
      email: 'ahmad@gmail.com',
    };

    // Callback ketika data berhasil diperoleh
    callback(null, userData);

    // Jika ingin simulasi kegagalan:
    // callback('Koneksi gagal', null);
  }, 2000);
}

function displayUserData(error, data) {
  if (error) {
    console.error('Error fetching data:', error);
  } else {
    console.log('User data:', data);
  }
}

getData(displayUserData);
```

### Output:
```
Fetching data user...
// setelah 2 detik
User data: { id: 1, name: 'Ahmad', email: 'ahmad@gmail.com' }
```

Jika callback dipanggil dengan error:
```javascript
callback('Koneksi gagal', null);
```

### Output:
```
Fetching data user...
// setelah 2 detik
Error fetching data: Koneksi gagal
```

---

## Penjelasan Tambahan

- **Synchronous**: Kode dieksekusi baris demi baris, menunggu hingga operasi selesai.
- **Asynchronous**: Kode tidak menunggu, melanjutkan eksekusi berikutnya sembari menunggu operasi seperti I/O selesai.

Callback digunakan untuk menangani operasi asynchronous agar kode tetap berjalan tanpa harus menunggu, tapi tetap bisa memproses data setelah tersedia.

---

## Catatan Penting tentang Callback

- Callback membantu menghindari **blocking code**.
- Callback dapat menyebabkan **callback hell** jika terlalu dalam atau bertingkat.
- Untuk menghindari callback hell, bisa menggunakan **Promise** atau **async/await**.

---

## Referensi Lanjutan

- [MDN Web Docs - Callback Function](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)
- [JavaScript.info - Callback](https://javascript.info/callbacks)


