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
-   **Math.abs(x)** → _abs dari kata absolute_, mengembalikan nilai absolut (selalu positif) dari `x`.
-   **Math.pow(x, y)** → _pow dari kata power_, menghitung `x` pangkat `y` (x^y).
-   **Math.sqrt(x)** → _sqrt dari square root_, menghitung akar kuadrat dari `x`.
-   **Math.cbrt(x)** → _cbrt dari cubic root_, menghitung akar kubik dari `x`.
-   **Math.max(a, b, ...)** → _max dari maximum_, mencari nilai terbesar dari sekumpulan angka.
-   **Math.min(a, b, ...)** → _min dari minimum_, mencari nilai terkecil dari sekumpulan angka.

```javascript
console.log(Math.abs(-7));      // 7
console.log(Math.pow(2, 5));    // 32
console.log(Math.sqrt(16));     // 4
console.log(Math.cbrt(8));      // 2
console.log(Math.max(1, 13, 89, 2, 75)); // 89
console.log(Math.min(1, 13, 89, 2, 75)); // 1
```

### Pembulatan Angka
-   **Math.round(x)** → _round dari kata rounding_, membulatkan ke nilai terdekat.
-   **Math.ceil(x)** → _ceil dari ceiling (langit-langit)_, membulatkan ke atas (ke angka lebih besar).
-   **Math.floor(x)** → _floor dari flooring (lantai)_, membulatkan ke bawah (ke angka lebih kecil).
-   **Math.trunc(x)** → _trunc dari truncation_, menghapus bagian desimal tanpa pembulatan.

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
