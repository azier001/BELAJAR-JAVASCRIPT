# Async/Await

Async/Await adalah sintaks modern dalam JavaScript untuk menangani operasi asynchronous secara lebih sederhana. Dengan async/await, kode asynchronous dapat ditulis seperti kode synchronous, sehingga lebih mudah dibaca dan dipahami.

## Pengertian

* `async` digunakan untuk mendeklarasikan sebuah fungsi agar dapat menggunakan `await` di dalamnya.
* `await` digunakan untuk menunggu penyelesaian sebuah Promise. Eksekusi kode akan berhenti sejenak sampai Promise tersebut selesai (resolved/rejected).

---

## Contoh Dasar

```javascript
function getData() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve('Data fetched');
    }, 2000);
  });
}

async function fetchData() {
  console.log('Fetching data ....');
  const data = await getData();
  console.log(data);
}

fetchData();
```

### Penjelasan

* `getData` adalah fungsi yang mengembalikan Promise dan selesai dalam 2 detik.
* `await getData()` akan menunggu Promise tersebut selesai sebelum melanjutkan ke `console.log(data)`.

---

## Contoh Penanganan Kondisi

### Stock Tersedia

```javascript
function checkStock(product) {
  return new Promise((resolve, reject) => {
    console.log('Checking stock');

    setTimeout(() => {
      const stockAvailable = true;

      if (stockAvailable) {
        resolve(`Stock ${product} is available`);
      } else {
        reject(`Stock ${product} is out of stock`);
      }
    }, 2000);
  });
}

async function checkData() {
  const data = await checkStock('Laptop');
  console.log(data);
}

checkData();
```

### Stock Tidak Tersedia (Error Handling dengan try/catch)

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

async function checkData() {
  try {
    const data = await checkStock('Laptop');
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

checkData();
```

---

## Tips dan Catatan Penting

* Jangan gunakan `await` di luar fungsi `async`.
* `await` hanya menunggu Promise, jika objek bukan Promise maka akan langsung dikembalikan.
* Error yang terjadi dalam Promise bisa ditangani dengan `try/catch`.
* Async/Await mempermudah chaining proses asynchronous dibandingkan `.then().catch()`.

---


## Referensi Tambahan

* MDN Web Docs: [https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async\_await](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await)
* JavaScript.info: [https://javascript.info/async-await](https://javascript.info/async-await)

---

> Catatan: Async/Await hanya tersedia di lingkungan JavaScript modern (ES2017 ke atas). Pastikan environment mendukung.
