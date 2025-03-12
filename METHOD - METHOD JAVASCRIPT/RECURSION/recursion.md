# ​‌‍‌⁡⁢⁣⁢Recursion di JavaScript⁡​

 ⁡⁣⁢⁢Recursion⁡ ⁡⁣⁣⁢terjadi ketika sebuah function memanggil dirinya sendiri secara langsung atau tidak langsung untuk menyelesaikan sebagian dari masalah yang diberikan. Setiap panggilan recursion membawa masalah tersebut lebih dekat ke kondisi dasar (base case), yaitu kondisi di mana recursion berhenti.⁡


## Struktur Recursion
Recursion biasanya terdiri dari dua bagian penting:
1. **Base Case (Kondisi Dasar)**: Bagian dari function yang menghentikan recursion. Ini adalah kondisi di mana masalah tidak lagi memerlukan pemanggilan function secara rekursif.
2. **Recursive Case**: Bagian dari function yang memecah masalah menjadi sub-masalah yang lebih kecil dan memanggil dirinya sendiri.


## Contoh Recursion: Faktorial
Faktorial dari sebuah bilangan adalah hasil kali dari bilangan tersebut dengan semua bilangan bulat positif di bawahnya. Faktorial dari `n` ditulis sebagai `n!`. Sebagai contoh:

- `5!` (dibaca "5 faktorial") adalah `5 * 4 * 3 * 2 * 1`, yang sama dengan `120`.

```javascript
function factorial(n) {
  // Base Case
  if (n === 0) {
    return 1;
  }

  // Recursive Case
  console.log(n); // output : 5, 4, 3, 2, 1
  return n * factorial(n - 1);
}

console.log(factorial(5)); // output : 120 -> 5 * 4 * 3 * 2 * 1
```

## Contoh Recursion: Fibonacci
Deret Fibonacci adalah urutan angka di mana setiap angka adalah jumlah dari dua angka sebelumnya, dimulai dari `0` dan `1`.

- Contoh: `0, 1, 1, 2, 3, 5, 8, 13, 21, ...`

```javascript
function fibonacci(n) {
  // Base Case
  if (n <= 1) {
    return n;
  }
  
  // Recursive Case
  return fibonacci(n - 1) + fibonacci(n - 2);
}

console.log(fibonacci(6)); // output : 8
```

## Kapan Menggunakan Recursion?
Gunakan recursion saat:
- Masalah dapat dipecah menjadi sub-masalah yang lebih kecil.
- Bekerja dengan struktur data seperti **pohon (tree)**.
- Algoritma **backtracking** diperlukan.

Namun, selalu pertimbangkan **kinerja** dan risiko **stack overflow** sebelum menggunakan recursion.
