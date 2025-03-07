### **Penjelasan Detail tentang Method `includes()` di JavaScript**

Method `includes()` pada JavaScript digunakan untuk mengecek apakah suatu elemen atau substring terdapat dalam sebuah array atau string. Jika elemen atau substring tersebut ditemukan, maka method ini akan mengembalikan `true`, jika tidak, maka akan mengembalikan `false`.

----------

## **Sintaks**

### **Untuk Array**



`array.includes(searchElement, fromIndex)` 

**Parameter:**

1.  `searchElement` → Elemen yang ingin dicari dalam array.
2.  `fromIndex` (opsional) → Indeks awal pencarian dalam array. Jika tidak diisi, pencarian dimulai dari indeks `0`. Jika bernilai negatif, akan dihitung dari belakang.

**Return Value:**

-   `true` jika elemen ditemukan dalam array.
-   `false` jika elemen tidak ditemukan.

----------

### **Untuk String**



`string.includes(searchString, position)` 

**Parameter:**

1.  `searchString` → Substring yang ingin dicari dalam string utama.
2.  `position` (opsional) → Indeks awal pencarian dalam string. Default-nya `0`.

**Return Value:**

-   `true` jika substring ditemukan dalam string utama.
-   `false` jika substring tidak ditemukan.

----------

## **Contoh Penggunaan**

### **1. Contoh `includes()` pada Array**



```javascript
const fruits = ["apel", "mangga", "jeruk", "pisang"];

console.log(fruits.includes("mangga"));  // true
console.log(fruits.includes("anggur"));  // false
console.log(fruits.includes("apel", 1)); // false (karena pencarian mulai dari indeks 1)
console.log(fruits.includes("jeruk", -2)); // true (karena -2 berarti mulai dari "jeruk")
```

### **2. Contoh `includes()` pada String**



```javascript
const sentence = "JavaScript adalah bahasa pemrograman.";

console.log(sentence.includes("JavaScript")); // true
console.log(sentence.includes("python")); // false
console.log(sentence.includes("bahasa", 15)); // true (karena "bahasa" ada setelah indeks 15)
console.log(sentence.includes("bahasa", 25)); // false (karena indeks 25 sudah melewati "bahasa")
```

----------

## **Perbedaan `includes()`, `indexOf()`, dan `some()`**

**Method**

`includes()`

**Kegunaan**

Mengecek apakah suatu elemen atau substring ada (`true`/`false`)


**Method**

`indexOf()`

**Kegunaan**

Mengembalikan indeks elemen pertama yang cocok atau `-1` jika tidak ditemukan


**Method**

`some()`

**Kegunaan**

Mengecek apakah minimal satu elemen memenuhi kondisi tertentu


**Contoh Perbedaan:**



```javascript
const arr = [10, 20, 30];

console.log(arr.includes(20));  // true
console.log(arr.indexOf(20));   // 1
console.log(arr.indexOf(50));   // -1
console.log(arr.some(num => num > 25)); // true
```

----------

### **Kesimpulan**

-   `includes()` sangat berguna untuk mengecek keberadaan elemen dalam **array** atau substring dalam **string**.
-   Berbeda dengan `indexOf()`, method ini lebih bersih dan mudah dibaca karena hanya mengembalikan `true` atau `false`.
-   Bisa digunakan dengan indeks negatif untuk pencarian dari belakang.
