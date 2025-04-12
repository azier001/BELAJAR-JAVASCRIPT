
# Penjelasan Sederhana Fungsi `this` dalam JavaScript

Dalam kode di bawah, kata kunci `this` digunakan untuk merujuk pada **objek tempat fungsi itu berada**, yaitu objek `mobil`.

```javascript
let mobil = {
  merk: 'Toyota',
  type: 'Avanza',
  tahun: 2021,

  start: function () {
    console.log('Mobil mulai');
  },

  info: function () {
    console.log(
      `Mobil ${this.merk}, dengan type ${this.type} dan tahun pembuatan ${this.tahun}`
    );
  },
};

mobil.start();
mobil.info();
```

## Fungsi `this` di Dalam Objek

Di dalam **method** (fungsi yang berada dalam objek), `this` merujuk ke **objek itu sendiri**.

Contohnya:

```javascript
this.merk   // sama seperti mobil.merk
this.type   // sama seperti mobil.type
this.tahun  // sama seperti mobil.tahun
```

## Penjelasan dari Kode

Pada bagian berikut:

```javascript
info: function () {
  console.log(
    `Mobil ${this.merk}, dengan type ${this.type} dan tahun pembuatan ${this.tahun}`
  );
}
```

Jika tidak pakai `this`, maka JavaScript **tidak akan tahu** dari mana harus ambil `merk`, `type`, dan `tahun`.

Dengan `this`, kita bilang: "**Ambil properti dari objek ini (`mobil`)**".

## Kesimpulan

`this` dipakai supaya **fungsi (method) dalam objek bisa mengakses data/properti milik objek itu sendiri**.

Tanpa `this`, kita **tidak bisa mengakses** `merk`, `type`, atau `tahun` dari dalam method seperti `info()`.
