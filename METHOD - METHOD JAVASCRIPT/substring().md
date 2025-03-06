# **Penjelasan Detail tentang `substring()` di JavaScript**

Method **`substring()`** pada JavaScript digunakan untuk **mengambil bagian dari string** berdasarkan indeks awal dan akhir yang diberikan. Method ini **tidak mengubah string asli**, melainkan mengembalikan string baru.

----------

## **Sintaks:**


`string.substring(start, end);` 

-   **`start`** _(wajib)_ → Indeks awal pemotongan (termasuk dalam hasil).
-   **`end`** _(opsional)_ → Indeks akhir pemotongan (tidak termasuk dalam hasil).
-   Jika **`end` tidak diberikan**, maka akan mengambil dari `start` hingga akhir string.
-   Jika **`start > end`**, maka `substring()` akan otomatis menukar nilai `start` dan `end`.
-   **Tidak mendukung indeks negatif**, jika diberikan nilai negatif akan dianggap sebagai `0`.

----------

## **1. Mengambil Bagian String dengan `substring()`**

Method `substring()` mengambil karakter dari indeks yang ditentukan dan mengembalikan string baru.

### **Contoh 1: Mengambil Sebagian String**


```javascript
let text = "JavaScript";
let result = text.substring(0, 4);

console.log(result); // Output: "Java"
```

> **Penjelasan:**
> 
> -   `substring(0, 4)` mengambil karakter dari **indeks 0 hingga 3** (indeks **4 tidak termasuk**).
> -   Menghasilkan `"Java"`.

----------

## **2. Jika `end` Tidak Diberikan**

Jika hanya memberikan **satu parameter**, `substring()` akan mengambil string dari indeks `start` hingga akhir.

### **Contoh 2: Mengambil dari Indeks ke-5 Hingga Akhir**


```javascript
let text = "JavaScript";
let result = text.substring(5);

console.log(result); // Output: "cript"
```

> **Penjelasan:**
> 
> -   `substring(5)` mengambil karakter dari **indeks 5 hingga akhir string**.
> -   Menghasilkan `"cript"`.

----------

## **3. `substring()` akan Menukar `start` dan `end` Jika Terbalik**

Jika nilai `start` lebih besar dari `end`, maka `substring()` akan otomatis menukarnya.

### **Contoh 3: `start > end`**




```javascript
let text = "JavaScript";
let result = text.substring(7, 2);

console.log(result); // Output: "vaScr"
```

> **Penjelasan:**
> 
> -   `substring(7, 2)` ditukar menjadi `substring(2, 7)`.
> -   Menghasilkan `"vaScr"`.

----------

## **4. Jika Menggunakan Indeks Negatif**

`substring()` **tidak mendukung indeks negatif**, sehingga nilai negatif akan dianggap **0**.

### **Contoh 4: Indeks Negatif**

```javascript
let text = "JavaScript";
let result = text.substring(-3, 4);

console.log(result); // Output: "Java"
```

> **Penjelasan:**
> 
> -   `-3` dianggap sebagai `0`, sehingga `substring(-3, 4)` sama dengan `substring(0, 4)`.
> -   Menghasilkan `"Java"`.

----------

## **5. Perbedaan `substring()` vs `slice()`**



**Method**

`substring()`

**Mendukung Indeks Negatif?**

❌ Tidak

**Bisa Menukar `start` & `end`?**

✅ Ya

**Mengubah String Asli?**

❌ Tidak


**Method**

`slice()`

**Mendukung Indeks Negatif?**

✅ Ya

**Bisa Menukar `start` & `end`?**

❌ Tidak

**Mengubah String Asli?**

❌ Tidak

### **Contoh Perbedaan `substring()` dan `slice()`**


```javascript
let text = "JavaScript";
```

// substring()
```javascript
console.log(text.substring(-3, 4)); // Output: "Java" (karena -3 dianggap 0)
console.log(text.substring(7, 2));  // Output: "vaScr" (karena 7 dan 2 ditukar)
```

// slice()
```javascript
console.log(text.slice(-3, 4)); // Output: "" (karena -3 berarti mulai dari belakang)
console.log(text.slice(7, 2));  // Output: "" (karena slice() tidak menukar nilai)` 
```
----------

## **Kesimpulan**

-   `substring(start, end)` digunakan untuk **mengambil bagian string** tanpa mengubah aslinya.
-   **Jika `start > end`**, maka `substring()` otomatis menukar nilainya.
-   **Tidak mendukung indeks negatif**, jika diberikan nilai negatif dianggap `0`.
-   Berbeda dengan `slice()`, yang **mendukung indeks negatif**.

Method `substring()` sangat berguna untuk **memotong string berdasarkan posisi indeks tanpa merusak data asli**! 🚀
