# Dokumentasi Arrow Function di JavaScript

## Pengantar
Arrow function adalah cara penulisan fungsi yang lebih ringkas dibandingkan function biasa. Arrow function diperkenalkan dalam ES6 dan memiliki beberapa keunggulan utama:

1. **Sintaks lebih ringkas**
2. **Tidak memiliki binding sendiri terhadap `this`** (menggunakan lexical scope)
3. **Implicit return** (jika hanya satu ekspresi, tidak perlu `return`)

---

## Sintaks Dasar
```javascript
// Function biasa
function tambah(a, b) {
  return a + b;
}

// Arrow function
const tambah = (a, b) => a + b;
console.log(tambah(5, 3)); // Output: 8
```

---

## Arrow Function Tanpa Parameter
```javascript
const sayHello = () => console.log("Hello, Dunia!");
sayHello(); // Output: Hello, Dunia!
```

---

## Arrow Function dengan Satu Parameter (Tanpa Kurung)
```javascript
const square = x => x * x;
console.log(square(4)); // Output: 16
```

---

## Arrow Function dengan `return` dan Beberapa Baris Kode
```javascript
const multiply = (a, b) => {
  let result = a * b;
  return result;
};
console.log(multiply(4, 5)); // Output: 20
```

---

## Arrow Function dalam Callback (`map`, `filter`, `reduce`)
```javascript
const numbers = [1, 2, 3, 4, 5];

// Menggunakan map untuk mengalikan setiap elemen dengan 2
const doubled = numbers.map(num => num * 2);
console.log(doubled); // Output: [2, 4, 6, 8, 10]
```

---

## Arrow Function dan `this`
Arrow function tidak memiliki binding sendiri terhadap `this`, sehingga sering digunakan dalam konteks asynchronous atau event listener.

```javascript
const person = {
  name: "Budi",
  greet: function() {
    setTimeout(() => {
      console.log(`Halo, nama saya ${this.name}`);
    }, 1000);
  }
};
person.greet(); // Output: Halo, nama saya Budi
```

Jika menggunakan function biasa dalam `setTimeout`, maka `this` akan `undefined` karena referensinya berubah.

---

## Kesimpulan
Arrow function adalah fitur yang sangat berguna dalam JavaScript modern, terutama untuk menulis fungsi dengan lebih ringkas dan menghindari masalah dengan `this`. Namun, perlu diingat bahwa arrow function **tidak bisa digunakan sebagai constructor** dan tidak memiliki akses ke `arguments` secara langsung.

