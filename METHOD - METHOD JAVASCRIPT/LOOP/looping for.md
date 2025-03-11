# Looping dengan `for` di JavaScript

## Pengertian
Looping dengan `for` adalah salah satu metode perulangan dalam JavaScript yang digunakan untuk mengeksekusi blok kode beberapa kali sesuai dengan kondisi yang ditentukan.

## Sintaks Dasar
```javascript
for (inisialisasi; kondisi; increment/decrement) {
    // Blok kode yang akan dieksekusi
}
```

- **Inisialisasi**: Menentukan nilai awal variabel penghitung.
- **Kondisi**: Mengevaluasi apakah looping harus terus berlanjut atau berhenti.
- **Increment/Decrement**: Menentukan perubahan nilai variabel penghitung di setiap iterasi.

## Contoh Penggunaan

### 1. Perulangan Menggunakan `for`
```javascript
for (let i = 0; i < 5; i++) {
    console.log("Iterasi ke-" + i);
}
```
**Output:**
```
Iterasi ke-0
Iterasi ke-1
Iterasi ke-2
Iterasi ke-3
Iterasi ke-4
```

### 2. Looping Array Menggunakan `for`
```javascript
let buah = ["Apel", "Jeruk", "Mangga", "Pisang"];
for (let i = 0; i < buah.length; i++) {
    console.log(buah[i]);
}
```
**Output:**
```
Apel
Jeruk
Mangga
Pisang
```

### 3. Looping Mundur (Decrement)
```javascript
for (let i = 5; i > 0; i--) {
    console.log("Countdown: " + i);
}
```
**Output:**
```
Countdown: 5
Countdown: 4
Countdown: 3
Countdown: 2
Countdown: 1
```

### 4. Looping dengan `break` dan `continue`
#### a) Menggunakan `break`
```javascript
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break; // Keluar dari loop ketika i = 5
    }
    console.log(i);
}
```
**Output:**
```
0
1
2
3
4
```

#### b) Menggunakan `continue`
```javascript
for (let i = 0; i < 5; i++) {
    if (i === 2) {
        continue; // Lewati iterasi ketika i = 2
    }
    console.log(i);
}
```
**Output:**
```
0
1
3
4
```

## Kesimpulan
Looping dengan `for` di JavaScript sangat berguna untuk mengulang eksekusi kode dalam jumlah yang telah ditentukan. Dengan memahami struktur `for`, kita bisa menggunakannya untuk berbagai keperluan seperti iterasi array, perhitungan mundur, serta pengendalian looping dengan `break` dan `continue`.
