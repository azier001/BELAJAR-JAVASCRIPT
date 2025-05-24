
# Penjelasan Lengkap: Error-First Callback di JavaScript

## Apa itu Error-First Callback?

**Error-First Callback** adalah pola standar dalam JavaScript (terutama di Node.js) untuk menangani operasi asynchronous, seperti pengambilan data dari server, pembacaan file, atau pemrosesan database.

Pola ini disebut **error-first** karena parameter **pertama** pada callback selalu digunakan untuk **menangani error**, dan parameter **kedua** digunakan untuk **mengirim data hasil operasi** jika tidak ada error.

## Struktur Dasar

```javascript
function callback(err, result) {
  if (err) {
    // Tangani error
  } else {
    // Gunakan hasil (result)
  }
}
```

## Contoh Penerapan

```javascript
function ambilData(callback) {
  setTimeout(() => {
    const sukses = true;

    if (sukses) {
      callback(null, { id: 1, nama: "Ahmad" });
    } else {
      callback("Gagal mengambil data", null);
    }
  }, 1000);
}

function tampilkanHasil(err, data) {
  if (err) {
    console.error("Terjadi kesalahan:", err);
  } else {
    console.log("Data berhasil:", data);
  }
}

ambilData(tampilkanHasil);
```

### Output (jika `sukses = true`):

```
Data berhasil: { id: 1, nama: 'Ahmad' }
```

### Output (jika `sukses = false`):

```
Terjadi kesalahan: Gagal mengambil data
```

### Penjelasan

- `null` dikirim sebagai parameter pertama karena tidak ada error.
- Jika terjadi error, parameter pertama akan berisi pesan atau objek error, dan data (parameter kedua) akan `null`.

## Mengapa Tidak Dibalik?

Jika kamu menukar posisi, seperti:

```javascript
callback(data, null);
```

Maka callback kamu akan **salah menganggap `data` sebagai error**, dan bisa menghasilkan logika yang salah.

## Kenapa Menggunakan `null`?

- `null` secara eksplisit menyatakan bahwa **tidak ada error**.
- Lebih jelas daripada menggunakan `false`, `undefined`, atau string kosong.
- Ini adalah konvensi resmi yang diikuti oleh banyak pustaka JavaScript, termasuk Node.js core API.

## Kelebihan Pola Error-First Callback

- Konsisten dan mudah diprediksi
- Memisahkan penanganan error dan data
- Kompatibel dengan pustaka Node.js dan callback legacy

## Kekurangan

- Jika banyak operasi async bersarang, dapat menyebabkan **callback hell** (terlalu banyak indentasi dan kompleksitas).
- Solusi modern untuk ini adalah menggunakan **Promise** dan **async/await**.

---

## Kesimpulan

- Selalu tempatkan parameter error sebagai **argumen pertama** pada callback.
- Gunakan `null` untuk menunjukkan tidak ada error.
- Ikuti konvensi ini agar kode kamu mudah dibaca, di-debug, dan konsisten dengan ekosistem Node.js.
