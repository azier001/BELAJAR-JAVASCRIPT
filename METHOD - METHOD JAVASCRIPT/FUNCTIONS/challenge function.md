# Challenge: Function Perkalian di JavaScript

## Tantangan
Buatlah function bernama `kali` yang menerima dua parameter dan mengembalikan hasil perkalian dari kedua parameter tersebut. Kemudian, panggil function tersebut dengan memberikan dua angka sebagai argumen.

---

## Jawaban
### **Function Perkalian**
```javascript
function kali(num1, num2) {
  return num1 * num2;
}

console.log(kali(2, 3)); // Output: 6
```

---

## Penjelasan
1. **Pendeklarasian Function**
   - Kita membuat function bernama `kali` yang menerima dua parameter (`num1` dan `num2`).
   - Function ini akan mengembalikan hasil perkalian dari kedua parameter tersebut menggunakan operator `*`.

2. **Pemanggilan Function**
   - Function `kali` dipanggil dengan dua angka, yaitu `2` dan `3`.
   - Hasil perkalian `2 * 3` akan menghasilkan `6`.
   - Hasil ini kemudian ditampilkan ke konsol dengan `console.log()`.

---

## Contoh Penggunaan Lain
```javascript
console.log(kali(5, 4)); // Output: 20
console.log(kali(10, 10)); // Output: 100
console.log(kali(-2, 8)); // Output: -16
```

