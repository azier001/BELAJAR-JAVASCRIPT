# ES6 Classes: Cara Modern untuk Membuat Constructor Function OOP di JavaScript

Dengan ES6, JavaScript memperkenalkan sintaks `class` yang lebih mudah dipahami dan digunakan untuk membuat objek dan mengimplementasikan prinsip Object-Oriented Programming (OOP).

## Perbandingan Sintaks Function vs Class

### Sebelum ES6 - Constructor Function:
```javascript
function Mobil(merk, model, tahun) {
  this.merk = merk;
  this.model = model;
  this.tahun = tahun;

  this.start = function () {
    console.log('Mobil dimulai');
  };

  this.info = function () {
    console.log(`Mobil : ${this.merk} ${this.model}`);
  };
}
```

### Dengan ES6 - Class:
```javascript
class Mobil {
  constructor(merk, model, tahun) {
    this.merk = merk;
    this.model = model;
    this.tahun = tahun;
  }

  start() {
    console.log('Mobil dimulai');
  }

  info() {
    console.log(`Mobil : ${this.merk} ${this.model}`);
  }
}

let mobil1 = new Mobil('Toyota', 'Avanza', 2021);
let mobil2 = new Mobil('Honda', 'Civic', 2020);

mobil1.start(); // Mobil dimulai
mobil2.info();  // Mobil : Honda Civic
```

## Penjelasan Konsep

- **Class** adalah *blueprint* untuk membuat objek.
- **Constructor** adalah method khusus yang otomatis dipanggil saat objek dibuat dengan keyword `new`.
- Method seperti `start()` dan `info()` otomatis disimpan di prototype, sehingga tidak mengulang deklarasi setiap kali objek dibuat (lebih hemat memori).

## Inheritance (Pewarisan)
Kita bisa membuat class turunan dengan keyword `extends`.

```javascript
class Kendaraan {
  constructor(jenis) {
    this.jenis = jenis;
  }

  nyalakan() {
    console.log(`${this.jenis} dinyalakan`);
  }
}

class Mobil extends Kendaraan {
  constructor(merk, model, tahun) {
    super('Mobil');
    this.merk = merk;
    this.model = model;
    this.tahun = tahun;
  }

  info() {
    console.log(`${this.jenis} : ${this.merk} ${this.model} (${this.tahun})`);
  }
}

const m1 = new Mobil('Suzuki', 'Ertiga', 2022);
m1.nyalakan(); // Mobil dinyalakan
m1.info();      // Mobil : Suzuki Ertiga (2022)
```

## Getter dan Setter
Class ES6 juga mendukung penggunaan getter dan setter untuk mengakses atau mengubah properti dengan cara yang lebih aman.

```javascript
class Motor {
  constructor(merk) {
    this._merk = merk;
  }

  get merk() {
    return this._merk;
  }

  set merk(nilai) {
    this._merk = nilai.toUpperCase();
  }
}

const mtr = new Motor('yamaha');
console.log(mtr.merk); // yamaha
mtr.merk = 'honda';
console.log(mtr.merk); // HONDA
```

## Kesimpulan

- Class ES6 memudahkan penulisan OOP di JavaScript.
- Mendukung constructor, inheritance, method di prototype, serta getter/setter.
- Membuat kode lebih bersih dan modular.

