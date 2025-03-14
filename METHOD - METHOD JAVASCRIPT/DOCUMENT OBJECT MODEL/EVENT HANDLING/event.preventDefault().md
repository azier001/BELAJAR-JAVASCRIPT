# Dokumentasi `event.preventDefault()`

## Pengertian

`event.preventDefault()` adalah metode dalam JavaScript yang digunakan untuk mencegah perilaku default dari suatu event. Contohnya:

- Mencegah tautan (`<a>`) berpindah halaman.
- Mencegah form dikirim saat tombol submit ditekan.
- Mencegah menu klik kanan muncul saat tombol kanan mouse ditekan.

## Cara Kerja

Saat suatu event terjadi, browser biasanya memiliki perilaku bawaan yang akan dijalankan. Dengan menggunakan `event.preventDefault()`, perilaku ini dapat dicegah tanpa menghentikan propagasi event ke elemen lain.

## Contoh Penggunaan

### 1. Mencegah Tautan Berpindah Halaman

```javascript
document.querySelector("a").addEventListener("click", function(event) {
    event.preventDefault(); // Mencegah navigasi ke URL href
    console.log("Tautan diklik, tetapi tidak berpindah halaman.");
});
```

### 2. Mencegah Pengiriman Formulir

```javascript
document.querySelector("form").addEventListener("submit", function(event) {
    event.preventDefault(); // Mencegah form terkirim
    console.log("Formulir tidak dikirim.");
});
```

### 3. Mencegah Menu Klik Kanan

```javascript
document.addEventListener("contextmenu", function(event) {
    event.preventDefault(); // Mencegah menu konteks muncul
    console.log("Klik kanan dinonaktifkan.");
});
```

## Perbedaan dengan `event.stopPropagation()`

| Metode                  | Fungsi |
|-------------------------|--------|
| `event.preventDefault()` | Mencegah aksi default, tetapi event tetap bisa naik ke elemen lain. |
| `event.stopPropagation()` | Menghentikan event agar tidak diteruskan ke elemen lain dalam hirarki DOM. |

### Contoh `event.stopPropagation()`

```javascript
document.querySelector("button").addEventListener("click", function(event) {
    event.stopPropagation(); // Mencegah event bubbling
    console.log("Klik tombol, tetapi tidak menyebar ke elemen luar.");
});
```

## Kesimpulan

`event.preventDefault()` sangat berguna untuk mengontrol perilaku default elemen HTML dan memberikan pengalaman pengguna yang lebih fleksibel sesuai kebutuhan aplikasi web.

