# **Penjelasan Detail tentang `splice()` di JavaScript**

Method **`splice()`** pada JavaScript digunakan untuk **menambah, menghapus, atau mengganti elemen dalam array**. Berbeda dengan `slice()`, method ini **mengubah array asli**.

----------

## **Sintaks:**



`array.splice(start, deleteCount, item1, item2, ...);` 

-   **`start`** → Indeks awal tempat elemen akan dimodifikasi.
-   **`deleteCount`** → Jumlah elemen yang akan dihapus.
-   **`item1, item2, ...`** _(opsional)_ → Elemen baru yang akan ditambahkan ke dalam array.
-   **Return Value** → Mengembalikan array yang berisi elemen yang **dihapus** (jika ada).

----------

# **1. Menghapus Elemen dengan `splice()`**

Kita bisa menggunakan `splice()` untuk menghapus elemen dari array dengan menentukan **indeks awal** dan jumlah elemen yang akan dihapus.

### **Contoh 1: Menghapus 2 Elemen dari Array**


```javascript
let fruits = ["Apel", "Mangga", "Jeruk", "Pisang", "Anggur"];
let removedFruits = fruits.splice(1, 2);

console.log(fruits);         // Output: ["Apel", "Pisang", "Anggur"]
console.log(removedFruits);  // Output: ["Mangga", "Jeruk"]
```

> **Penjelasan:**
> 
> -   `splice(1, 2)` berarti mulai dari **indeks 1** dan menghapus **2 elemen**.
> -   Elemen `"Mangga"` dan `"Jeruk"` dihapus.
> -   Array asli **berubah**.

----------

# **2. Menambahkan Elemen dengan `splice()`**

Kita bisa **menyisipkan elemen baru** ke dalam array menggunakan `splice()` dengan memberikan elemen tambahan.

### **Contoh 2: Menyisipkan Elemen Baru**

```javascript
let colors = ["Merah", "Biru", "Hijau"];
colors.splice(1, 0, "Kuning", "Ungu");

console.log(colors); // Output: ["Merah", "Kuning", "Ungu", "Biru", "Hijau"]
```

> **Penjelasan:**
> 
> -   `splice(1, 0, "Kuning", "Ungu")`
> -   Mulai dari indeks **1**, hapus **0 elemen** (artinya hanya menyisipkan).
> -   `"Kuning"` dan `"Ungu"` ditambahkan.

----------

# **3. Mengganti Elemen dengan `splice()`**

Kita bisa **mengganti elemen lama dengan elemen baru** dengan `splice()`.

### **Contoh 3: Mengganti Elemen di Array**

```javascript
let days = ["Senin", "Selasa", "Kamis", "Jumat"];
days.splice(2, 1, "Rabu");

console.log(days); // Output: ["Senin", "Selasa", "Rabu", "Jumat"]
```

> **Penjelasan:**
> 
> -   `splice(2, 1, "Rabu")`
> -   Mulai dari **indeks 2**, hapus **1 elemen** (`"Kamis"`) dan gantikan dengan `"Rabu"`.

----------

# **4. Menghapus Semua Elemen Setelah Indeks Tertentu**

Jika ingin **menghapus semua elemen setelah indeks tertentu**, cukup gunakan `splice()` dengan `deleteCount` besar.

### **Contoh 4: Menghapus Semua Elemen Setelah Indeks ke-2**


```javascript
let numbers = [10, 20, 30, 40, 50, 60];
numbers.splice(3); 

console.log(numbers); // Output: [10, 20, 30]
```

> **Penjelasan:**
> 
> -   `splice(3)` berarti mulai dari indeks **3**, hapus semua elemen setelahnya.
> -   Elemen **40, 50, 60** dihapus.

----------

# **5. Menggunakan `splice()` dengan Indeks Negatif**

Kita bisa menggunakan **indeks negatif** untuk mulai dari belakang array.

### **Contoh 5: Menghapus Elemen dari Belakang**

```javascript
let animals = ["Kucing", "Anjing", "Burung", "Ikan"];
animals.splice(-2, 1);

console.log(animals); // Output: ["Kucing", "Anjing", "Ikan"]
```

> **Penjelasan:**
> 
> -   `splice(-2, 1)` berarti mulai dari **indeks ke-2 dari belakang** dan hapus **1 elemen**.
> -   `"Burung"` dihapus.

----------

# **Perbedaan `splice()` vs `slice()`**



**Method**

`splice()`

**Fungsi**

Menghapus, menambah, atau mengganti elemen

**Mengubah Array Asli?**

✅ Ya

**Return Value**

Elemen yang dihapus


**Method**

`slice()`

**Fungsi**

Mengambil sebagian array tanpa mengubahnya

**Mengubah Array Asli?**

❌ Tidak

**Return Value**

Array baru


### **Contoh Perbedaan `splice()` dan `slice()`**



```javascript
let arr = ["A", "B", "C", "D"];
```

// Menggunakan slice() (tidak mengubah array asli)
```javascript
let slicedArr = arr.slice(1, 3);
console.log(arr);       // Output: ["A", "B", "C", "D"] (Tetap sama)
console.log(slicedArr); // Output: ["B", "C"]
```

// Menggunakan splice() (mengubah array asli)
```javascript
let splicedArr = arr.splice(1, 2);
console.log(arr);       // Output: ["A", "D"] (Berubah)
console.log(splicedArr); // Output: ["B", "C"]
```

----------

# **Kesimpulan**

-   `splice()` digunakan untuk **menghapus, menambahkan, atau mengganti elemen dalam array**.
-   `splice(start, deleteCount, item1, item2, ...)`
-   **Mengubah array asli**, berbeda dengan `slice()` yang hanya membuat salinan.
-   Bisa digunakan dengan **indeks negatif** untuk mulai dari belakang.

Method `splice()` sangat berguna saat ingin **memodifikasi array secara langsung**! 🚀
