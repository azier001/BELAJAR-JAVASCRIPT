# Object di JavaScript

Object di JavaScript adalah tipe data yang digunakan untuk menyimpan koleksi data dan entitas yang lebih kompleks. Sebuah object adalah pasangan antara **key** dan **value** (disebut juga properti).

---

## Membuat Object

### 1. Object Literal
Object dapat dibuat menggunakan **Object Literal** seperti contoh berikut:

```javascript
let mobil = {
  merk: 'Toyota',
  model: 'Avanza',
  tahun: 2014,
};

console.log(mobil);
// Output: { merk: 'Toyota', model: 'Avanza', tahun: 2014 }
```

### 2. Menggunakan Constructor `new Object()`
Cara lain untuk membuat object adalah dengan menggunakan **constructor `new Object()`**:

```javascript
let buku = new Object();

buku.judul = 'Belajar Javascript';
buku.penulis = 'Ahmad Reza';

console.log(buku);
// Output: { judul: 'Belajar Javascript', penulis: 'Ahmad Reza' }
```

---

## Mengakses Properti Object

### 1. Menggunakan Notasi Titik (Dot Notation)
```javascript
let mahasiswa = {
  nama: 'Budi',
  umur: 21,
  'jurusan mahasiswa': 'Teknik Informatika',
};

console.log(mahasiswa.nama);  // Output: 'Budi'
console.log(mahasiswa.umur);  // Output: 21
console.log(mahasiswa.jurusan); // Output: undefined
```

### 2. Menggunakan Notasi Kurung (Bracket Notation)
```javascript
console.log(mahasiswa['jurusan mahasiswa']);
// Output: 'Teknik Informatika'
```
> **Catatan:** Notasi kurung sangat berguna jika nama properti mengandung spasi atau karakter khusus.

---

## Menambah dan Mengubah Properti

### 1. Menambah Properti
```javascript
mahasiswa.alamat = 'Semarang';
console.log(mahasiswa);
// Output: { nama: 'Budi', umur: 21, 'jurusan mahasiswa': 'Teknik Informatika', alamat: 'Semarang' }
```

### 2. Mengubah Properti
```javascript
mahasiswa.nama = 'Ahmad';
console.log(mahasiswa);
// Output: { nama: 'Ahmad', umur: 21, 'jurusan mahasiswa': 'Teknik Informatika', alamat: 'Semarang' }
```

---

## Menghapus Properti
```javascript
delete mahasiswa.alamat;
console.log(mahasiswa);
// Output: { nama: 'Ahmad', umur: 21, 'jurusan mahasiswa': 'Teknik Informatika' }
```

---

## Nested Object
Object bisa memiliki object lain di dalamnya (nested object):

```javascript
let universitas = {
  nama: 'ITB',
  fakultas: {
    nama: 'Fakultas Teknik Industri',
    jurusan: 'Teknik Fisika'
  }
};

console.log(universitas);
// Output: { nama: 'ITB', fakultas: { nama: 'Fakultas Teknik Industri', jurusan: 'Teknik Fisika' } }
```

---

## Destructuring Object
Destructuring digunakan untuk mengambil nilai dari object ke dalam variabel dengan lebih ringkas.

```javascript
let { nama, umur } = mahasiswa;

console.log(nama); // Output: 'Ahmad'
console.log(umur); // Output: 21
```

---

## Object Methods
Selain properti, object juga bisa memiliki metode (fungsi yang berada di dalam object).

```javascript
let person = {
  name: 'Dina',
  greet: function () {
    return `Halo, nama saya ${this.name}`;
  }
};

console.log(person.greet());
// Output: 'Halo, nama saya Dina'
```

---

## Iterasi pada Object
Untuk melakukan iterasi pada object, kita bisa menggunakan **for...in** loop:

```javascript
for (let key in mahasiswa) {
  console.log(`${key}: ${mahasiswa[key]}`);
}
```

Output:
```
nama: Ahmad
umur: 21
jurusan mahasiswa: Teknik Informatika
```

---

## Kesimpulan
- **Object** adalah struktur data yang menyimpan pasangan **key-value**.
- Bisa dibuat dengan **Object Literal** atau **Constructor `new Object()`**.
- Properti bisa diakses dengan **dot notation** atau **bracket notation**.
- Bisa menambah, mengubah, dan menghapus properti kapan saja.
- Bisa memiliki **nested object** dan **method**.
- Bisa diiterasi menggunakan **for...in**.
Dengan memahami object di JavaScript, kita bisa lebih mudah mengelola data dalam program. Selamat belajar! 🚀

