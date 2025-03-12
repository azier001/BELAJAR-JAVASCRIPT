# Konsep Perhitungan Fibonacci

## Konsep Utama
Konsep utama dari deret Fibonacci adalah bahwa setiap angka dalam deret dihitung berdasarkan **dua angka sebelumnya**.

## Alasan Menggunakan `n - 1` dan `n - 2`
Ketika kita menghitung Fibonacci dari `n`, kita perlu menjumlahkan hasil Fibonacci dari dua angka sebelumnya:

\[
F(n) = F(n-1) + F(n-2)
\]

- **`n - 1`**: Mendapatkan nilai Fibonacci dari angka sebelum `n`
- **`n - 2`**: Mendapatkan nilai Fibonacci dari dua angka sebelum `n`

Misalnya, jika kita ingin menghitung `fibonacci(5)`, maka:

\[
fibonacci(5) = fibonacci(4) + fibonacci(3)
\]

Kemudian, untuk `fibonacci(4)`, kita hitung lagi:

\[
fibonacci(4) = fibonacci(3) + fibonacci(2)
\]

Dan seterusnya, sampai mencapai **base case** (`fibonacci(1) = 1` dan `fibonacci(0) = 0`).

## Kenapa Tidak `n + 1` dan `n + 2`?
Jika kita menggunakan `n + 1` dan `n + 2`, kita malah mencoba **menghitung angka Fibonacci setelah `n`** sebelum mengetahui nilai `n` itu sendiri. Ini tidak masuk akal karena kita membutuhkan nilai sebelumnya untuk mendapatkan nilai Fibonacci dari `n`, bukan sebaliknya.

Misalnya:
- Jika kita ingin menghitung `fibonacci(5)`, lalu kita menggunakan `fibonacci(6) + fibonacci(7)`, kita malah mencoba menghitung sesuatu yang belum diketahui.

Pendekatan ini salah karena Fibonacci adalah **bottom-up**, bukan **top-down**.

## Mengapa `return n` Digunakan?
Di dalam fungsi rekursif Fibonacci, kita memiliki **base case** yang menentukan kapan rekursi harus berhenti:

```javascript
if (n <= 1) {
  return n;
}
```

Alasan `return n` digunakan adalah:
- **Menangani kasus dasar**: Nilai Fibonacci dari `0` adalah `0`, dan nilai Fibonacci dari `1` adalah `1`. Ini sesuai dengan definisi dasar deret Fibonacci.
- **Mencegah rekursi tak terbatas**: Tanpa base case ini, fungsi akan terus memanggil dirinya sendiri tanpa akhir, menyebabkan stack overflow.
- **Mengembalikan nilai langsung**: Untuk `n = 0` atau `n = 1`, kita tidak perlu melakukan perhitungan lebih lanjut karena hasilnya sudah diketahui.

Tanpa `return n`, fungsi tidak akan pernah mencapai titik akhir dan akan terus memanggil dirinya sendiri secara tak terbatas.

## Kesimpulan
- Fibonacci selalu menggunakan **dua angka sebelumnya** (`n - 1` dan `n - 2`), bukan angka setelahnya (`n + 1` dan `n + 2`).
- Menggunakan `n + 1` dan `n + 2` akan menyebabkan kesalahan logika karena kita belum tahu hasil `n`, tapi malah mencoba menghitung angka setelahnya.
- `return n` digunakan sebagai **base case** untuk menghentikan rekursi dan mengembalikan nilai langsung ketika `n` adalah `0` atau `1`, sesuai dengan definisi Fibonacci.


