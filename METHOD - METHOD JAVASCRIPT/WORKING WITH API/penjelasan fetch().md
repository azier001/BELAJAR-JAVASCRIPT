# 📘 Belajar `fetch` di JavaScript

## Apa itu `fetch`?

`fetch` adalah fungsi bawaan di JavaScript yang digunakan untuk mengambil data dari server atau API. Fungsi ini bekerja secara asynchronous dan menggunakan konsep Promise.

---

## Sintaks Dasar

```javascript
fetch(url, options)
  .then(response => response.json())
  .then(data => {
    // proses data
  })
  .catch(error => {
    // tangani error
  });
```

### Parameter:
- `url`: string, alamat API atau file yang ingin diambil.
- `options`: objek (opsional) seperti method (GET, POST), headers, dan body.

---

## Contoh Penggunaan

### Mengambil data dari API publik:

```javascript
fetch('https://jsonplaceholder.typicode.com/posts/1')
  .then(response => response.json())
  .then(data => {
    console.log("Judul:", data.title);
    console.log("Isi:", data.body);
  })
  .catch(error => {
    console.error("Terjadi error:", error);
  });
```

### Output:

```
Judul: sunt aut facere repellat provident occaecati excepturi optio reprehenderit
Isi: quia et suscipit
suscipit recusandae consequuntur expedita et cum
reprehenderit molestiae ut ut quas totam
nostrum rerum est autem sunt rem eveniet architecto
```

---

## Versi Modern dengan `async/await`

```javascript
async function ambilData() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/posts/1');
    const data = await response.json();
    console.log("Judul:", data.title);
    console.log("Isi:", data.body);
  } catch (error) {
    console.error("Terjadi error:", error);
  }
}

ambilData();
```

---

## Tips

- Selalu gunakan `.catch()` atau `try/catch` untuk menangani error.
- Gunakan `response.ok` untuk mengecek status respons:

```javascript
if (!response.ok) {
  throw new Error('Network response was not ok');
}
```

---

## Referensi

- [MDN Web Docs - fetch()](https://developer.mozilla.org/en-US/docs/Web/API/fetch)
- [JSONPlaceholder - API Dummy](https://jsonplaceholder.typicode.com/)

---

## Penggunaan Parameter `options` di `fetch`

`fetch` bisa menerima parameter kedua berupa objek `options` untuk mengatur jenis request seperti `POST`, `PUT`, `DELETE`, dan sebagainya.

### Struktur Umum `options`

```javascript
{
  method: 'POST', // atau 'GET', 'PUT', 'DELETE'
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(data) // data yang akan dikirim ke server
}
```

---

## Contoh: Mengirim Data dengan Method POST

```javascript
const data = {
  title: 'Belajar Fetch',
  body: 'Ini adalah konten belajar menggunakan fetch dengan method POST',
  userId: 1
};

fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(data)
})
  .then(response => response.json())
  .then(data => {
    console.log("Respons dari server:", data);
  })
  .catch(error => {
    console.error("Terjadi error:", error);
  });
```

### Output:

```
Respons dari server: {
  id: 101,
  title: 'Belajar Fetch',
  body: 'Ini adalah konten belajar menggunakan fetch dengan method POST',
  userId: 1
}
```

---

## Catatan Penting

- `Content-Type: application/json` penting agar server tahu bahwa data yang dikirim berbentuk JSON.
- `body` hanya digunakan untuk method seperti `POST`, `PUT`, atau `PATCH`, bukan untuk `GET`.

