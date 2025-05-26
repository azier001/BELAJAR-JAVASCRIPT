# 📘 JSONPlaceholder Guide for Beginners

**JSONPlaceholder** adalah layanan **fake REST API** gratis untuk kebutuhan **testing** dan **prototyping** aplikasi frontend. Kamu bisa melakukan operasi `GET`, `POST`, `PUT`, `PATCH`, dan `DELETE` layaknya pada REST API sungguhan — namun data yang dikirim tidak benar-benar disimpan permanen di server.

---

## 📦 Daftar Resource

Beberapa resource yang tersedia:
- `/posts`
- `/comments`
- `/albums`
- `/photos`
- `/todos`
- `/users`

---

## 🚀 Contoh Penggunaan (dengan `fetch` API)

> Kamu bisa menyalin kode di bawah dan menjalankannya di **console browser** untuk langsung mencoba.

### 1. 🔍 Mendapatkan 1 Data (GET)

```js
fetch('https://jsonplaceholder.typicode.com/posts/1')
  .then((response) => response.json())
  .then((json) => console.log(json));
```

**Output:**

```json
{
  "id": 1,
  "title": "...",
  "body": "...",
  "userId": 1
}
```

---

### 2. 📃 Mendapatkan Semua Data (GET All)

```js
fetch('https://jsonplaceholder.typicode.com/posts')
  .then((response) => response.json())
  .then((json) => console.log(json));
```

**Output:**
```json
[
  { "id": 1, "title": "...", "body": "...", "userId": 1 },
  { "id": 2, "title": "...", "body": "...", "userId": 1 },
  ...
]
```

---

### 3. ➕ Membuat Data Baru (POST)

```js
fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  body: JSON.stringify({
    title: 'foo',
    body: 'bar',
    userId: 1,
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
  .then((response) => response.json())
  .then((json) => console.log(json));
```

**Output:**
```json
{
  "id": 101,
  "title": "foo",
  "body": "bar",
  "userId": 1
}
```

📝 *Catatan: Data ini tidak benar-benar disimpan, hanya dipalsukan seolah berhasil dibuat.*

---

### 4. 📝 Mengupdate Data (PUT)

```js
fetch('https://jsonplaceholder.typicode.com/posts/1', {
  method: 'PUT',
  body: JSON.stringify({
    id: 1,
    title: 'foo',
    body: 'bar',
    userId: 1,
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
  .then((response) => response.json())
  .then((json) => console.log(json));
```

**Output:**
```json
{
  "id": 1,
  "title": "foo",
  "body": "bar",
  "userId": 1
}
```

---

### 5. ✏️ Patch sebagian data (PATCH)

```js
fetch('https://jsonplaceholder.typicode.com/posts/1', {
  method: 'PATCH',
  body: JSON.stringify({
    title: 'foo',
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
  .then((response) => response.json())
  .then((json) => console.log(json));
```

**Output:**
```json
{
  "id": 1,
  "title": "foo",
  "body": "...",
  "userId": 1
}
```

---

### 6. ❌ Menghapus Data (DELETE)

```js
fetch('https://jsonplaceholder.typicode.com/posts/1', {
  method: 'DELETE',
});
```

📝 *Catatan: Data tidak benar-benar dihapus dari server.*

---

### 🔎 Filter Data

Kamu bisa menambahkan **query parameter** untuk memfilter data.

Contoh: Dapatkan semua postingan milik userId 1

```js
fetch('https://jsonplaceholder.typicode.com/posts?userId=1')
  .then((response) => response.json())
  .then((json) => console.log(json));
```

---

### 📂 Nested Resource

JSONPlaceholder juga mendukung nested route (1 level dalam):

```js
// Sama dengan /comments?postId=1
fetch('https://jsonplaceholder.typicode.com/posts/1/comments')
  .then((response) => response.json())
  .then((json) => console.log(json));
```

**Route nested lainnya:**
- `/posts/1/comments`
- `/albums/1/photos`
- `/users/1/albums`
- `/users/1/todos`
- `/users/1/posts`

---

