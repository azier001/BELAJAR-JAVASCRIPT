# 📘 Error Handling di JavaScript

Error handling adalah proses menangani kesalahan dalam kode agar aplikasi tidak crash atau berhenti secara tiba-tiba. JavaScript menyediakan beberapa cara untuk menangani error, seperti:

- Menggunakan `try ... catch`
- Menggunakan `finally`
- Membuat *custom error*
- Menangani error dalam kode asynchronous (misalnya dengan `async/await` dan `Promise`)

---

## 🔹 Try ... Catch ... Finally

`try ... catch ... finally` adalah cara paling umum untuk menangani error di JavaScript.

### Struktur:

```js
try {
  // kode yang berpotensi menimbulkan error
} catch (error) {
  // kode untuk menangani error
} finally {
  // kode yang akan selalu dijalankan
}
```

- **`try`**: Tempat menaruh kode yang ingin diuji.
- **`catch`**: Menangani error jika terjadi di dalam blok `try`.
- **`finally`** *(opsional)*: Selalu dijalankan, baik terjadi error maupun tidak.

### Contoh:

```js
let number = 123;

try {
  if (number == 123) {
    throw new Error('Nomor 123 tidak diperbolehkan');
  }
  console.log(number);
} catch (err) {
  console.error(`Error terjadi: ${err.message}`);
} finally {
  console.log('Ini akan selalu dijalankan');
}
```

#### Output:

```
Error terjadi: Nomor 123 tidak diperbolehkan
Ini akan selalu dijalankan
```

### Penjelasan:

- Kode dalam blok `try` dijalankan terlebih dahulu.
- Jika terjadi error, eksekusi langsung berpindah ke blok `catch`.
- Objek `error` menyimpan informasi seperti `message`.
- Blok `finally` akan **selalu** dijalankan, bahkan jika ada `return` di `try` atau `catch`.

---

## 🔸 Custom Error dengan `throw`

`throw` digunakan untuk membuat error kustom, yang berguna ketika ingin memvalidasi kondisi tertentu dan memberikan pesan error sendiri.

### Contoh:

```js
function divide(a, b) {
  if (b === 0) {
    throw new Error('Pembagian dengan 0 tidak diperbolehkan');
  }

  return a / b;
}

try {
  let result = divide(10, 0);
  console.log(result);
} catch (error) {
  console.error('Error:', error.message);
}
```

#### Output:

```
Error: Pembagian dengan 0 tidak diperbolehkan
```

### Penjelasan:

- `throw` digunakan untuk **melempar error secara manual**.
- Dalam contoh di atas, error dilempar jika nilai pembagi (`b`) adalah `0`.

---

## 🧠 Catatan Tambahan

- `catch` tidak harus menggunakan nama `error`, bisa diganti dengan nama lain seperti `err`, `e`, dll.
- Selalu usahakan untuk memberikan pesan error yang jelas agar mudah untuk debugging.
- Untuk menangani error dalam kode asynchronous, gunakan `try...catch` di dalam `async` function.

---

## ✅ Kesimpulan

| Fitur       | Fungsi                                                                 |
|-------------|------------------------------------------------------------------------|
| `try`       | Menjalankan blok kode yang mungkin menghasilkan error.                |
| `catch`     | Menangkap dan menangani error yang terjadi pada blok `try`.           |
| `finally`   | Menjalankan kode tertentu terlepas dari hasil `try` atau `catch`.     |
| `throw`     | Melempar error secara manual sesuai kondisi yang ditentukan sendiri.  |
