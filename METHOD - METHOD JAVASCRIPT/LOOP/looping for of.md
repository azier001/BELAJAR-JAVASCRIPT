# Looping dengan `for...of` di JavaScript

## Pengantar
`for...of` adalah salah satu metode looping di JavaScript yang digunakan untuk mengiterasi elemen dalam objek yang bersifat iterable seperti array, string, Map, Set, dan lain-lain.

## Sintaks Dasar
```javascript
for (variabel of iterable) {
    // blok kode yang akan dieksekusi
}
```
- `variabel` adalah variabel yang digunakan untuk menyimpan nilai dari setiap elemen iterable dalam setiap iterasi.
- `iterable` adalah objek yang dapat diiterasi, seperti array atau string.

## Contoh Penggunaan

### 1. Looping pada Array
```javascript
const buah = ["Apel", "Mangga", "Jeruk"];

for (const item of buah) {
    console.log(item);
}
```
**Output:**
```
Apel
Mangga
Jeruk
```

### 2. Looping pada String
```javascript
const teks = "Halo";

for (const karakter of teks) {
    console.log(karakter);
}
```
**Output:**
```
H
a
l
o
```

### 3. Looping pada Set
```javascript
const angkaSet = new Set([1, 2, 3, 4]);

for (const angka of angkaSet) {
    console.log(angka);
}
```
**Output:**
```
1
2
3
4
```

### 4. Looping pada Map
```javascript
const users = new Map([
    ["id1", "Alice"],
    ["id2", "Bob"],
    ["id3", "Charlie"]
]);

for (const [key, value] of users) {
    console.log(`${key}: ${value}`);
}
```
**Output:**
```
id1: Alice
id2: Bob
id3: Charlie
```

## Kelebihan `for...of`
1. **Lebih mudah dibaca** dibandingkan `for` klasik atau `forEach`.
2. **Mendukung berbagai jenis iterable** seperti array, string, Set, dan Map.
3. **Dapat digunakan dengan `break` dan `continue`**, tidak seperti `forEach` yang tidak bisa dihentikan di tengah proses iterasi.

## Kesimpulan
Looping dengan `for...of` adalah cara yang efektif dan bersih untuk mengiterasi elemen dalam objek iterable di JavaScript. Cocok digunakan untuk array, string, Set, dan Map, serta memberikan sintaks yang lebih mudah dipahami dibandingkan metode looping lainnya.
