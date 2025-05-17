# 🧠 Abstraction dalam JavaScript

## 📌 Apa itu Abstraction (Abstraksi)?
**Abstraksi** adalah salah satu konsep dasar dalam *Object-Oriented Programming* (OOP). Abstraksi memungkinkan kita:
- Menyembunyikan detail implementasi dari pengguna.
- Menampilkan hanya fitur-fitur penting dari suatu objek.
- Menyederhanakan kompleksitas program.

> Dalam bahasa seperti JavaScript yang tidak memiliki dukungan bawaan untuk kelas abstrak atau interface seperti Java atau C#, abstraksi bisa disimulasikan dengan teknik tertentu.

---

## 🛠️ Simulasi Abstraksi di JavaScript

```javascript
// Kelas Abstrak
class Shape {
  constructor(name) {
    if (this.constructor === Shape) {
      throw new Error('Cannot instantiate abstract class');
    }
    this.name = name;
  }

  // Method abstrak
  calculateArea() {
    throw new Error('Method "calculateArea()" must be implemented');
  }
}
```

- `Shape` adalah **kelas abstrak**: tidak boleh di-*instantiate* secara langsung.
- Method `calculateArea()` adalah **method abstrak**: harus diimplementasikan oleh subclass.

---

## 🧱 Contoh Implementasi: Rectangle

```javascript
class Rectangle extends Shape {
  constructor(width, height) {
    super('Rectangle');
    this.width = width;
    this.height = height;
  }

  // Implementasi dari method abstrak
  calculateArea() {
    return this.width * this.height;
  }
}

let myRect = new Rectangle(10, 4);
console.log(myRect.calculateArea()); // Output: 40
```

### 💡 Penjelasan:
- `Rectangle` adalah turunan dari `Shape`.
- Harus mengimplementasikan method `calculateArea()`.
- Jika tidak diimplementasikan, akan menghasilkan error dari method abstrak di superclass.

---

## 🔍 Mengapa Abstraksi Penting?
- Mengurangi kompleksitas kode.
- Memudahkan kolaborasi tim (pengembang cukup tahu "apa yang dilakukan", bukan "bagaimana dilakukan").
- Meningkatkan fleksibilitas dan skalabilitas dalam desain aplikasi.

---

## 📚 Contoh Lain: Circle

```javascript
class Circle extends Shape {
  constructor(radius) {
    super('Circle');
    this.radius = radius;
  }

  calculateArea() {
    return Math.PI * this.radius * this.radius;
  }
}

let myCircle = new Circle(5);
console.log(myCircle.calculateArea()); // Output: 78.53981633974483
```

---

## 📦 Kesimpulan

- **Abstraksi** menyederhanakan antarmuka objek.
- JavaScript tidak memiliki fitur `abstract class` secara langsung, tetapi bisa disimulasikan.
- Abstraksi membuat kode lebih **modular**, **mudah diuji**, dan **mudah dikembangkan**.
