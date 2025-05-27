
# 📘 Panduan Lengkap `JSON.stringify()` dalam JavaScript

## 🔍 Apa Itu `JSON.stringify()`

`JSON.stringify()` adalah **method bawaan JavaScript** yang digunakan untuk mengubah **objek JavaScript** menjadi **string JSON** (JavaScript Object Notation).

---

## 🧠 Kenapa Kita Perlu `JSON.stringify()`

Object JavaScript **tidak bisa langsung disimpan atau dikirim**. Untuk mengirim data ke server, menyimpannya di `localStorage`, atau menampilkan di UI, kita perlu mengubahnya menjadi string dalam format JSON.

---

## 💡 Sintaks Dasar

```javascript
JSON.stringify(value[, replacer[, space]])
```

- `value`: Data yang ingin diubah menjadi string JSON.
- `replacer` (opsional): Fungsi/filter untuk memilih properti yang disertakan.
- `space` (opsional): Jumlah spasi/indentasi untuk mempercantik tampilan JSON.

---

## 📦 Contoh Kasus Nyata

### 1. ✅ Menyimpan Data ke localStorage

Tanpa `JSON.stringify()`:
```javascript
const user = { name: "Budi", age: 25, isMember: true };
localStorage.setItem("userData", user); // ❌ Menyimpan [object Object]
```

Dengan `JSON.stringify()`:
```javascript
const user = { name: "Budi", age: 25, isMember: true };
const jsonUser = JSON.stringify(user);
localStorage.setItem("userData", jsonUser); // ✅ Aman disimpan
```

### 2. 📥 Membaca Kembali Data dari localStorage

```javascript
const savedUser = localStorage.getItem("userData");
const parsedUser = JSON.parse(savedUser); // ✅ Ubah kembali ke objek
console.log(parsedUser.name); // Output: Budi
```

---

### 3. 📡 Mengirim Data ke Server via Fetch API

```javascript
const order = {
  item: "Kopi",
  qty: 2,
  notes: "Tanpa gula"
};

fetch("https://example.com/api/order", {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify(order)
});
```

Tanpa `JSON.stringify()`, data tidak akan terkirim dalam format JSON.

---

## ❓ json.stringify() vs JSON.stringify()

| Penulisan         | Status  | Penjelasan                                                                 |
|-------------------|---------|---------------------------------------------------------------------------|
| `JSON.stringify()` | ✅ Benar | JSON adalah built-in object (harus huruf kapital semua)                   |
| `json.stringify()` | ❌ Salah | `json` dianggap sebagai variabel biasa yang belum didefinisikan (error)  |

```javascript
// ❌ Salah:
json.stringify({}) // Error: json is not defined

// ✅ Benar:
JSON.stringify({})
```

---

## 🧯 Fungsi Kebalikannya

Gunakan `JSON.parse()` untuk mengubah string JSON kembali menjadi objek JavaScript:

```javascript
const str = '{"name":"Budi","age":25}';
const obj = JSON.parse(str);
console.log(obj.name); // Output: Budi
```

---

## 📌 Kesimpulan

| Aspek                      | Penjelasan                                    |
|---------------------------|-----------------------------------------------|
| Fungsi                    | Mengubah objek ke string JSON                 |
| Kapan digunakan           | Saat menyimpan data, mengirim ke server, dll  |
| Hasil                     | Tipe data string                              |
| Penulisan yang benar      | `JSON.stringify()`                            |
| Fungsi kebalikannya       | `JSON.parse()`                                |

---

> 💡 Tips: Gunakan `JSON.stringify(obj, null, 2)` agar hasil JSON lebih mudah dibaca dengan indentasi 2 spasi.
