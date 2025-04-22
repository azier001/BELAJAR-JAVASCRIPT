# OOP JavaScript: Pewarisan (Inheritance) dengan Contoh Hewan dan Kucing

Kode berikut merupakan implementasi konsep **pewarisan (inheritance)** dalam Object-Oriented Programming (OOP) menggunakan JavaScript. Kita akan membahas struktur kelas, metode, pewarisan, serta dua pendekatan dalam memberikan nilai default pada properti.

---

## 1. Kelas Induk: `Hewan`

```javascript
class Hewan {
  constructor(nama, jenis = 'hewan') {
    this.nama = nama;
    this.jenis = jenis;
  }

  makan() {
    return `${this.nama} sedang makan`;
  }
}
```

### Penjelasan:
- Kelas `Hewan` memiliki dua properti: `nama` dan `jenis`.
- Properti `jenis` memiliki **nilai default** `'hewan'` jika tidak diberikan saat objek dibuat.
- Metode `makan()` mengembalikan string yang menyatakan bahwa hewan sedang makan.

---

## 2. Kelas Turunan: `Kucing`

### Pendekatan A: Default di Parameter Konstruktor

```javascript
class Kucing extends Hewan {
  constructor(nama, warna, jenis = 'kucing') {
    super(nama, jenis);
    this.warna = warna;
  }

  kucingMakan() {
    return `${super.makan()}
makannya lahap sekali`;
  }
}
```

### Pendekatan B: Default Langsung di `super()`

```javascript
class Kucing extends Hewan {
  constructor(nama, warna) {
    super(nama, 'kucing'); // default langsung di sini
    this.warna = warna;
  }

  kucingMakan() {
    return `${super.makan()}
makannya lahap sekali`;
  }
}
```

### Penjelasan:
- Kelas `Kucing` mewarisi dari `Hewan` menggunakan `extends`.
- Properti `warna` ditambahkan di kelas ini.
- Metode `kucingMakan()` menambahkan perilaku unik setelah memanggil `super.makan()`.
- **Kedua pendekatan sama-sama valid**, hanya berbeda dalam lokasi penetapan nilai default:
  - Pendekatan A lebih fleksibel, bisa ditimpa dari luar.
  - Pendekatan B lebih ketat, nilainya dikunci dalam kelas turunan.

---

## 3. Pembuatan Objek dan Output

```javascript
let Kitty = new Kucing('Kitty', 'orange');

console.log(Kitty.jenis);        // Output: kucing
console.log(Kitty.kucingMakan());
```

### Penjelasan:
- Objek `Kitty` dibuat dari kelas `Kucing`.
- Properti `jenis` otomatis bernilai `'kucing'` karena diberikan default di konstruktor atau di `super()`.
- Metode `kucingMakan()` akan mencetak dua baris:
  1. "Kitty sedang makan"
  2. "makannya lahap sekali"

### Hasil di konsol:
```text
kucing
Kitty sedang makan
makannya lahap sekali
```

---

## Ringkasan Materi:
- Gunakan `class` untuk membuat blueprint objek.
- Gunakan `extends` untuk mewarisi kelas lain.
- Gunakan `super()` untuk memanggil konstruktor atau metode dari kelas induk.
- Nilai default properti bisa dibuat:
  - Di parameter konstruktor (`constructor(nama, jenis = 'kucing')`)
  - Langsung di pemanggilan `super()` (`super(nama, 'kucing')`)
- Pilih sesuai kebutuhan: fleksibilitas atau keketatan nilai.


