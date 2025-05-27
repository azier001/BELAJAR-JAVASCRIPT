# 📘 Dokumentasi Belajar: Pengenalan API

---

## Apa Itu API?

**API (Application Programming Interface)** memungkinkan pengembang untuk berinteraksi dengan aplikasi lain tanpa mengetahui detail implementasi internalnya. API menyediakan cara standar untuk:

* Mengambil data dari server
* Mengirim data ke server
* Autentikasi pengguna
* Mengakses layanan pihak ketiga (misalnya Google Maps, OpenWeather, dsb)

### Dua Komponen Penting dalam API:

* **REST API (Representational State Transfer)**
  API berbasis HTTP yang umum digunakan dalam komunikasi antara klien dan server.

* **JSON (JavaScript Object Notation)**
  Format data ringan dan mudah dibaca yang digunakan untuk bertukar data antar sistem.

---

## HTTP Request Methods

Metode umum yang digunakan dalam permintaan HTTP:

| Metode | Deskripsi                           |
| ------ | ----------------------------------- |
| GET    | Mengambil data dari server          |
| POST   | Mengirim data baru ke server        |
| PUT    | Memperbarui data yang ada di server |
| DELETE | Menghapus data dari server          |

---

## HTTP Status Code

Kode status dikembalikan oleh server sebagai respon atas permintaan:

| Kode | Arti                                     |
| ---- | ---------------------------------------- |
| 200  | OK – Permintaan berhasil                 |
| 201  | Created – Data berhasil dibuat           |
| 400  | Bad Request – Permintaan tidak valid     |
| 401  | Unauthorized – Autentikasi gagal         |
| 403  | Forbidden – Akses ditolak                |
| 404  | Not Found – Sumber tidak ditemukan       |
| 500  | Internal Server Error – Kesalahan server |

---

## fetch() API

`fetch()` adalah cara modern dan berbasis promise untuk mengirim permintaan HTTP.

### Contoh: GET Data

```javascript
fetch('https://jsonplaceholder.typicode.com/posts/1')
  .then((response) => {
    if (!response.ok) {
      throw new Error(`Network response not ok`);
    }
    return response.json();
  })
  .then((data) => {
    console.log(data);
  })
  .catch((error) => {
    console.error(`Error: ${error}`);
  });
```

**Output:**

```json
{
  "userId": 1,
  "id": 1,
  "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  "body": "quia et suscipit..."
}
```

---

### POST Data dengan fetch()

```javascript
const postData = {
  title: 'New Post',
  body: 'This is the body of the new post',
  userId: 1,
};

fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  body: JSON.stringify(postData),
  headers: {
    'Content-type': 'application/json',
  },
})
  .then((response) => response.json())
  .then((data) => {
    console.log('Data posted:', data);
  })
  .catch((error) => {
    console.error('Error posting data:', error);
  });
```

**Output:**

```json
{
  "title": "New Post",
  "body": "This is the body of the new post",
  "userId": 1,
  "id": 101
}
```

---

## Autentikasi Menggunakan Token

```javascript
const token = 'YOUR_ACCESS_TOKEN';

fetch('https://api.example.com/user/profile', {
  method: 'GET',
  headers: {
    'Authorization': `Bearer ${token}`,
  },
})
  .then((res) => res.json())
  .then((data) => console.log(data))
  .catch((err) => console.error('Auth error:', err));
```

**Output (contoh):**

```json
{
  "id": 1,
  "name": "John Doe",
  "email": "john@example.com"
}
```

---

## Error Handling yang Lebih Baik

```javascript
function handleResponse(response) {
  if (!response.ok) {
    throw new Error(`HTTP error! status: ${response.status}`);
  }
  return response.json();
}

fetch('https://jsonplaceholder.typicode.com/posts/1')
  .then(handleResponse)
  .then((data) => console.log(data))
  .catch((error) => console.error('Error:', error.message));
```

**Kemungkinan Output:**

```json
{
  "userId": 1,
  "id": 1,
  "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  "body": "quia et suscipit..."
}
```

Jika error:

```bash
Error: HTTP error! status: 404
```

---

## Kesimpulan

Dengan memahami API, HTTP methods, status code, dan penggunaan `fetch()`, kita dapat:

* Membaca/mengambil data dari server
* Menambahkan atau mengedit data
* Mengelola autentikasi
* Menangani error secara efisien

API adalah komponen kunci dalam pengembangan aplikasi modern berbasis web.
