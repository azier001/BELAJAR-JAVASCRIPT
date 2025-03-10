# If-Else Statement di JavaScript

## Pengertian
If-else statement adalah salah satu struktur kontrol yang paling dasar di JavaScript. Ini digunakan untuk membuat keputusan berdasarkan kondisi tertentu. Jika kondisi tersebut benar (*true*), blok kode tertentu akan dijalankan. Jika salah (*false*), kode lain dapat dijalankan.

## Sintaks Dasar
```javascript
if (kondisi) {
    // Kode yang dijalankan jika kondisi benar (true)
} else {
    // Kode yang dijalankan jika kondisi salah (false)
}
```

### Contoh Penggunaan
```javascript
let age = 18;

if (age >= 18) {
    console.log('You are eligible to vote');
} else {
    console.log('You are not eligible to vote');
}
```

## If-Else If Statement
Digunakan untuk memeriksa beberapa kondisi secara berurutan. Blok kode pertama yang kondisinya benar (*true*) akan dijalankan, dan eksekusi akan berhenti setelah itu.

### Sintaks
```javascript
if (kondisi1) {
    // Kode jika kondisi1 benar (true)
} else if (kondisi2) {
    // Kode jika kondisi2 benar (true)
} else {
    // Kode jika semua kondisi salah (false)
}
```

### Contoh Penggunaan
```javascript
let score = 60;

if (score >= 90) {
    console.log('Grade : A');
} else if (score >= 80) {
    console.log('Grade : B');
} else if (score >= 70) {
    console.log('Grade : C');
} else if (score >= 60) {
    console.log('Grade : D');
} else {
    console.log('Grade : E');
}
```

## Nested If-Else (If-Else Bertingkat)
Kita juga bisa menempatkan if-else di dalam blok if-else lainnya. Ini disebut sebagai nested if-else.

### Sintaks
```javascript
if (kondisi1) {
    if (kondisi2) {
        // Kode jika kondisi1 dan kondisi2 benar
    } else {
        // Kode jika kondisi1 benar tapi kondisi2 salah
    }
} else {
    // Kode jika kondisi1 salah
}
```

### Contoh Penggunaan
```javascript
let num = 10;

if (num > 0) {
    if (num % 2 == 0) {
        console.log(`${num} adalah angka positif dan bilangan genap`);
    } else {
        console.log(`${num} adalah angka positif dan bilangan ganjil`);
    }
} else {
    console.log(`${num} adalah angka negatif`);
}
```

