# 🎯 Method `closest()` pada DOM JavaScript

> **Panduan lengkap untuk memahami method closest() dengan mudah**

---

## 📖 Apa itu `closest()`?

Method `closest()` adalah cara untuk **mencari elemen terdekat** (termasuk elemen itu sendiri) yang cocok dengan selector CSS yang kita tentukan. Method ini akan mencari ke **atas** (parent, grandparent, dst) sampai menemukan elemen yang cocok.

**Analogi Sederhana:**
Bayangkan Anda sedang di sebuah gedung bertingkat. Method `closest()` seperti naik lift dari lantai Anda sekarang, berhenti di setiap lantai untuk memeriksa apakah itu lantai yang Anda cari, sampai akhirnya menemukan lantai yang tepat atau sampai di atap gedung.

---

## ✨ Sintaks Dasar

```javascript
element.closest(selector)
```

**Parameter:**
- `selector` - String CSS selector yang ingin dicari

**Return Value:**
- Elemen yang cocok (jika ditemukan)
- `null` (jika tidak ditemukan)

---

## 🌳 Cara Kerja `closest()`

```
┌─────────────────────────┐
│   <body>                │  ← Berhenti di sini (paling atas)
│   ┌─────────────────┐   │
│   │ <div class="a"> │   │  ← Cek: apakah ini yang dicari?
│   │ ┌─────────────┐ │   │
│   │ │ <div id="b">│ │   │  ← Cek: apakah ini yang dicari?
│   │ │ ┌─────────┐ │ │   │
│   │ │ │ <button>│ │ │   │  ← Mulai dari sini
│   │ │ └─────────┘ │ │   │
│   │ └─────────────┘ │   │
│   └─────────────────┘   │
└─────────────────────────┘
```

**Proses Pencarian:**
1. ✅ Cek elemen saat ini
2. ⬆️ Naik ke parent
3. ✅ Cek parent
4. ⬆️ Naik lagi
5. 🔁 Ulangi sampai ketemu atau sampai di `<html>`

---

## 💡 Contoh Penggunaan

### Contoh 1: Mencari Parent dengan Class

```html
<div class="container">
  <div class="card">
    <button id="myButton">Klik Saya</button>
  </div>
</div>
```

```javascript
const button = document.getElementById('myButton');
const card = button.closest('.card');

console.log(card); // <div class="card">...</div>
```

**Penjelasan:** Dari `button`, cari elemen terdekat yang punya class `card`.

---

### Contoh 2: Mencari Diri Sendiri

```html
<div class="box" id="myBox">
  <p>Konten</p>
</div>
```

```javascript
const box = document.getElementById('myBox');
const result = box.closest('.box');

console.log(result === box); // true ✅
```

**Penjelasan:** `closest()` juga memeriksa elemen itu sendiri!

---

### Contoh 3: Tidak Ditemukan

```html
<div class="wrapper">
  <button id="btn">Tombol</button>
</div>
```

```javascript
const btn = document.getElementById('btn');
const notFound = btn.closest('.tidak-ada');

console.log(notFound); // null ❌
```

**Penjelasan:** Jika tidak ada elemen yang cocok, return `null`.

---

## 🎯 Use Case Praktis

### 1. Event Delegation pada List Items

```html
<ul class="todo-list">
  <li data-id="1">
    <span>Belajar JavaScript</span>
    <button class="delete">🗑️</button>
  </li>
  <li data-id="2">
    <span>Belajar closest()</span>
    <button class="delete">🗑️</button>
  </li>
</ul>
```

```javascript
document.querySelector('.todo-list').addEventListener('click', (e) => {
  if (e.target.classList.contains('delete')) {
    // Cari <li> terdekat dari tombol delete
    const listItem = e.target.closest('li');
    const id = listItem.dataset.id;
    
    console.log(`Menghapus item dengan ID: ${id}`);
    listItem.remove();
  }
});
```

**Keuntungan:** Tidak perlu attach event listener ke setiap tombol!

---

### 2. Modal / Dialog Handler

```html
<div class="modal" id="myModal">
  <div class="modal-content">
    <h2>Judul Modal</h2>
    <p>Konten modal...</p>
    <button class="close">Tutup</button>
  </div>
</div>
```

```javascript
document.addEventListener('click', (e) => {
  // Jika klik di luar modal-content, tutup modal
  const modal = e.target.closest('.modal');
  const modalContent = e.target.closest('.modal-content');
  
  if (modal && !modalContent) {
    modal.style.display = 'none';
  }
});
```

---

### 3. Form Validation

```html
<form>
  <div class="form-group">
    <label>Email</label>
    <input type="email" name="email" required>
    <span class="error-message"></span>
  </div>
</form>
```

```javascript
document.querySelectorAll('input').forEach(input => {
  input.addEventListener('blur', (e) => {
    // Cari form-group terdekat untuk menampilkan error
    const formGroup = e.target.closest('.form-group');
    const errorMessage = formGroup.querySelector('.error-message');
    
    if (!e.target.validity.valid) {
      errorMessage.textContent = 'Input tidak valid!';
      formGroup.classList.add('has-error');
    }
  });
});
```

---

## 🆚 Perbandingan dengan Method Lain

| Method | Arah Pencarian | Cek Diri Sendiri | Return |
|--------|----------------|------------------|--------|
| `closest()` | ⬆️ Ke atas (ancestors) | ✅ Ya | 1 elemen atau null |
| `querySelector()` | ⬇️ Ke bawah (descendants) | ❌ Tidak | 1 elemen atau null |
| `querySelectorAll()` | ⬇️ Ke bawah (descendants) | ❌ Tidak | NodeList |
| `parentElement` | ⬆️ Satu level parent | ❌ Tidak | 1 elemen atau null |

---

## ⚡ Tips & Best Practices

### ✅ DO (Lakukan)

```javascript
// ✅ Gunakan untuk event delegation
element.closest('.target-class');

// ✅ Cek null sebelum menggunakan hasil
const parent = element.closest('.parent');
if (parent) {
  parent.classList.add('active');
}

// ✅ Gunakan untuk navigasi DOM yang kompleks
button.closest('form').submit();
```

### ❌ DON'T (Jangan)

```javascript
// ❌ Jangan gunakan untuk mencari child
// Gunakan querySelector() untuk itu
element.closest('.child-class'); // SALAH KONSEP!

// ❌ Jangan lupa cek null
const parent = element.closest('.parent');
parent.classList.add('active'); // Error jika null!

// ❌ Jangan gunakan selector yang terlalu kompleks
element.closest('div > ul > li:nth-child(2) > a'); // Terlalu spesifik
```

---

## 🔧 Browser Support

| Browser | Version |
|---------|---------|
| Chrome | ✅ 41+ |
| Firefox | ✅ 35+ |
| Safari | ✅ 9+ |
| Edge | ✅ 15+ |
| IE | ❌ Tidak support |

**Polyfill untuk IE:**
```javascript
if (!Element.prototype.closest) {
  Element.prototype.closest = function(s) {
    var el = this;
    do {
      if (el.matches(s)) return el;
      el = el.parentElement || el.parentNode;
    } while (el !== null && el.nodeType === 1);
    return null;
  };
}
```

---

## 📝 Rangkuman

🎯 **`closest()`** adalah method untuk mencari elemen ancestor (ke atas) yang cocok dengan selector

✨ **Keunggulan:**
- Simpel dan mudah dibaca
- Otomatis cek diri sendiri
- Perfect untuk event delegation
- Mengurangi kode boilerplate

⚠️ **Ingat:**
- Selalu cek return value (bisa `null`)
- Hanya mencari ke atas, bukan ke bawah
- Return elemen pertama yang cocok

---

## 🚀 Latihan

Coba buat sendiri:

1. **Event handler** untuk menghapus baris tabel saat tombol delete diklik
2. **Toggle accordion** yang mencari `.accordion-item` terdekat
3. **Form submit** yang mencari `<form>` terdekat dari tombol submit

---

<div align="center">

**Happy Coding! 💻✨**

Dibuat dengan ❤️ untuk dokumentasi belajar

</div>
