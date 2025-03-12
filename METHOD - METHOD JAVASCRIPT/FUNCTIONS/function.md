# 📌 **Function di JavaScript**

Function di JavaScript adalah blok kode yang dirancang untuk melakukan tugas tertentu dan dapat digunakan berulang kali. Function mempermudah pengorganisasian kode dengan membagi tugas besar menjadi tugas-tugas kecil yang lebih terstruktur.

## 📌 **Membuat Function**

Untuk membuat function, gunakan kata kunci `function` diikuti dengan nama function, parameter (jika ada), dan blok kode yang akan dijalankan.

```javascript
function namaFunction(parameter1, parameter2, ...) {
    // Blok kode yang akan dijalankan
}
```

### 📌 Contoh Function dengan Parameter
```javascript
function sapaPengguna(nama) {
    console.log(`Hallo ${nama}!`);
}

function sapaSemua() {
    console.log("Hallo semuanya!");
}
```

## 📌 **Memanggil Function**

Untuk menjalankan function, cukup panggil dengan menyebutkan nama function diikuti dengan tanda kurung, serta masukkan nilai untuk parameternya (jika ada).

```javascript
sapaPengguna("Budi"); // Output: Hallo Budi!
sapaSemua(); // Output: Hallo semuanya!
```

## 📌 **Parameter dan Argumen**

- **Parameter** adalah variabel yang didefinisikan dalam deklarasi function.
- **Argumen** adalah nilai yang diberikan saat function dipanggil.

Contoh:
```javascript
function tambah(a, b) {
    console.log(a + b);
}

tambah(3, 5); // Output: 8
```

Di sini:
- `a` dan `b` adalah **parameter**.
- `3` dan `5` adalah **argumen**.

## 📌 **Return Statement**

Function dapat mengembalikan nilai menggunakan `return`. Setelah `return` dieksekusi, eksekusi function akan berhenti.

```javascript
function kuadrat(num) {
    if (num > 0) {
        return num * num;
    }
    return "Angka negatif tidak kami kuadratkan";
}

console.log(kuadrat(-2)); // Output: Angka negatif tidak kami kuadratkan
console.log(kuadrat(4));  // Output: 16
```

## 📌 **Function Expression**

Selain menggunakan deklarasi function, kita juga bisa membuat function menggunakan function expression, yaitu dengan menyimpan function dalam sebuah variabel.

```javascript
const kali = function(a, b) {
    return a * b;
};

console.log(kali(4, 5)); // Output: 20
```

## 📌 **Arrow Function**

Arrow function adalah cara yang lebih ringkas dalam menuliskan function.

```javascript
const kurang = (a, b) => a - b;

console.log(kurang(10, 4)); // Output: 6
```

## 📌 **Function dengan Default Parameter**

Kita bisa memberikan nilai default pada parameter function agar tidak menghasilkan `undefined` jika tidak ada argumen yang diberikan.

```javascript
function sapa(nama = "Pengguna") {
    console.log(`Hallo, ${nama}!`);
}

sapa(); // Output: Hallo, Pengguna!
sapa("Rina"); // Output: Hallo, Rina!
```

## 📌 **IIFE (Immediately Invoked Function Expression)**

IIFE adalah function yang langsung dijalankan saat dideklarasikan.

```javascript
(function() {
    console.log("Function langsung berjalan!");
})();

// Output: Function langsung berjalan!
```

## 📌 **Kesimpulan**

1. Function adalah blok kode yang dapat digunakan kembali.
2. Bisa memiliki parameter dan mengembalikan nilai dengan `return`.
3. Terdapat beberapa cara mendeklarasikan function:
   - Function Declaration
   - Function Expression
   - Arrow Function
   - IIFE
4. Bisa menggunakan default parameter untuk menangani nilai yang tidak diberikan.


