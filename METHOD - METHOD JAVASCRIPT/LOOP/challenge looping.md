# Challenge: Looping di JavaScript

## Tantangan
Buatlah kode menggunakan `for loop` yang mencetak angka dari 1 hingga 10, tetapi melewatkan angka 5 (tidak mencetak angka 5). Gunakan pernyataan `continue` untuk melewati iterasi tertentu.

---

## Jawaban
### **Menggunakan For Loop dengan Continue**

```javascript
for (let i = 1; i <= 10; i++) {
  // Jika i bernilai 5, lewati iterasi ini
  if (i === 5) {
    continue;
  }
  console.log(i);
}
```

**Output:**
```
1
2
3
4
6
7
8
9
10
```

### **Penjelasan Kode**
1. **Deklarasi Loop**: `for (let i = 1; i <= 10; i++)` menjalankan iterasi dari 1 hingga 10.
2. **Kondisi Continue**: `if (i === 5)` memeriksa apakah `i` bernilai 5.
3. **Continue**: Jika kondisi benar, `continue` akan dilewati dan `console.log(i)` tidak akan dieksekusi untuk nilai 5.
4. **Output**: Program akan mencetak angka 1, 2, 3, 4, 6, 7, 8, 9, dan 10.

### **Manfaat Menggunakan Continue**
- Berguna untuk melewati iterasi tertentu tanpa menghentikan loop.
- Membantu meningkatkan keterbacaan kode dengan menghindari penggunaan blok `else` yang tidak perlu.

---

## Alternatif Penyelesaian
### **Menggunakan While Loop**
Selain `for`, kita juga bisa menggunakan `while` loop untuk mencapai hasil yang sama:

```javascript
let i = 1;
while (i <= 10) {
  if (i === 5) {
    i++;
    continue;
  }
  console.log(i);
  i++;
}
```

**Output:**
```
1
2
3
4
6
7
8
9
10
```

### **Menggunakan For Loop Tanpa Continue**
Jika hanya ingin mencetak angka tanpa menggunakan `continue`, kita bisa menggunakan pendekatan berikut:

```javascript
for (let i = 1; i <= 10; i++) {
  if (i !== 5) console.log(i);
}
```

**Output:**
```
1
2
3
4
6
7
8
9
10
```

Kode ini lebih ringkas karena langsung memeriksa kondisi sebelum mencetak angka tanpa menggunakan `continue`.

