# Method `padStart()` dalam JavaScript

## 📌 Pengertian
Method `padStart()` digunakan untuk menambahkan karakter di awal string hingga mencapai panjang tertentu. Ini berguna untuk memastikan string memiliki panjang minimum dengan menambahkan karakter tambahan di depan string asli.

## 🔧 **Sintaks**
```javascript
string.padStart(targetLength, padString)
```

### **Parameter**
1. **`targetLength`** → Panjang akhir string setelah padding. Jika lebih kecil atau sama dengan panjang string asli, maka string asli dikembalikan tanpa perubahan.
2. **`padString`** _(opsional)_ → String yang digunakan sebagai padding. Default-nya adalah **spasi (`" "`)** jika tidak diberikan.

### **Return Value**
Mengembalikan string baru dengan karakter tambahan di awal hingga mencapai `targetLength`.

---

## 📌 **Contoh Penggunaan**

### **1️⃣ Zero Padding (Menambahkan Nol di Depan)**
```javascript
let invoice = "123";
let paddedInvoice = invoice.padStart(6, "0");
console.log(paddedInvoice); // Output: "000123"
```
> String "123" ditambahkan "000" di depan hingga panjangnya menjadi 6.

---

### **2️⃣ Menggunakan Karakter Khusus sebagai Padding**
```javascript
let kode = "A1";
let paddedKode = kode.padStart(5, "*");
console.log(paddedKode); // Output: "***A1"
```
> String "A1" ditambahkan "***" di depan hingga panjangnya menjadi 5.

---

### **3️⃣ Jika `targetLength` Lebih Kecil dari Panjang String Asli**
```javascript
let text = "Dicoding";
console.log(text.padStart(5, "*")); // Output: "Dicoding" (tidak berubah)
```
> Karena panjang string asli lebih besar dari `targetLength`, string tetap sama.

---

### **4️⃣ Format Tanggal dengan `padStart()`**
```javascript
let day = "5".padStart(2, "0");  // "05"
let month = "3".padStart(2, "0"); // "03"
let year = "2025";
console.log(`${day}-${month}-${year}`); // Output: "05-03-2025"
```
> `padStart(2, "0")` memastikan angka selalu dua digit.

---

## 📌 **Kombinasi dengan `padEnd()`**
Selain `padStart()`, ada juga method `padEnd()` yang bekerja sebaliknya, yaitu menambahkan karakter di akhir string.
```javascript
let text = "JS";
console.log(text.padEnd(5, "!"));  // Output: "JS!!!"
```

---

## 📌 **Kesimpulan**
✅ `padStart()` menambahkan karakter di **depan** string.
✅ Digunakan untuk **zero padding**, **format tanggal**, atau **menyesuaikan panjang string**.
✅ Jika `targetLength` lebih kecil dari panjang string asli, maka string tetap sama.
✅ Secara default, `padString` menggunakan **spasi (`" "`)** jika tidak diberikan.



