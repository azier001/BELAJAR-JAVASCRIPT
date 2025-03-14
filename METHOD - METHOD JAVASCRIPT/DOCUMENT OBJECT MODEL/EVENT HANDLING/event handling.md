# Event Handling dalam JavaScript

## Pengertian Event Handling

Event Handling adalah konsep penting dalam pengembangan web yang memungkinkan kita menangkap dan merespons interaksi pengguna, seperti klik tombol, gerakan mouse, input keyboard, dan lainnya.

---

## Apa itu Event?

Event adalah suatu tindakan atau kejadian yang terjadi di halaman web. Contohnya:
- Klik pada tombol
- Pengisian formulir
- Pengguliran halaman

Event ini dapat ditangkap dan ditangani menggunakan JavaScript.

Contoh:
```html
<button onclick="alert('Tombol diklik!')">Klik Saya</button>
```
Kode di atas akan menampilkan alert ketika tombol diklik.

---

## Event Listener

Event Listener adalah mekanisme untuk menangkap event dan menjalankan fungsi tertentu ketika event tersebut terjadi.

### Cara Menambahkan Event Listener

#### 1. Menggunakan **onclick** (Inline Event Handling)
```html
<button onclick="tampilkanPesan()">Klik Saya</button>
<script>
    function tampilkanPesan() {
        alert("Tombol diklik!");
    }
</script>
```

#### 2. Menggunakan **addEventListener** (JavaScript Modern)
```html
<button id="btn">Klik Saya</button>
<script>
    document.getElementById("btn").addEventListener("click", function() {
        alert("Tombol diklik!");
    });
</script>
```

---

## Jenis-Jenis Event yang Umum Digunakan

### 1. Mouse Events
Event yang berhubungan dengan interaksi mouse.

- **click** – Ketika elemen diklik.
- **dblclick** – Ketika elemen diklik dua kali.
- **mouseover** – Ketika mouse berada di atas elemen.
- **mouseout** – Ketika mouse meninggalkan elemen.

Contoh:
```html
<button id="mouseBtn">Hover atau Klik</button>
<script>
    let btn = document.getElementById("mouseBtn");
    
    btn.addEventListener("click", function() {
        alert("Tombol diklik!");
    });
    
    btn.addEventListener("mouseover", function() {
        btn.style.backgroundColor = "yellow";
    });
    
    btn.addEventListener("mouseout", function() {
        btn.style.backgroundColor = "";
    });
</script>
```

### 2. Keyboard Events
Event yang berhubungan dengan interaksi keyboard.

- **keydown** – Ketika sebuah tombol ditekan.
- **keyup** – Ketika sebuah tombol dilepaskan.
- **keypress** – Ketika sebuah tombol ditekan dan dilepaskan (tidak digunakan lagi).

Contoh:
```html
<input type="text" id="inputText" placeholder="Ketik sesuatu...">
<script>
    document.getElementById("inputText").addEventListener("keydown", function(event) {
        console.log("Tombol ditekan: " + event.key);
    });
</script>
```

### 3. Form Events
Event yang berkaitan dengan elemen formulir.

- **submit** – Ketika formulir dikirim.
- **change** – Ketika nilai elemen input berubah.
- **focus** – Ketika elemen form mendapatkan fokus.
- **blur** – Ketika elemen form kehilangan fokus.

Contoh:
```html
<form id="myForm">
    <input type="text" id="name" placeholder="Masukkan nama" required>
    <button type="submit">Kirim</button>
</form>
<script>
    document.getElementById("myForm").addEventListener("submit", function(event) {
        event.preventDefault(); // Mencegah reload halaman
        alert("Formulir dikirim!");
    });
</script>
```

### 4. Window Events
Event yang berkaitan dengan jendela browser.

- **load** – Ketika halaman selesai dimuat.
- **resize** – Ketika ukuran jendela berubah.
- **scroll** – Ketika halaman digulir.

Contoh:
```html
<script>
    window.addEventListener("load", function() {
        console.log("Halaman telah dimuat!");
    });

    window.addEventListener("resize", function() {
        console.log("Ukuran jendela berubah: " + window.innerWidth + "px");
    });
</script>
```

---

## Kesimpulan
Event Handling adalah konsep penting dalam JavaScript yang memungkinkan kita menangani interaksi pengguna dengan halaman web. Dengan memahami berbagai jenis event dan cara menggunakannya, kita dapat membuat aplikasi web yang lebih interaktif dan responsif.



