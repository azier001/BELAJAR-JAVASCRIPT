
# 📘 Penjelasan REST API untuk Pemula

## Apa itu REST API?

**REST API** adalah singkatan dari **Representational State Transfer - Application Programming Interface**.

REST API adalah **cara aplikasi berkomunikasi melalui internet menggunakan protokol HTTP** (seperti yang digunakan saat kamu membuka website).  
REST API biasanya digunakan untuk **mengambil, menambah, mengubah, atau menghapus data dari server**.

---

## 🎯 Analogi REST API dalam Kehidupan Nyata

### ✅ Contoh: Aplikasi Pemesanan Makanan Online

Bayangkan kamu menggunakan aplikasi untuk memesan makanan:

- Kamu melihat daftar restoran → aplikasi **mengambil data** dari server (GET)
- Kamu memilih makanan dan memesan → aplikasi **mengirim data pesanan** ke server (POST)
- Kamu mengubah pesanan → aplikasi **mengubah data** di server (PUT/PATCH)
- Kamu membatalkan pesanan → aplikasi **menghapus data** di server (DELETE)

Semua proses ini dilakukan lewat REST API, yang menjadi **jembatan antara aplikasi di ponselmu dan server restoran**.

---

## 🧱 Komponen Dasar REST API

### 1. **Endpoint**
Alamat URL untuk mengakses data tertentu.
Contoh:  
`https://api.example.com/users`

### 2. **HTTP Method**
Digunakan untuk menentukan aksi apa yang dilakukan terhadap data:
- `GET` → Mengambil data
- `POST` → Menambahkan data
- `PUT` → Mengubah seluruh data
- `PATCH` → Mengubah sebagian data
- `DELETE` → Menghapus data

### 3. **Request dan Response**
- **Request**: permintaan dari klien (misalnya aplikasi atau browser)
- **Response**: jawaban dari server, biasanya dalam format JSON

---

## 📦 Contoh Penggunaan REST API

### Contoh: Ambil daftar pengguna

```http
GET https://api.example.com/users
```

Respon dari server:

```json
[
  {
    "id": 1,
    "nama": "Ali",
    "email": "ali@example.com"
  },
  {
    "id": 2,
    "nama": "Siti",
    "email": "siti@example.com"
  }
]
```

---

## 🌍 Ciri-Ciri REST API

1. **Stateless**  
   Setiap permintaan tidak bergantung pada permintaan sebelumnya.

2. **Menggunakan HTTP**  
   REST API bekerja menggunakan protokol HTTP (GET, POST, dll).

3. **Data format umum: JSON**  
   REST API biasanya mengirim dan menerima data dalam format JSON karena ringan dan mudah dibaca.

4. **Memiliki struktur URL yang rapi (endpoint)**  
   Contoh:
   - `GET /produk` → ambil semua produk
   - `GET /produk/1` → ambil produk dengan id 1
   - `POST /produk` → tambah produk baru

---

## 💡 Kenapa REST API Populer?

- **Mudah digunakan dan dipahami**
- **Ringan dan cepat**
- **Kompatibel dengan hampir semua bahasa pemrograman**
- **Cocok untuk aplikasi web & mobile**

---

## 🧠 Kesimpulan

- REST API adalah **cara standar aplikasi berkomunikasi lewat internet menggunakan HTTP**.
- REST API digunakan untuk **mengelola data** di server (ambil, tambah, ubah, hapus).
- REST API sangat umum digunakan di dunia pengembangan software modern.

---

## 📎 Tips Belajar REST API

- Gunakan tools seperti **Postman** untuk mencoba request tanpa membuat aplikasi.
- Coba akses REST API gratis seperti:
  - https://jsonplaceholder.typicode.com
  - https://reqres.in
- Pelajari format **JSON** karena sangat sering digunakan di REST API.

