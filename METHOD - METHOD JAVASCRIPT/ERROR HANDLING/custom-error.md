# Membuat Custom Error di JavaScript

Dalam JavaScript, kita bisa membuat *custom error* (kesalahan buatan sendiri) dengan mendefinisikan sebuah kelas yang mewarisi dari kelas `Error`. Ini sangat berguna untuk membuat pesan kesalahan yang lebih spesifik dan sesuai dengan kebutuhan aplikasi.

---

## 📌 Contoh 1: Error Biasa

```javascript
let num = 123;

try {
  if (num === 123) {
    throw new Error('num tidak boleh bernilai 123');
  }
} catch (error) {
  console.error(`Error : ${error.message}`);
}
```

💡 **Output:**
```
Error : num tidak boleh bernilai 123
```

Penjelasan:

- Kita menggunakan `throw new Error(...)` untuk memunculkan kesalahan.
- Error yang dilempar adalah bawaan dari JavaScript (`Error` class standar).
- Pesan kesalahan dapat dibaca melalui properti `.message`.

---

## 📌 Contoh 2: Custom Error (Error Buatan Sendiri)

```javascript
let number = 123;

class CustomError extends Error {
  constructor(message) {
    super(message); // Memanggil constructor dari kelas Error
    this.name = 'Custom Error'; // Menentukan nama error sendiri
  }
}

try {
  if (number === 123) {
    throw new CustomError('number tidak boleh bernilai 123');
  }
} catch (error) {
  console.error(`Nama Error : ${error.name}`);
  console.error(`Message Error : ${error.message}`);
}
```

💡 **Output:**
```
Nama Error : Custom Error
Message Error : number tidak boleh bernilai 123
```

Penjelasan:

- `CustomError` adalah kelas yang mewarisi dari `Error`.
- `super(message)` memanggil constructor dari `Error` untuk menyimpan pesan.
- Kita bisa mengganti nama error dengan menetapkan `this.name`.
- Dengan cara ini, kita bisa membedakan berbagai jenis kesalahan dalam aplikasi.

---

## ✅ Kapan Harus Menggunakan Custom Error?

Gunakan *custom error* ketika:

- Ingin membedakan jenis error berdasarkan nama (`.name`).
- Ingin memberikan konteks spesifik terhadap kesalahan (misalnya validasi input, koneksi database, otorisasi).
- Ingin membuat *error handling* lebih modular dan mudah dipelihara.

---

## ✨ Tips Tambahan

### Menambahkan Properti Tambahan pada Error

```javascript
class ValidationError extends Error {
  constructor(message, field) {
    super(message);
    this.name = 'ValidationError';
    this.field = field;
  }
}

try {
  throw new ValidationError('Username tidak valid', 'username');
} catch (error) {
  console.error(`${error.name} pada field ${error.field}: ${error.message}`);
}
```

💡 **Output:**
```
ValidationError pada field username: Username tidak valid
```

Dengan menambahkan properti seperti `field`, kita bisa memberikan informasi tambahan yang bisa digunakan saat debugging atau logging.

---

## 📚 Kesimpulan

- `Error` adalah kelas dasar untuk semua jenis error di JavaScript.
- Kita bisa membuat *custom error* dengan cara mewarisi dari kelas `Error`.
- Custom error memudahkan kita untuk menangani kesalahan yang lebih terstruktur dan bermakna dalam aplikasi.

---

## 🔗 Referensi

- [MDN Web Docs - Error](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error)
- [JavaScript.info - Custom Errors](https://javascript.info/custom-errors)
