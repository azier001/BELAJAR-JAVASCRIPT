# Struktur DOM dalam JavaScript

## Apa Itu DOM?
DOM (**Document Object Model**) adalah representasi berbentuk pohon dari dokumen HTML yang memungkinkan JavaScript untuk mengakses dan memanipulasi elemen-elemen di dalamnya.

## Struktur Hierarki DOM
DOM direpresentasikan dalam bentuk **pohon** (tree structure) dengan tiga jenis node utama:

1. **Document Node**: Akar dari seluruh dokumen.
2. **Element Node**: Setiap elemen HTML.
3. **Text Node**: Isi teks dari elemen.

### **Penjelasan Detail tentang Node dalam DOM**

#### **1. Document Node**
- Document node adalah akar dari seluruh dokumen HTML yang direpresentasikan dalam DOM.
- Semua elemen HTML berada di bawah document node.
- Dapat diakses menggunakan `document` dalam JavaScript.

**Contoh:**
```javascript
console.log(document); // Menampilkan seluruh dokumen HTML di console
```

#### **2. Element Node**
- Element node mewakili setiap elemen HTML seperti `<html>`, `<body>`, `<h1>`, dll.
- Bisa diakses dan dimodifikasi menggunakan berbagai metode DOM.

**Contoh:**
```javascript
let bodyElement = document.body;
console.log(bodyElement); // Menampilkan elemen <body> beserta isinya
```

#### **3. Text Node**
- Text node berisi teks yang terdapat dalam elemen HTML.
- Text node tidak memiliki anak (child), hanya berisi teks murni.
- Dapat diakses menggunakan `.textContent` atau `.nodeValue`.

**Contoh:**
```javascript
let h1 = document.getElementById("judul");
console.log(h1.firstChild.nodeValue); // Output: "Halo, DOM!"
```

### Contoh Struktur DOM
Misalkan kita memiliki HTML berikut:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Belajar DOM</title>
</head>
<body>
    <h1 id="judul">Halo, DOM!</h1>
    <p class="paragraf">Ini adalah contoh manipulasi DOM.</p>
</body>
</html>
```

Struktur DOM yang terbentuk adalah:

```
Document
│
├── <html> (Element Node)
│   ├── <head> (Element Node)
│   │   ├── <title> (Element Node)
│   │   │   ├── "Belajar DOM" (Text Node)
│   ├── <body> (Element Node)
│       ├── <h1 id="judul"> (Element Node)
│       │   ├── "Halo, DOM!" (Text Node)
│       ├── <p class="paragraf"> (Element Node)
│       │   ├── "Ini adalah contoh manipulasi DOM." (Text Node)
```

## Cara Mengakses Elemen DOM

### 1. Menggunakan `document.getElementById()`
Mengambil elemen berdasarkan ID:
```javascript
let h1 = document.getElementById("judul");
console.log(h1.textContent); // Output: Halo, DOM!
```

### 2. Menggunakan `document.querySelector()`
Mengambil elemen pertama yang cocok dengan selector CSS:
```javascript
let paragraf = document.querySelector(".paragraf");
console.log(paragraf.textContent);
```

### 3. Menggunakan `document.getElementsByClassName()`
Mengambil elemen berdasarkan class:
```javascript
let paragrafList = document.getElementsByClassName("paragraf");
console.log(paragrafList[0].textContent);
```

## Memodifikasi Elemen DOM

### 1. Mengubah Konten Elemen
```javascript
h1.textContent = "DOM telah dimanipulasi!";
```

### 2. Mengubah Gaya Elemen
```javascript
h1.style.color = "blue";
```

### 3. Menambahkan Elemen Baru
```javascript
let newParagraph = document.createElement("p");
newParagraph.textContent = "Ini paragraf baru!";
document.body.appendChild(newParagraph);
```

### 4. Menghapus Elemen
```javascript
paragraf.remove();
```

## Kesimpulan
- DOM memungkinkan JavaScript untuk mengakses dan mengubah elemen HTML.
- Struktur DOM berbentuk hierarki dengan document sebagai akar.
- Document node adalah akar dari dokumen, element node mewakili elemen HTML, dan text node berisi teks di dalam elemen.
- Manipulasi DOM bisa dilakukan dengan metode seperti `getElementById()`, `querySelector()`, dan `createElement()`.



