# 📦 Panduan JavaScript Modules

---

## 📘 Pengenalan JavaScript Modules

JavaScript Modules memungkinkan kita untuk membagi kode ke dalam file terpisah dan saling terhubung dengan ekspor dan impor. Ini membantu menciptakan struktur kode yang lebih bersih, terorganisir, dan mudah dikelola.

---

## 🎯 Mengapa Harus Menggunakan Modules?

### ✅ Keuntungan:

* 🔧 **Pemeliharaan Mudah**: Kode modular lebih gampang diuji dan diperbaiki.
* 🔁 **Reuse Kode**: Fungsi dapat digunakan ulang di berbagai tempat.
* 🧠 **Lebih Mudah Dibaca**: Struktur file lebih jelas dan tidak membingungkan.
* 🧩 **Namespace Management**: Menghindari konflik nama antar fungsi/variabel.
* ⏳ **Lazy Loading**: Memuat modul hanya saat dibutuhkan, meningkatkan performa.

---

## 📂 Tipe JavaScript Module

### 1. **ES Modules (ESM)**

* Menggunakan `import` dan `export`.
* Standar modern, didukung oleh browser & Node.js.

### 2. **CommonJS (CJS)**

* Umumnya digunakan di Node.js.
* Menggunakan `require` dan `module.exports`.

---

## 📌 Contoh Penggunaan ES Modules

### ✴️ Named Export

**math.js**

```js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;
```

**main.js**

```js
import { add, subtract } from './math.js';
console.log(add(2, 3)); // 5
```

### 🔤 Aliasing

```js
import { add as tambah, subtract as kurang } from './math.js';
```

### 🌐 Wildcard Import

```js
import * as math from './math.js';
console.log(math.add(1, 2));
```

### 🧾 Default Export

**greet.js**

```js
export default function greet(name) {
  return `Hello, ${name}!`;
}
```

**main.js**

```js
import greet from './greet.js';
console.log(greet('Alice'));
```

### 🔀 Gabungan Default dan Named Export

**utils.js**

```js
export default function formatCurrency(amount) {
  return `$${amount.toFixed(2)}`;
}
export const TAX_RATE = 0.1;
```

**main.js**

```js
import formatCurrency, { TAX_RATE } from './utils.js';
```

---

## 📦 CommonJS Modules

### 📤 Export

**math.js**

```js
const add = (a, b) => a + b;
module.exports = { add };
```

### 📥 Import

**main.js**

```js
const { add } = require('./math');
console.log(add(2, 3));
```

### 🚀 Export Fungsi Tunggal

**logger.js**

```js
module.exports = function log(msg) {
  console.log(`[LOG]: ${msg}`);
};
```

**app.js**

```js
const log = require('./logger');
log('App started');
```

---

## ⏱️ Dynamic Import (Lazy Loading)

**app.js**

```js
document.getElementById('btn').addEventListener('click', async () => {
  const math = await import('./math.js');
  console.log(math.add(2, 3));
});
```

### 🚨 Dengan Error Handling

```js
async function loadMath() {
  try {
    const math = await import('./math.js');
    return math;
  } catch (e) {
    console.error('Gagal memuat modul:', e);
  }
}
```

---

## 🔁 Re-export Modules

**index.js**

```js
export { add } from './add.js';
export * from './math-utils.js';
```

---

## 📚 Module Pattern & Namespace

**MyLibrary.js**

```js
const MyLibrary = {
  utils: {
    formatDate: (date) => date.toLocaleDateString(),
  },
  math: {
    add: (a, b) => a + b,
  },
};
export default MyLibrary;
```

---

## 💡 Best Practices

1. 🧩 **Gunakan Named Exports untuk fungsi utilitas**

```js
export const formatDate = () => {};
```

2. 🎯 **Gunakan Default Export untuk Class/Component utama**

```js
export default class App {}
```

3. 🗂️ **Konsisten dalam penamaan file**
   Gunakan `kebab-case` atau `camelCase`, jangan campur.
4. 🔄 **Hindari Circular Dependencies**
   Pisahkan kode yang saling bergantung ke modul baru.

---

## 🛠️ Troubleshooting Umum

* ❗ **CORS Error**: Pastikan file JS tersedia dengan CORS header yang tepat.
* 📄 **Ekstensi .js Wajib untuk Browser**:

```js
// ✅
import { add } from './math.js';
```

* 📜 **Tambahkan `type="module"` di HTML**

```html
<script type="module" src="main.js"></script>
```

---

## 🗂️ Struktur Proyek Modular (Contoh)

```
/src
  /utils
    format.js
  /services
    api.js
  main.js
```

**main.js**

```js
import { formatDate } from './utils/format.js';
```

---

## 📎 Kesimpulan

JavaScript Modules adalah fondasi penting dalam membangun aplikasi modern. Gunakanlah dengan bijak: kenali perbedaan antara ES Modules dan CommonJS, manfaatkan dynamic import untuk performa, dan terapkan pola arsitektur yang bersih.
