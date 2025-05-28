
# Belajar `async`/`await` dan `fetch()` di JavaScript


## 📚 Dasar `async` dan `await`

### 🔹 Fungsi `async`

`async` digunakan untuk mendeklarasikan fungsi asynchronous. Fungsi ini secara otomatis akan mengembalikan promise.

```javascript
async function namaFungsi() {
  // kode asynchronous di sini
}
```

### 🔹 Kata kunci `await`

`await` digunakan di dalam fungsi `async` untuk menunggu promise selesai sebelum melanjutkan ke baris kode berikutnya.

```javascript
const hasil = await promise;
```

> **Catatan:** `await` hanya bisa digunakan di dalam fungsi yang dideklarasikan dengan `async`.

---

## 🌐 Contoh Penggunaan `fetch()` dengan `async`/`await`

```javascript
// Menggunakan async await dengan fetch()
// Dengan async await, kode kita menjadi lebih mudah dibaca dan ditulis, terutama saat menangani operasi asynchronous.

async function getPost() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/posts/1');

    if (!response.ok) {
      throw new Error(`Network response was not ok`);
    }

    const data = await response.json();
    console.log('Data fetched using async await :', data);
  } catch (error) {
    console.error('Error fetching data :', error);
  }
}

getPost();
```

### 🖥️ Output di Console (jika sukses):

```json
Data fetched using async await : {
  "userId": 1,
  "id": 1,
  "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum..."
}
```

---

## 🧠 Penjelasan Kode

- `async function getPost()`  
  Menandakan bahwa fungsi `getPost` adalah fungsi asynchronous.

- `await fetch(...)`  
  Menunggu hasil dari pemanggilan API sebelum lanjut ke baris berikutnya.

- `response.ok`  
  Mengecek apakah respons berhasil (status HTTP 200-299).

- `await response.json()`  
  Mengubah respons HTTP menjadi objek JavaScript.

- `try...catch`  
  Menangani error yang mungkin terjadi, seperti kegagalan jaringan.

---

## ✅ Keuntungan Menggunakan `async`/`await`

- Penulisan kode lebih **sederhana dan bersih** dibandingkan callback atau `.then()`.
- **Mudah dibaca** seperti kode synchronous.
- Mudah dalam penanganan **error** dengan `try...catch`.

---

## ⚠️ Tips Tambahan

- Selalu tangani error dengan `try...catch` saat menggunakan `await`.
- Jangan lupa untuk **mengecek `response.ok`** agar tahu jika ada error dari server.

---

## 📁 Struktur File yang Direkomendasikan

Simpan file ini sebagai:  
**`async-await-fetch.md`**

---

## 📌 Sumber Belajar Lanjutan

- [MDN Web Docs - async function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
- [MDN Web Docs - fetch API](https://developer.mozilla.org/en-US/docs/Web/API/fetch)
- [JavaScript Info - async/await](https://javascript.info/async-await)

