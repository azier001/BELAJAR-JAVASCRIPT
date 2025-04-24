# Polymorphism dalam OOP (Object-Oriented Programming) - JavaScript

Polymorphism (polimorfisme) adalah konsep dalam pemrograman berorientasi objek yang memungkinkan penggunaan method yang sama pada objek-objek dari class yang berbeda. Konsep ini membantu dalam menyederhanakan kode dan meningkatkan fleksibilitas program.

## Contoh Implementasi Polymorphism

```javascript
// Kelas induk
class Hewan {
  bersuara() {
    console.log("Hewan bersuara");
  }
}

// Kelas turunan: Kucing
class Kucing extends Hewan {
  bersuara() {
    console.log("Miau");
  }
}

// Kelas turunan: Anjing
class Anjing extends Hewan {
  bersuara() {
    console.log("Guk Guk!");
  }
}

// Penggunaan objek
let hewan = new Hewan();
hewan.bersuara(); // Output: Hewan bersuara

let kucing = new Kucing();
kucing.bersuara(); // Output: Miau

let anjing = new Anjing();
anjing.bersuara(); // Output: Guk Guk!
```

> **Catatan:** Method `bersuara()` didefinisikan ulang di masing-masing class turunan. Ini merupakan contoh dari polymorphism, karena meskipun nama method sama, perilakunya berbeda tergantung pada objek yang mengaksesnya.

## Manfaat Polymorphism

- **Reusability:** Kode dapat digunakan ulang tanpa perlu menulis ulang method dengan nama berbeda.
- **Maintainability:** Mudah dikelola karena struktur class yang lebih bersih.
- **Scalability:** Memudahkan pengembangan aplikasi yang lebih kompleks.

## Dynamic Dispatch

Polymorphism dalam JavaScript menggunakan mekanisme yang disebut _dynamic dispatch_, di mana method yang dipanggil ditentukan pada saat runtime berdasarkan tipe objek sebenarnya, bukan tipe referensinya.

```javascript
function suaraHewan(hewan) {
  hewan.bersuara();
}

suaraHewan(new Kucing()); // Output: Miau
suaraHewan(new Anjing()); // Output: Guk Guk!
```

Fungsi `suaraHewan()` menunjukkan bahwa kita bisa memanfaatkan polymorphism untuk memanggil method yang sesuai dengan objek yang diberikan, tanpa harus mengetahui tipe spesifik dari objek tersebut.

## Kesimpulan

Polymorphism adalah konsep penting dalam OOP yang memberikan fleksibilitas dalam penggunaan method dan membantu menulis kode yang lebih bersih, reusable, dan mudah dikembangkan. Dalam JavaScript, ini diimplementasikan melalui pewarisan (inheritance) dan _method overriding_.

