# **Penjelasan Detail tentang `replace()` di JavaScript**

Method **`replace()`** pada JavaScript digunakan untuk **mengganti sebagian atau seluruh string** berdasarkan pola tertentu. Method ini **tidak mengubah string asli**, melainkan mengembalikan string baru dengan hasil perubahan.

----------

## **Sintaks:**


`string.replace(searchValue, newValue);` 

-   **`searchValue`** → **String atau Regular Expression** yang ingin diganti.
-   **`newValue`** → **String atau fungsi callback** sebagai pengganti `searchValue`.
-   **Return Value** → Mengembalikan string baru dengan hasil perubahan.

> **Catatan:** Method ini **hanya mengganti kemunculan pertama** dari `searchValue`. Jika ingin mengganti semua kemunculan, gunakan **RegExp dengan flag global (`/g`)**.

----------

## **1. Mengganti Sebagian String**

### **Contoh 1: Mengganti Kata Pertama yang Ditemukan**



```javascript
let text = "Saya suka apel, apel sangat enak!";
let result = text.replace("apel", "mangga");

console.log(result);
// Output: "Saya suka mangga, apel sangat enak!"
```

> **Penjelasan:**
> 
> -   Hanya mengganti kemunculan **pertama** dari `"apel"` menjadi `"mangga"`.
> -   `"apel"` kedua tetap ada.

----------

## **2. Mengganti Semua Kemunculan (`g` flag)**

Jika ingin mengganti **semua kemunculan**, gunakan **Regular Expression** dengan flag **`/g`**.

### **Contoh 2: Mengganti Semua Kemunculan Suatu Kata**


```javascript
let text = "Saya suka apel, apel sangat enak!";
let result = text.replace(/apel/g, "mangga");

console.log(result);
// Output: "Saya suka mangga, mangga sangat enak!"
```

> **Penjelasan:**
> 
> -   Menggunakan **RegExp `/apel/g`** berarti mengganti **semua** `"apel"` dalam string.
> -   Semua `"apel"` diubah menjadi `"mangga"`.

----------

## **3. Mengganti dengan **Regular Expression Case-Insensitive** (`gi` flag)**

Gunakan **`i` flag** jika ingin penggantian **tidak sensitif huruf besar/kecil**.

### **Contoh 3: Mengganti Kata Tanpa Memedulikan Huruf Besar/Kecil**


```javascript
let text = "Saya suka Apel, apel sangat enak!";
let result = text.replace(/apel/gi, "mangga");

console.log(result);
// Output: "Saya suka mangga, mangga sangat enak!"
```

> **Penjelasan:**
> 
> -   **`/apel/gi`** berarti **ganti semua (`g`)** dan **abaikan huruf besar/kecil (`i`)**.
> -   `"Apel"` dan `"apel"` keduanya berubah menjadi `"mangga"`.

----------

## **4. Menggunakan Fungsi Callback dalam `replace()`**

Jika ingin mengganti nilai **dinamis**, bisa menggunakan fungsi sebagai parameter `newValue`.

### **Contoh 4: Mengubah Angka ke Format Rupiah**


```javascript
let text = "Harga: 5000, Diskon: 3000";
let result = text.replace(/\d+/g, (match) => "Rp " + match);

console.log(result);
// Output: "Harga: Rp 5000, Diskon: Rp 3000"
```

> **Penjelasan:**
> 
> -   `/\d+/g` → Mencari semua angka (`\d+` artinya angka satu atau lebih).
> -   Fungsi callback **menambahkan `"Rp "`** sebelum angka.

----------

## **5. Menggunakan `$1`, `$2`, ... untuk Menggunakan Hasil dari RegExp**

Jika menggunakan **grup pencocokan** dalam RegExp `( ... )`, kita bisa menggunakan **`$1`, `$2`, dll.** sebagai referensi hasilnya.

### **Contoh 5: Menukar Urutan Nama Depan dan Belakang**


```javascript
let text = "Nama: Budi Santoso";
let result = text.replace(/(\w+) (\w+)/, "$2, $1");

console.log(result);
// Output: "Nama: Santoso, Budi"
```

> **Penjelasan:**
> 
> -   `(\w+) (\w+)` → Mencari **dua kata** yang dipisahkan spasi.
> -   `$1` → Kata pertama (`Budi`), `$2` → Kata kedua (`Santoso`).
> -   `"Santoso, Budi"` → Urutan ditukar menggunakan `$2, $1`.

----------

## **6. Menghapus Karakter atau Kata dengan `replace()`**

Gunakan `""` sebagai `newValue` jika ingin **menghapus teks tertentu**.

### **Contoh 6: Menghapus Semua Angka**


```javascript
let text = "Promo 50% hanya berlaku sampai 2025!";
let result = text.replace(/\d+/g, "");

console.log(result);
// Output: "Promo % hanya berlaku sampai !"
```

> **Penjelasan:**
> 
> -   `/\d+/g` → Mencari semua angka (`\d+`).
> -   Diganti dengan `""` (string kosong) sehingga angka dihapus.

----------

## **7. Perbedaan `replace()` vs `replaceAll()`**



**Method**

`replace()`

**Mengganti Semua Kemunculan?**

❌ Tidak (hanya yang pertama)

**Mendukung RegExp?**

✅ Ya

**Method**

`replaceAll()`

**Mengganti Semua Kemunculan?**

✅ Ya

**Mendukung RegExp?**

✅ Ya


Jika ingin mengganti **semua kemunculan tanpa RegExp**, gunakan **`replaceAll()`** (ES2021 ke atas).

### **Contoh 7: Menggunakan `replaceAll()`**



```javascript
let text = "Saya suka apel, apel sangat enak!";
let result = text.replaceAll("apel", "mangga");

console.log(result);
// Output: "Saya suka mangga, mangga sangat enak!"
```

> **`replaceAll()` mengganti semua `"apel"` tanpa perlu `/g` dalam RegExp.**

----------

## **Kesimpulan**

-   `replace(searchValue, newValue)` **mengganti bagian string** yang cocok dengan `searchValue`.
-   **Hanya mengganti kemunculan pertama**, kecuali menggunakan **RegExp `/g`** atau `replaceAll()`.
-   Bisa menggunakan **fungsi callback** untuk mengganti nilai secara dinamis.
-   Bisa menggunakan **grup pencocokan** (`$1`, `$2`, dll.) untuk menukar teks.
-   Gunakan `replaceAll()` jika ingin mengganti **semua kemunculan** tanpa perlu RegExp.

Method `replace()` sangat fleksibel dan bisa digunakan untuk berbagai keperluan pengolahan teks! 🚀
