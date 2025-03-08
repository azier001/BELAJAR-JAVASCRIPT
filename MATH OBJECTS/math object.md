### 𝗠𝗮𝘁𝗵 𝗢𝗯𝗷𝗲𝗰𝘁

Math Object di JavaScript adalah objek bawaan yang berisi berbagai properti dan metode untuk melakukan operasi matematika.

## Properti Math

- **Math.PI**: Mengembalikan nilai π (3.14159...).
- **Math.E**: Mengembalikan nilai konstanta Euler (2.718...).

```javascript
console.log(Math.PI); // 3.141592653589793
console.log(Math.E);  // 2.718281828459045
```

## Metode Math

### Operasi Matematika
- **Math.abs(x)**: Mengembalikan nilai absolut dari x.
- **Math.pow(x, y)**: Mengembalikan nilai x pangkat y.
- **Math.sqrt(x)**: Mengembalikan akar kuadrat dari x.
- **Math.cbrt(x)**: Mengembalikan akar kubik dari x.
- **Math.max(a, b, c, ...)**: Mengembalikan nilai terbesar dari sekumpulan angka.
- **Math.min(a, b, c, ...)**: Mengembalikan nilai terkecil dari sekumpulan angka.

```javascript
console.log(Math.abs(-7));      // 7
console.log(Math.pow(2, 5));    // 32
console.log(Math.sqrt(16));     // 4
console.log(Math.cbrt(8));      // 2
console.log(Math.max(1, 13, 89, 2, 75)); // 89
console.log(Math.min(1, 13, 89, 2, 75)); // 1
```

### Pembulatan Angka
- **Math.round(x)**: Membulatkan angka ke nilai terdekat.
- **Math.ceil(x)**: Membulatkan angka ke atas (ke nilai terbesar berikutnya).
- **Math.floor(x)**: Membulatkan angka ke bawah (ke nilai terkecil berikutnya).
- **Math.trunc(x)**: Menghapus bagian desimal dari angka.

```javascript
console.log(Math.round(3.6));   // 4
console.log(Math.ceil(4.0000001)); // 5
console.log(Math.floor(3.9));   // 3
console.log(Math.trunc(4.99999)); // 4
```

### Random Number
- **Math.random()**: Menghasilkan angka acak antara 0 dan 1.
- Untuk mendapatkan angka acak dalam rentang tertentu, kalikan hasilnya dengan angka maksimum yang diinginkan.

```javascript
console.log(Math.round(Math.random() * 100)); // Angka acak antara 0 - 100
```

