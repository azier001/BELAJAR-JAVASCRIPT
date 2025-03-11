# Loop di JavaScript

Loop digunakan untuk menjalankan blok kode berulang kali selama kondisi tertentu terpenuhi. JavaScript mendukung beberapa jenis loop, yaitu:

- **`for` Loop** → Digunakan ketika jumlah iterasi sudah diketahui.
- **`while` Loop** → Digunakan ketika jumlah iterasi tidak diketahui dan bergantung pada kondisi tertentu.
- **`do-while` Loop** → Mirip dengan `while`, tetapi kode dijalankan minimal sekali sebelum pengecekan kondisi.
- **`for-in` Loop** → Digunakan untuk mengiterasi properti dalam objek.
- **`for-of` Loop** → Digunakan untuk mengiterasi nilai dalam objek iterable seperti array atau string.

## 1. `for` Loop

Digunakan untuk menjalankan kode sejumlah iterasi yang telah ditentukan.

**Struktur**:
```javascript
for (inisialisasi; kondisi; perubahan) {
    // kode yang dijalankan selama kondisi benar
}
```

**Contoh**:
```javascript
for (let i = 1; i <= 5; i++) {
  console.log(`Iterasi ke ${i}`);
}
```

## 2. `while` Loop

Digunakan untuk menjalankan kode selama kondisi masih bernilai `true`.

**Struktur**:
```javascript
while (kondisi) {
    // kode yang dijalankan selama kondisi benar
}
```

**Contoh**:
```javascript
let y = 1;
while (y <= 5) {
  console.log(`Iterasi ke ${y} dengan while loop`);
  y++;
}
```

## 3. `do-while` Loop

Mirip dengan `while`, tetapi kode akan dieksekusi minimal sekali sebelum kondisi diperiksa.

**Struktur**:
```javascript
do {
    // kode yang dijalankan minimal sekali
} while (kondisi);
```

**Contoh**:
```javascript
let z = 1;
do {
  console.log(`Iterasi ke ${z} looping dengan do while`);
  z++;
} while (z <= 5);
```

## 4. `for-in` Loop

Digunakan untuk mengiterasi properti dalam objek.

**Struktur**:
```javascript
for (let property in objek) {
    // kode yang dijalankan untuk setiap properti dalam objek
}
```

**Contoh**:
```javascript
const object = {
  nama: 'Ahmad',
  umur: 32,
};

for (let property in object) {
  console.log(property); // Output: nama, umur
  console.log(object[property]); // Output: Ahmad, 32
}
```

## 5. `for-of` Loop

Digunakan untuk mengiterasi nilai dalam objek iterable seperti array.

**Struktur**:
```javascript
for (let nilai of iterable) {
    // kode yang dijalankan untuk setiap nilai dalam iterable
}
```

**Contoh**:
```javascript
let sum = 0;
const array = [1, 2, 3, 4, 5];

for (let nilai of array) {
  console.log(nilai);
  sum += nilai;
}

console.log(sum); // Output: 15 (1 + 2 + 3 + 4 + 5)
```

## Kesimpulan

- Gunakan `for` loop jika jumlah iterasi diketahui.
- Gunakan `while` loop jika iterasi tergantung pada kondisi tertentu.
- Gunakan `do-while` loop jika ingin menjalankan kode minimal satu kali.
- Gunakan `for-in` loop untuk mengakses properti dalam objek.
- Gunakan `for-of` loop untuk mengakses nilai dalam array atau iterable lainnya.


