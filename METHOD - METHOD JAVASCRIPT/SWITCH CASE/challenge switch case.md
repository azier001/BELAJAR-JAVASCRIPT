# Challenge: Switch-Case di JavaScript

## Tantangan
Buatlah kode menggunakan `switch-case` yang menerima sebuah variabel `bulan` dengan nilai 1 hingga 12, dan mencetak nama bulan tersebut. Sertakan case `default` yang mencetak "Bulan tidak valid" jika nilainya tidak berada dalam rentang 1 hingga 12.

---

## Jawaban
### **Menggunakan Switch-Case**
```javascript
// Deklarasi variabel bulan
let bulan = 11;
let namaBulan;

// Menggunakan switch-case untuk menentukan nama bulan
switch (bulan) {
  case 1:
    namaBulan = 'Januari';
    break;
  case 2:
    namaBulan = 'Februari';
    break;
  case 3:
    namaBulan = 'Maret';
    break;
  case 4:
    namaBulan = 'April';
    break;
  case 5:
    namaBulan = 'Mei';
    break;
  case 6:
    namaBulan = 'Juni';
    break;
  case 7:
    namaBulan = 'Juli';
    break;
  case 8:
    namaBulan = 'Agustus';
    break;
  case 9:
    namaBulan = 'September';
    break;
  case 10:
    namaBulan = 'Oktober';
    break;
  case 11:
    namaBulan = 'November';
    break;
  case 12:
    namaBulan = 'Desember';
    break;
  default:
    namaBulan = 'Bulan tidak valid';
}

console.log(namaBulan);
```

---

## Alternatif: Menggunakan Array
Jika ingin solusi yang lebih ringkas, kita dapat menggunakan array:

```javascript
let bulan = 11;

// Array nama bulan
const namaBulan = [
  'Bulan tidak valid', 'Januari', 'Februari', 'Maret', 'April', 'Mei', 'Juni',
  'Juli', 'Agustus', 'September', 'Oktober', 'November', 'Desember'
];

// Menampilkan hasil
console.log(bulan >= 1 && bulan <= 12 ? namaBulan[bulan] : 'Bulan tidak valid');
```

---

## Kesimpulan
- **Switch-case** cocok digunakan untuk menangani banyak kondisi berbeda.
- **Array** lebih ringkas dan efisien dalam pencarian nama bulan.
- Selalu gunakan case `default` untuk menangani input yang tidak valid.



