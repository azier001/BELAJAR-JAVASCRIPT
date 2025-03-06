## **Penjelasan Detail tentang `slice()` di JavaScript**

Method **`slice()`** pada JavaScript digunakan untuk mengambil bagian tertentu dari sebuah **array** atau **string** tanpa mengubah data asli. Method ini mengembalikan **salinan** bagian yang dipilih dalam bentuk array baru atau string baru.

----------

### **Sintaks:**


`array.slice(start, end);` 

atau



`string.slice(start, end);` 

-   **`start`** _(optional)_ → Indeks awal pemotongan (termasuk dalam hasil).
-   **`end`** _(optional)_ → Indeks akhir pemotongan (tidak termasuk dalam hasil).
-   Jika **`end` tidak diberikan**, maka `slice()` akan mengambil semua elemen hingga akhir array atau string.
-   Jika **indeks negatif**, maka dihitung dari akhir array atau string.

----------

## **1. `slice()` pada Array**

Method `slice()` pada array akan mengembalikan array baru berdasarkan indeks yang diberikan.

### **Contoh 1: Mengambil Elemen dari Array**



```javascript
let fruits = ["Apel", "Mangga", "Jeruk", "Pisang", "Anggur"];
let slicedFruits = fruits.slice(1, 4); // Mengambil indeks 1 sampai 3
console.log(slicedFruits); // Output: ["Mangga", "Jeruk", "Pisang"]
```

> `slice(1, 4)` mengambil elemen dari indeks **1 sampai 3**, karena indeks **4 tidak termasuk**.

----------

### **Contoh 2: `slice()` Tanpa Parameter**


```javascript
let numbers = [1, 2, 3, 4, 5];
let copyNumbers = numbers.slice();
console.log(copyNumbers); // Output: [1, 2, 3, 4, 5]
```

> Jika `slice()` dipanggil tanpa argumen, **seluruh array akan disalin**.

----------

### **Contoh 3: Menggunakan Indeks Negatif**



```javascript
let animals = ["Kucing", "Anjing", "Singa", "Harimau", "Gajah"];
let lastThree = animals.slice(-3);
console.log(lastThree); // Output: ["Singa", "Harimau", "Gajah"]
```

> `slice(-3)` mengambil **tiga elemen terakhir**.



```javascript
let partial = animals.slice(-4, -1);
console.log(partial); // Output: ["Anjing", "Singa", "Harimau"]
```

> `slice(-4, -1)` berarti mulai dari **indeks ke-4 dari belakang hingga indeks ke-1 dari belakang**.

----------

### **Contoh 4: `slice()` Tidak Mengubah Array Asli**



```javascript
let colors = ["Merah", "Biru", "Hijau", "Kuning"];
let newColors = colors.slice(1, 3);
console.log(newColors); // Output: ["Biru", "Hijau"]
console.log(colors);    // Output: ["Merah", "Biru", "Hijau", "Kuning"] (Tetap sama)
```

> Array asli **tidak berubah**, karena `slice()` hanya mengembalikan **salinan baru**.

----------

## **2. `slice()` pada String**

Method `slice()` juga bisa digunakan pada string untuk mengambil sebagian teks.

### **Contoh 1: Mengambil Bagian String**



```javascript
let text = "JavaScript";
let slicedText = text.slice(0, 4);
console.log(slicedText); // Output: "Java"
```

> `slice(0, 4)` mengambil karakter dari indeks **0 sampai 3**.

----------

### **Contoh 2: Menggunakan Indeks Negatif pada String**



```javascript
let word = "Hello World";
let lastWord = word.slice(-5);
console.log(lastWord); // Output: "World"
```

> `slice(-5)` mengambil **lima karakter terakhir**.



```javascript
let part = word.slice(-11, -6);
console.log(part); // Output: "Hello"
```

> `slice(-11, -6)` mengambil bagian **"Hello"**.

----------

## **Perbedaan `slice()`, `splice()`, dan `substring()`**


**Method**

`slice()`

**Digunakan Untuk**

Mengambil bagian dari **array** atau **string**

**Mengubah Data Asli?**

❌ Tidak

**Mendukung Indeks Negatif?**

✅ Ya

**Method**

`splice()`

**Digunakan Untuk**

Menghapus, menambahkan, atau mengganti elemen **array**

**Mengubah Data Asli?**

✅ Ya

**Mendukung Indeks Negatif?**

❌ Tidak

**Method**

`substring()`

**Digunakan Untuk**

Mengambil bagian dari **string**

**Mengubah Data Asli?**

❌ Tidak

**Mendukung Indeks Negatif?**

❌ Tidak


**Contoh `splice()`:**



```javascript
let fruits = ["Apel", "Mangga", "Jeruk"];
fruits.splice(1, 1); // Menghapus 1 elemen dari indeks 1
console.log(fruits); // Output: ["Apel", "Jeruk"]
```

> `splice()` mengubah array asli, sedangkan `slice()` hanya membuat salinan.

----------

## **Kesimpulan**

-   `slice()` digunakan untuk mengambil bagian dari **array atau string** tanpa mengubah data asli.
-   `slice(start, end)` → **`start` termasuk, `end` tidak termasuk**.
-   Bisa menggunakan **indeks negatif** untuk mengambil bagian dari belakang.
-   Berbeda dengan `splice()`, yang **mengubah array asli**.

Method `slice()` sangat berguna untuk **memotong data, menyalin array, atau memanipulasi string** tanpa mengubah nilai aslinya! 🚀
