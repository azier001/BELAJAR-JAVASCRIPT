
# 📘 Belajar JavaScript: Promises

## Apa itu Promise?

`Promise` adalah cara modern untuk menangani proses asynchronous (proses yang berjalan di latar belakang dan memerlukan waktu) dalam JavaScript. Dengan Promise, penulisan kode menjadi lebih rapi dan mudah dibaca dibandingkan dengan menggunakan **callback**.

## States (Keadaan) dalam Promise

Promise memiliki tiga state utama:

1. **Pending** – Promise masih dalam proses.
2. **Fulfilled** – Promise berhasil diselesaikan.
3. **Rejected** – Promise gagal dijalankan.

## Struktur Umum Promise

```javascript
const promise = new Promise((resolve, reject) => {
  // Proses asynchronous
  if (/* kondisi berhasil */) {
    resolve("Berhasil");
  } else {
    reject("Gagal");
  }
});
```

## Contoh: Mengecek Stok Produk

Berikut contoh penggunaan `Promise` untuk mengecek ketersediaan stok sebuah produk:

```javascript
function checkStock(product) {
  return new Promise((resolve, reject) => {
    console.log('Checking stock');

    setTimeout(() => {
      const stockAvailable = false;

      if (stockAvailable) {
        resolve(`Stock ${product} is available`);
      } else {
        reject(`Stock ${product} is out of stock`);
      }
    }, 2000);
  });
}

checkStock('Laptop')
  .then((message) => {
    console.log(message);
  })
  .catch((error) => {
    console.error(error);
  });
```

### Output:

```
Checking stock
Stock Laptop is out of stock
```

> **Catatan:** Karena `stockAvailable = false`, maka Promise akan masuk ke `.catch()` dan menampilkan pesan error.

---

## Kenapa Menggunakan Promise?

- Menghindari **callback hell**.
- Membuat kode lebih mudah dibaca dan dikelola.
- Dapat dikombinasikan dengan fitur `async`/`await` untuk penulisan yang lebih sederhana.

---

## Bonus: Promise dengan Async/Await

Contoh di atas bisa ditulis ulang menggunakan `async/await`:

```javascript
async function check() {
  try {
    const result = await checkStock('Laptop');
    console.log(result);
  } catch (error) {
    console.error(error);
  }
}

check();
```

### Output:

```
Checking stock
Stock Laptop is out of stock
```

---

## Referensi

- 📚 [MDN Web Docs – Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
- 📘 [JavaScript.info – Promise](https://javascript.info/promise-basics)
- 📺 [JavaScript Async/Await Tutorial – Programming with Mosh (YouTube)](https://www.youtube.com/watch?v=568g8hxJJp4)
