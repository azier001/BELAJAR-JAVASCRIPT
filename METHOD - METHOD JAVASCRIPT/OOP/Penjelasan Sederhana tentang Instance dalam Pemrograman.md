# Penjelasan Sederhana tentang Instance dalam Pemrograman

## Analogi: Cetakan dan Produk

Bayangkan kamu punya cetakan kue berbentuk bintang. Dari satu cetakan itu, kamu bisa membuat banyak kue yang bentuknya sama, tapi bisa punya rasa atau warna yang berbeda.

- **Cetakan** = blueprint / cetak biru → dalam kode disebut class atau function constructor
- **Kue yang jadi dari cetakan itu** = instance

## Dalam Kode JavaScript

```javascript
function Mobil(merk, type, tahun) {
  this.merk = merk;
  this.type = type;
  this.tahun = tahun;

  this.start = function() {
    console.log(`${this.merk} dimulai`);
  };

  this.info = function() {
    console.log(
      `Mobil: ${this.merk} ${this.type}, tahun pembuatan: ${this.tahun}`
    );
  };
}
```

Bagian di atas adalah cetakan atau constructor function yang digunakan untuk membuat mobil.

## Membuat Instance

```javascript
const mobil1 = new Mobil('Toyota', 'Avanza', 2021);
const mobil2 = new Mobil('Honda', 'Civic', 2020);
```

Dengan kode di atas, kamu sedang membuat dua buah mobil nyata dari cetakan itu.
Nah, `mobil1` dan `mobil2` itulah yang disebut instance dari `Mobil`.

## Ringkasnya

- Instance adalah objek nyata yang dibuat dari constructor (atau class).
- Dalam contoh ini, `mobil1` dan `mobil2` adalah instance dari `Mobil`.
