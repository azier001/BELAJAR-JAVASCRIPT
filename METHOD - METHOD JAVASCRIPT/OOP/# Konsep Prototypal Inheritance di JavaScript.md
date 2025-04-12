# Konsep Prototypal Inheritance di JavaScript

JavaScript menggunakan **Prototypal Inheritance**, yaitu sistem pewarisan di mana objek dapat mewarisi properti dan method dari objek lain melalui *prototype*.

## Contoh Dasar

```javascript
function Hewan(nama, jenis) {
  this.nama = nama;
  this.jenis = jenis;
}

Hewan.prototype.makan = function() {
  console.log(`${this.nama} sedang makan`);
};

let kucing = new Hewan('Kitty', 'kucing');
kucing.makan(); // output: Kitty sedang makan
```

## Penjelasan

1. **Fungsi Konstruktor (Constructor Function):**  
   `function Hewan(nama, jenis)` adalah sebuah *constructor function* yang digunakan untuk membuat objek `Hewan`. Saat objek dibuat menggunakan `new Hewan(...)`, properti `nama` dan `jenis` akan disimpan di dalam objek tersebut.

2. **Menambahkan Method ke Prototype:**  
   `Hewan.prototype.makan` menambahkan method `makan` ke prototype dari objek `Hewan`. Artinya, semua objek yang dibuat dengan `new Hewan()` akan mewarisi method `makan` ini.

3. **Pewarisan Melalui Prototype:**  
   Ketika kita membuat objek `kucing`, objek tersebut bisa menggunakan method `makan()` meskipun method itu tidak langsung didefinisikan di dalam objek `kucing`. Ini karena JavaScript akan mencarinya di prototype chain.

4. **Output:**  
   Saat kita memanggil `kucing.makan()`, akan tampil `Kitty sedang makan`.

## Pewarisan Antar Objek

```javascript
// Membuat constructor untuk Kucing yang mewarisi dari Hewan
function Kucing(nama, ras) {
  Hewan.call(this, nama, 'kucing');
  this.ras = ras;
}

// Mewarisi prototype dari Hewan
Kucing.prototype = Object.create(Hewan.prototype);
Kucing.prototype.constructor = Kucing;

// Menambahkan method khusus untuk Kucing
Kucing.prototype.meong = function() {
  console.log(`${this.nama} berbunyi meong!`);
};

let persia = new Kucing('Fluffy', 'Persia');
persia.makan(); // Output: Fluffy sedang makan
persia.meong(); // Output: Fluffy berbunyi meong!
```

## Keuntungan Prototypal Inheritance

1. **Efisiensi Memori:**  
   Method didefinisikan sekali pada prototype, bukan untuk setiap instance.

2. **Fleksibilitas:**  
   Prototype dapat dimodifikasi pada runtime, mempengaruhi semua objek.

3. **Dynamic Binding:**  
   Objek mengakses property terbaru dari prototype saat dibutuhkan.

## Contoh Modern dengan Class (ES6+)

```javascript
class Hewan {
  constructor(nama, jenis) {
    this.nama = nama;
    this.jenis = jenis;
  }
  
  makan() {
    console.log(`${this.nama} sedang makan`);
  }
}

class Kucing extends Hewan {
  constructor(nama, ras) {
    super(nama, 'kucing');
    this.ras = ras;
  }
  
  meong() {
    console.log(`${this.nama} berbunyi meong!`);
  }
}

const kitty = new Kucing('Kitty', 'Anggora');
kitty.makan(); // Output: Kitty sedang makan
kitty.meong(); // Output: Kitty berbunyi meong!
```

*Catatan: Sintaks `class` di ES6 hanyalah "syntactic sugar" - di bawah hood, JavaScript tetap menggunakan prototypal inheritance.*
