
# ⚠ Callback Hell

## Apa itu Callback Hell?

**Callback Hell** terjadi ketika kita memiliki banyak operasi asynchronous (misalnya: membaca file, mengambil data dari API, dll) yang saling bergantung, dan masing-masing menggunakan callback function. Karena setiap callback berada di dalam callback lainnya, struktur kode menjadi seperti "piramida ke neraka" — dalam artian makin dalam dan sulit dibaca.

---

## 🧱 Contoh Callback Hell

Misalnya, kita ingin:

1. Mengambil data pengguna  
2. Mengambil postingan berdasarkan pengguna  
3. Mengambil komentar berdasarkan postingan  

```javascript
function getUser(callback) {
  setTimeout(() => {
    console.log("1. Mengambil data pengguna...");
    callback({ userId: 1, name: "John" });
  }, 1000);
}

function getPosts(userId, callback) {
  setTimeout(() => {
    console.log("2. Mengambil postingan pengguna...");
    callback([{ postId: 101, title: "Post Satu" }]);
  }, 1000);
}

function getComments(postId, callback) {
  setTimeout(() => {
    console.log("3. Mengambil komentar pada postingan...");
    callback([{ commentId: 1001, content: "Komentar pertama" }]);
  }, 1000);
}

// Callback Hell
getUser((user) => {
  getPosts(user.userId, (posts) => {
    getComments(posts[0].postId, (comments) => {
      console.log("Output akhir:", comments);
    });
  });
});
```

### Output:
```
1. Mengambil data pengguna...
2. Mengambil postingan pengguna...
3. Mengambil komentar pada postingan...
Output akhir: [ { commentId: 1001, content: 'Komentar pertama' } ]
```

> Masalah: Terlalu banyak indentasi, sulit dibaca, dan sulit di-debug jika terjadi error.

---

## 💡 Cara Mengatasi Callback Hell

---

### ✅ 1. Menggunakan Promises

Promises memungkinkan kita untuk menulis kode asynchronous secara berantai dan lebih bersih:

```javascript
function getUser() {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log("1. Mengambil data pengguna...");
      resolve({ userId: 1, name: "John" });
    }, 1000);
  });
}

function getPosts(userId) {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log("2. Mengambil postingan pengguna...");
      resolve([{ postId: 101, title: "Post Satu" }]);
    }, 1000);
  });
}

function getComments(postId) {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log("3. Mengambil komentar pada postingan...");
      resolve([{ commentId: 1001, content: "Komentar pertama" }]);
    }, 1000);
  });
}

// Menggunakan Promise chaining
getUser()
  .then(user => getPosts(user.userId))
  .then(posts => getComments(posts[0].postId))
  .then(comments => {
    console.log("Output akhir:", comments);
  });
```

### Output:
```
1. Mengambil data pengguna...
2. Mengambil postingan pengguna...
3. Mengambil komentar pada postingan...
Output akhir: [ { commentId: 1001, content: 'Komentar pertama' } ]
```

---

### ✅ 2. Menggunakan Async/Await

Async/Await memberikan sintaks yang terlihat lebih seperti kode sinkron, tetapi tetap bersifat asynchronous.

```javascript
async function getUser() {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log("1. Mengambil data pengguna...");
      resolve({ userId: 1, name: "John" });
    }, 1000);
  });
}

async function getPosts(userId) {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log("2. Mengambil postingan pengguna...");
      resolve([{ postId: 101, title: "Post Satu" }]);
    }, 1000);
  });
}

async function getComments(postId) {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log("3. Mengambil komentar pada postingan...");
      resolve([{ commentId: 1001, content: "Komentar pertama" }]);
    }, 1000);
  });
}

async function showData() {
  const user = await getUser();
  const posts = await getPosts(user.userId);
  const comments = await getComments(posts[0].postId);
  console.log("Output akhir:", comments);
}

showData();
```

### Output:
```
1. Mengambil data pengguna...
2. Mengambil postingan pengguna...
3. Mengambil komentar pada postingan...
Output akhir: [ { commentId: 1001, content: 'Komentar pertama' } ]
```

---

## 📌 Kesimpulan

| Pendekatan     | Kelebihan                                              | Kekurangan                              |
|----------------|--------------------------------------------------------|------------------------------------------|
| Callback       | Mudah dipahami untuk proses tunggal                    | Tidak cocok untuk banyak proses          |
| Promises       | Menghindari callback hell dengan chaining              | Bisa menjadi panjang jika banyak .then   |
| Async/Await    | Kode bersih dan mudah dibaca seperti kode sinkron     | Perlu try-catch untuk menangani error    |

---

## 🔥 Tips Menghindari Callback Hell

- Gunakan **Promises** atau **Async/Await** sejak awal
- Hindari terlalu banyak *nested callback*
- Pisahkan setiap operasi ke dalam fungsi tersendiri
- Gunakan `try-catch` untuk penanganan error dalam async/await
