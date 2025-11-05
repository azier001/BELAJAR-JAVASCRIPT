# 🎯 Dokumentasi dispatchEvent JavaScript

<div align="center">

![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Level](https://img.shields.io/badge/Level-Pemula-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Lengkap-blue?style=for-the-badge)

**Panduan lengkap memahami dan menggunakan dispatchEvent di JavaScript**

[⭐ Star Repository Ini](#) • [📖 Dokumentasi](#) • [💬 Diskusi](#)

</div>

---

## 📑 Daftar Isi

- <a href="#apa-itu-dispatchevent">🤔 Apa itu dispatchEvent?</a>
- <a href="#kenapa-perlu-dispatchevent">❓ Kenapa Perlu dispatchEvent?</a>
- <a href="#cara-kerja-dispatchevent">⚙️ Cara Kerja dispatchEvent</a>
- <a href="#sintaks-dasar">📝 Sintaks Dasar</a>
- <a href="#contoh-penggunaan-sederhana">🎈 Contoh Penggunaan Sederhana</a>
- <a href="#custom-event">🎨 Custom Event</a>
- <a href="#event-bubbling-dan-capturing">🔄 Event Bubbling dan Capturing</a>
- <a href="#contoh-kasus-nyata">💡 Contoh Kasus Nyata</a>
- <a href="#tips-dan-best-practice">✨ Tips dan Best Practice</a>
- <a href="#kesalahan-umum">⚠️ Kesalahan Umum</a>
- <a href="#referensi">📚 Referensi</a>

---

<h2 id="apa-itu-dispatchevent">🤔 Apa itu dispatchEvent?</h2>

**dispatchEvent** adalah method JavaScript yang digunakan untuk **memicu (trigger) event secara manual** pada sebuah element HTML atau objek DOM.

Bayangkan seperti ini:
- Biasanya event terjadi karena **aksi user** (klik mouse, tekan keyboard, dll)
- Dengan `dispatchEvent`, kita bisa **membuat event itu terjadi sendiri** tanpa aksi user!

### Analogi Sederhana 🎭

Ibaratkan event seperti bel pintu rumah:
- **Normal**: Tamu menekan bel → bel berbunyi
- **dispatchEvent**: Kita menekan bel dari dalam rumah → bel tetap berbunyi

---

<h2 id="kenapa-perlu-dispatchevent">❓ Kenapa Perlu dispatchEvent?</h2>

### Kegunaan Utama:

1. **Testing** - Menguji fungsi event handler tanpa interaksi manual
2. **Automation** - Membuat workflow otomatis dalam aplikasi
3. **Component Communication** - Komunikasi antar komponen/modul
4. **Simulasi User Action** - Simulasi klik, input, dll secara programmatic
5. **Custom Events** - Membuat event kustom untuk kebutuhan spesifik

---

<h2 id="cara-kerja-dispatchevent">⚙️ Cara Kerja dispatchEvent</h2>

### Diagram Alur:

```
1. Buat Event Object
   ↓
2. Dispatch Event ke Element
   ↓
3. Event Handler Terpanggil
   ↓
4. Event Selesai
```

### Langkah-Langkah:

1. **Membuat Event**: Gunakan `new Event()` atau `new CustomEvent()`
2. **Dispatch**: Panggil `element.dispatchEvent(event)`
3. **Listen**: Event listener yang terdaftar akan terpanggil

---

<h2 id="sintaks-dasar">📝 Sintaks Dasar</h2>

```javascript
// Sintaks umum
element.dispatchEvent(event)

// Membuat event
const event = new Event('nama-event', {
  bubbles: true,      // Apakah event naik ke parent?
  cancelable: true,   // Apakah bisa di-cancel?
  composed: false     // Apakah melewati shadow DOM?
});

// Dispatch event
element.dispatchEvent(event);
```

### Parameter Event Options:

| Parameter | Type | Default | Deskripsi |
|-----------|------|---------|-----------|
| `bubbles` | Boolean | `false` | Event naik ke element parent |
| `cancelable` | Boolean | `false` | Event bisa di-cancel dengan `preventDefault()` |
| `composed` | Boolean | `false` | Event melewati shadow DOM boundary |

---

<h2 id="contoh-penggunaan-sederhana">🎈 Contoh Penggunaan Sederhana</h2>

### Contoh 1: Trigger Click Event

```javascript
// HTML: <button id="myBtn">Klik Saya</button>

const button = document.getElementById('myBtn');

// Tambahkan event listener
button.addEventListener('click', function() {
  console.log('Button diklik!');
  alert('Halo! Button baru saja diklik.');
});

// Trigger click secara manual
const clickEvent = new Event('click');
button.dispatchEvent(clickEvent);
```

**Output:**
```
Console: "Button diklik!"
Alert: "Halo! Button baru saja diklik."
```

> ✅ Button seperti diklik, padahal kita tidak menekan mouse!

---

### Contoh 2: Trigger Input Event

```javascript
// HTML: <input id="nama" type="text">

const inputField = document.getElementById('nama');

// Listen input changes
inputField.addEventListener('input', function(e) {
  console.log('Input berubah:', e.target.value);
});

// Ubah value dan trigger event
inputField.value = 'John Doe';
const inputEvent = new Event('input', { bubbles: true });
inputField.dispatchEvent(inputEvent);
```

**Output:**
```
Console: "Input berubah: John Doe"
```

---

<h2 id="custom-event">🎨 Custom Event</h2>

**CustomEvent** memungkinkan kita mengirim **data tambahan** saat dispatch event.

### Sintaks CustomEvent:

```javascript
const customEvent = new CustomEvent('nama-event', {
  detail: { /* data apapun */ },
  bubbles: true,
  cancelable: true
});
```

### Contoh 3: Custom Event dengan Data

```javascript
const button = document.getElementById('myBtn');

// Listen custom event
button.addEventListener('userLogin', function(e) {
  console.log('User login detected!');
  console.log('Username:', e.detail.username);
  console.log('Role:', e.detail.role);
  console.log('Timestamp:', e.detail.timestamp);
});

// Dispatch custom event dengan data
const loginEvent = new CustomEvent('userLogin', {
  detail: {
    username: 'johndoe',
    role: 'admin',
    timestamp: new Date().toISOString()
  },
  bubbles: true
});

button.dispatchEvent(loginEvent);
```

**Output:**
```
Console: "User login detected!"
Console: "Username: johndoe"
Console: "Role: admin"
Console: "Timestamp: 2025-11-05T10:30:45.123Z"
```

---

### Contoh 4: Notifikasi System

```javascript
// System notifikasi sederhana
const app = document.body;

// Listen notifikasi
app.addEventListener('notify', function(e) {
  const { type, message } = e.detail;
  console.log(`[${type.toUpperCase()}] ${message}`);
});

// Fungsi helper untuk kirim notifikasi
function sendNotification(type, message) {
  const notifyEvent = new CustomEvent('notify', {
    detail: { type, message }
  });
  app.dispatchEvent(notifyEvent);
}

// Gunakan
sendNotification('success', 'Data berhasil disimpan!');
sendNotification('error', 'Gagal menghubungi server');
sendNotification('info', 'Anda memiliki 3 pesan baru');
```

**Output:**
```
Console: "[SUCCESS] Data berhasil disimpan!"
Console: "[ERROR] Gagal menghubungi server"
Console: "[INFO] Anda memiliki 3 pesan baru"
```

---

<h2 id="event-bubbling-dan-capturing">🔄 Event Bubbling dan Capturing</h2>

### Apa itu Bubbling?

**Bubbling** = Event naik dari child ke parent element.

```html
<div id="parent">
  <button id="child">Click Me</button>
</div>
```

```javascript
const parent = document.getElementById('parent');
const child = document.getElementById('child');

// Listener di parent
parent.addEventListener('click', function() {
  console.log('Parent clicked!');
});

// Listener di child
child.addEventListener('click', function() {
  console.log('Child clicked!');
});

// Dispatch dengan bubbles: true
const event = new Event('click', { bubbles: true });
child.dispatchEvent(event);
```

**Output:**
```
Console: "Child clicked!"
Console: "Parent clicked!"  ← Event naik ke parent!
```

---

### Tanpa Bubbling

```javascript
// Dispatch dengan bubbles: false (default)
const event = new Event('click', { bubbles: false });
child.dispatchEvent(event);
```

**Output:**
```
Console: "Child clicked!"
// Parent TIDAK terpanggil!
```

---

<h2 id="contoh-kasus-nyata">💡 Contoh Kasus Nyata</h2>

### Contoh 5: Form Validation System

```javascript
const form = document.getElementById('myForm');
const usernameInput = document.getElementById('username');

// Validator system
form.addEventListener('validate', function(e) {
  const { field, value } = e.detail;
  
  if (field === 'username' && value.length < 3) {
    console.log('❌ Username terlalu pendek!');
    e.detail.isValid = false;
  } else {
    console.log('✅ Validasi berhasil');
    e.detail.isValid = true;
  }
});

// Fungsi validasi
function validateField(field, value) {
  const validateEvent = new CustomEvent('validate', {
    detail: { field, value, isValid: true },
    cancelable: true
  });
  
  form.dispatchEvent(validateEvent);
  return validateEvent.detail.isValid;
}

// Test validasi
console.log('Test 1: username = "ab"');
validateField('username', 'ab');

console.log('\nTest 2: username = "john"');
validateField('username', 'john');
```

**Output:**
```
Test 1: username = "ab"
Console: "❌ Username terlalu pendek!"

Test 2: username = "john"
Console: "✅ Validasi berhasil"
```

---

### Contoh 6: Shopping Cart System

```javascript
const cart = document.getElementById('cart');
let cartItems = [];

// Listen cart events
cart.addEventListener('addToCart', function(e) {
  const item = e.detail;
  cartItems.push(item);
  console.log(`✅ "${item.name}" ditambahkan ke keranjang`);
  console.log(`📦 Total item: ${cartItems.length}`);
});

cart.addEventListener('removeFromCart', function(e) {
  const index = cartItems.findIndex(i => i.id === e.detail.id);
  if (index > -1) {
    const removed = cartItems.splice(index, 1)[0];
    console.log(`🗑️ "${removed.name}" dihapus dari keranjang`);
    console.log(`📦 Total item: ${cartItems.length}`);
  }
});

// Helper functions
function addToCart(product) {
  const event = new CustomEvent('addToCart', {
    detail: product
  });
  cart.dispatchEvent(event);
}

function removeFromCart(productId) {
  const event = new CustomEvent('removeFromCart', {
    detail: { id: productId }
  });
  cart.dispatchEvent(event);
}

// Simulasi
addToCart({ id: 1, name: 'Laptop', price: 10000000 });
addToCart({ id: 2, name: 'Mouse', price: 150000 });
removeFromCart(1);
```

**Output:**
```
Console: "✅ "Laptop" ditambahkan ke keranjang"
Console: "📦 Total item: 1"
Console: "✅ "Mouse" ditambahkan ke keranjang"
Console: "📦 Total item: 2"
Console: "🗑️ "Laptop" dihapus dari keranjang"
Console: "📦 Total item: 1"
```

---

<h2 id="tips-dan-best-practice">✨ Tips dan Best Practice</h2>

### ✅ DO (Yang Benar)

```javascript
// 1. Gunakan CustomEvent untuk data kompleks
const event = new CustomEvent('update', {
  detail: { user: 'John', action: 'login' }
});

// 2. Buat nama event yang deskriptif
element.addEventListener('userLoggedIn', handler);
element.addEventListener('dataFetchComplete', handler);

// 3. Gunakan bubbles untuk komunikasi parent-child
const event = new Event('change', { bubbles: true });

// 4. Cleanup event listener
const handler = (e) => console.log(e.detail);
element.addEventListener('custom', handler);
// Nanti: element.removeEventListener('custom', handler);
```

### ❌ DON'T (Yang Salah)

```javascript
// 1. Jangan gunakan nama event bawaan browser untuk custom event
const badEvent = new Event('click'); // ❌ Bisa confusing

// 2. Jangan lupa set bubbles jika perlu parent mendengar
const badEvent = new Event('update'); // ❌ bubbles default = false

// 3. Jangan dispatch event dalam loop besar tanpa debounce
for (let i = 0; i < 10000; i++) {
  element.dispatchEvent(event); // ❌ Performance issue!
}

// 4. Jangan lupa handle error
try {
  element.dispatchEvent(event);
} catch (error) {
  console.error('Dispatch failed:', error);
}
```

---

<h2 id="kesalahan-umum">⚠️ Kesalahan Umum</h2>

### 1. Lupa Set Bubbles

```javascript
// ❌ Salah
const event = new Event('update');
child.dispatchEvent(event);
// Parent tidak akan mendengar!

// ✅ Benar
const event = new Event('update', { bubbles: true });
child.dispatchEvent(event);
```

---

### 2. Dispatch Sebelum Element Siap

```javascript
// ❌ Salah - Element belum ada di DOM
const button = document.getElementById('btn');
button.dispatchEvent(event); // Error!

// ✅ Benar - Tunggu DOM ready
document.addEventListener('DOMContentLoaded', function() {
  const button = document.getElementById('btn');
  button.dispatchEvent(event);
});
```

---

### 3. Tidak Return Value dari dispatchEvent

```javascript
// dispatchEvent return boolean
const wasCancelled = !element.dispatchEvent(event);

if (wasCancelled) {
  console.log('Event di-cancel oleh preventDefault()');
}
```

---

<h2 id="referensi">📚 Referensi</h2>

### 📖 Dokumentasi Resmi
- [MDN - EventTarget.dispatchEvent()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/dispatchEvent)
- [MDN - Event Constructor](https://developer.mozilla.org/en-US/docs/Web/API/Event/Event)
- [MDN - CustomEvent](https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent)

### 🎓 Tutorial Lanjutan
- Event Bubbling dan Capturing
- Event Delegation
- Custom Events Architecture
- Testing dengan Dispatch Events

---

<div align="center">

### 🎉 Selamat Belajar!

**Dibuat dengan ❤️ untuk pembelajaran JavaScript**

[⬆️ Kembali ke Atas](#-dokumentasi-dispatchevent-javascript)

---

*Dokumentasi ini dibuat untuk pemula dan tujuan pembelajaran pribadi*

![JavaScript](https://img.shields.io/badge/Keep-Learning-orange?style=for-the-badge)

</div>
