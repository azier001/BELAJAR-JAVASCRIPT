# Encapsulation dalam JavaScript

Encapsulation adalah konsep dalam pemrograman berorientasi objek (OOP) yang digunakan untuk membatasi akses ke properti dan method dari sebuah objek. Tujuan utama dari encapsulation adalah untuk melindungi data internal objek agar tidak dapat diakses atau dimodifikasi secara langsung dari luar objek tersebut.

## 1. Encapsulation dengan Underscore (_)

Pada JavaScript ES6 dan sebelumnya, encapsulation umumnya dilakukan secara konvensional dengan menambahkan simbol underscore (`_`) di awal nama properti. Ini menandakan bahwa properti tersebut sebaiknya dianggap sebagai "pribadi", meskipun tetap bisa diakses dari luar.

```javascript
class BankAccount {
  constructor(owner, balance) {
    this.owner = owner;
    this._balance = balance;
  }

  deposit(amount) {
    this._balance += amount;
    console.log(`Deposit : ${amount}`);
  }

  withdraw(amount) {
    if (amount > this._balance) {
      console.log(`Saldo tidak mencukupi`);
    } else {
      this._balance -= amount;
      console.log(`Withdraw : ${amount}`);
    }
  }

  getBalance() {
    console.log(`Saldo : ${this._balance}`);
  }
}

let akunAhmad = new BankAccount('Ahmad', 2000);
akunAhmad.deposit(1000);     // Output: Deposit : 1000
akunAhmad.withdraw(500);     // Output: Withdraw : 500
akunAhmad.getBalance();      // Output: Saldo : 2500

// Meskipun _balance dimaksudkan sebagai properti pribadi, tetap bisa diakses secara langsung:
console.log(akunAhmad._balance); // Output: 2500
```

## 2. Encapsulation dengan Private Field (#)

Sejak ES2022, JavaScript mendukung penulisan properti privat yang sebenarnya dengan menggunakan simbol `#`. Properti atau method dengan awalan `#` tidak bisa diakses dari luar class, menjadikannya lebih aman.

```javascript
class BankAccount {
  #balance;

  constructor(owner, balance) {
    this.owner = owner;
    this.#balance = balance;
  }

  deposit(amount) {
    this.#balance += amount;
  }

  getBalance() {
    console.log(`Saldo : ${this.#balance}`);
  }
}

let akunRanggo = new BankAccount("Ranggo", 1000);

// Akan error karena #balance adalah private
akunRanggo.#balance = 12000; // SyntaxError
console.log(akunRanggo.#balance); // SyntaxError
```

## 3. Encapsulation dengan Closure

Sebelum fitur private field, cara lain untuk mengimplementasikan encapsulation adalah dengan menggunakan closure. Ini dilakukan dengan mendefinisikan variabel di dalam fungsi constructor, dan hanya mengekspos method yang diperlukan.

```javascript
function BankAccount(owner, initialBalance) {
  let balance = initialBalance;

  this.owner = owner;

  this.deposit = function(amount) {
    balance += amount;
  };

  this.getBalance = function() {
    console.log(`Saldo : ${balance}`);
  };
}

let akunBudi = new BankAccount("Budi", 1500);
akunBudi.deposit(500);
akunBudi.getBalance(); // Output: Saldo : 2000

// Tidak bisa diakses langsung
console.log(akunBudi.balance); // Output: undefined
```

## Kesimpulan

Encapsulation sangat penting dalam desain sistem yang aman dan terstruktur. JavaScript menyediakan beberapa pendekatan untuk menerapkannya:

- **Underscore (`_`)**: Konvensi yang lemah untuk menandai properti privat.
- **Private Field (`#`)**: Solusi modern dan aman yang hanya tersedia di ES2022 ke atas.
- **Closure**: Teknik lama yang tetap efektif, terutama pada fungsi konstruktor.

Gunakan pendekatan yang sesuai dengan versi JavaScript yang Anda gunakan dan kebutuhan keamanan aplikasi Anda.

