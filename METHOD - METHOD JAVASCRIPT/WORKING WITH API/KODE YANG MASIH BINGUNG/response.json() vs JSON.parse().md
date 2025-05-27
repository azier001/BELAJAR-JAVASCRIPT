
# 📄 `response.json()` vs `JSON.parse()` dalam JavaScript

---

## 📌 1. Apa itu `.then((response) => response.json())`

Kode ini umum digunakan dalam JavaScript saat mengambil data dari server menggunakan `fetch()`:

```javascript
fetch('https://api.example.com/data')
  .then((response) => response.json())
  .then((data) => {
    console.log(data);
  });
```

### Penjelasan:

- `fetch()` mengembalikan **Promise** berisi **Response object**.
- `response.json()` akan mengubah **response body** (yang masih berupa teks JSON) menjadi **objek JavaScript asli**.
- Ini berguna agar kita bisa memanipulasi data tersebut secara langsung di JavaScript.

---

## 📌 2. Analogi Dunia Nyata

Misalnya kamu pesan makanan dari aplikasi, dan data dari server berupa JSON:

```json
{
  "nama": "Nasi Goreng",
  "harga": 20000
}
```

Maka kode JavaScript-nya:

```javascript
fetch('https://api.makanan.com/pesanan')
  .then((response) => response.json())
  .then((data) => {
    console.log(data.nama);  // Output: Nasi Goreng
    console.log(data.harga); // Output: 20000
  });
```

Tanpa `.json()`, kamu tidak bisa langsung mengakses properti `data.nama` karena datanya belum menjadi objek JavaScript.

---

## 📌 3. Perbedaan `response.json()` vs `JSON.parse()`

| Fitur              | `response.json()`                                  | `JSON.parse()`                             |
|-------------------|-----------------------------------------------------|--------------------------------------------|
| Input              | `Response` dari `fetch()`                          | String JSON biasa                          |
| Keluaran           | Objek JavaScript (dalam Promise)                   | Objek JavaScript langsung                  |
| Sifat              | Asynchronous (mengembalikan Promise)              | Synchronous (langsung mengembalikan data) |
| Kapan digunakan?   | Saat menggunakan `fetch()`                         | Saat sudah punya string JSON               |
| Contoh             | `fetch().then(r => r.json())`                      | `JSON.parse('{"nama":"Roti"}')`           |

### Contoh `JSON.parse()`:

```javascript
let jsonString = '{"nama": "Es Teh", "harga": 5000}';
let data = JSON.parse(jsonString);
console.log(data.nama); // "Es Teh"
```

---

## 📌 4. Hati-hati: `response.JSON()` adalah SALAH

JavaScript **case-sensitive**, jadi:

- ✅ Benar: `response.json()`
- ❌ Salah: `response.JSON()` → akan menyebabkan error

---

## ✅ Ringkasan

- Gunakan `.json()` untuk mengurai hasil `fetch()` menjadi objek.
- Gunakan `JSON.parse()` untuk mengurai **string JSON** manual.
- Jangan gunakan `response.JSON()` (huruf kapital) karena tidak ada method tersebut.
- Pastikan selalu menunggu hasil `.json()` dengan `await` atau `.then()` karena sifatnya asynchronous.
