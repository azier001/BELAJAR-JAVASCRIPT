## Higher-Order Functions dan Callback Functions

### Pengertian

**Higher-order functions** adalah fungsi yang menerima fungsi lain sebagai argumen atau mengembalikan fungsi lain sebagai hasil.

**Callback function** adalah fungsi yang dikirim sebagai argumen ke fungsi lain dan dipanggil di dalam fungsi tersebut.

### Contoh Penggunaan

```javascript
// Higher-order function
function selesaikanTugas(tugas, callback) {
  console.log('Menyelesaikan tugas: ' + tugas);
  callback();
}

// Callback function
function tugasSelesai() {
  console.log('Tugas selesai');
}

// Eksekusi
selesaikanTugas('Belajar JavaScript', tugasSelesai);
```

### Contoh Higher-Order Function Lainnya

1. **Menggunakan `map()` untuk memodifikasi array**

```javascript
const angka = [1, 2, 3, 4, 5];
const hasil = angka.map(num => num * 2);
console.log(hasil); // Output: [2, 4, 6, 8, 10]
```

2. **Menggunakan `filter()` untuk menyaring data**

```javascript
const angkaGenap = angka.filter(num => num % 2 === 0);
console.log(angkaGenap); // Output: [2, 4]
```

3. **Menggunakan `reduce()` untuk menghitung total nilai**

```javascript
const total = angka.reduce((acc, num) => acc + num, 0);
console.log(total); // Output: 15
```

### Kesimpulan

Higher-order function sangat berguna dalam pemrograman fungsional karena memudahkan manipulasi data dan kode menjadi lebih ringkas dan mudah dibaca.

