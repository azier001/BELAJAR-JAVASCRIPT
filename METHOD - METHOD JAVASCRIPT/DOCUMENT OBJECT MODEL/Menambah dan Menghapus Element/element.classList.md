# Dokumentasi element.classList pada DOM JavaScript

## 1. Pengenalan
`element.classList` adalah properti dalam DOM (Document Object Model) yang mengembalikan objek `DOMTokenList`, yang berisi daftar kelas (CSS classes) yang dimiliki oleh suatu elemen HTML. Properti ini memungkinkan kita untuk dengan mudah menambah, menghapus, atau memeriksa kelas dari elemen tanpa perlu mengubah nilai `className` secara langsung.

## 2. Metode dalam element.classList
Berikut adalah metode yang tersedia dalam `element.classList`:

### a. `add(class1, class2, ...)`
Menambahkan satu atau lebih kelas ke elemen. Jika kelas sudah ada, maka tidak akan ditambahkan lagi.

#### Contoh:
```javascript
const element = document.querySelector(".my-element");
element.classList.add("new-class", "another-class");
```

### b. `remove(class1, class2, ...)`
Menghapus satu atau lebih kelas dari elemen.

#### Contoh:
```javascript
const element = document.querySelector(".my-element");
element.classList.remove("old-class", "another-old-class");
```

### c. `toggle(className, [force])`
- Jika kelas belum ada, maka akan ditambahkan.
- Jika kelas sudah ada, maka akan dihapus.
- Jika `force` diberikan (`true` atau `false`), maka akan menambahkan atau menghapus kelas berdasarkan nilai `force`.

#### Contoh:
```javascript
const element = document.querySelector(".my-element");
element.classList.toggle("active"); // Tambah jika belum ada, hapus jika sudah ada

element.classList.toggle("hidden", true); // Paksa tambahkan kelas

element.classList.toggle("hidden", false); // Paksa hapus kelas
```

### d. `contains(className)`
Memeriksa apakah elemen memiliki kelas tertentu. Mengembalikan nilai `true` jika kelas ada, dan `false` jika tidak ada.

#### Contoh:
```javascript
const element = document.querySelector(".my-element");
if (element.classList.contains("active")) {
    console.log("Elemen memiliki kelas 'active'");
} else {
    console.log("Elemen tidak memiliki kelas 'active'");
}
```

### e. `replace(oldClass, newClass)`
Mengganti kelas yang ada dengan kelas baru.

#### Contoh:
```javascript
const element = document.querySelector(".my-element");
element.classList.replace("old-class", "new-class");
```

### f. `length`
Menampilkan jumlah kelas yang ada dalam elemen.

#### Contoh:
```javascript
const element = document.querySelector(".my-element");
console.log(element.classList.length); // Output: jumlah kelas yang ada
```

### g. Iterasi classList
Kita dapat melakukan iterasi pada `classList` menggunakan `forEach` atau `for...of`.

#### Contoh:
```javascript
const element = document.querySelector(".my-element");
element.classList.forEach(className => {
    console.log(className);
});
```

Atau menggunakan `for...of`:
```javascript
for (let className of element.classList) {
    console.log(className);
}
```

## 3. Kesimpulan
`element.classList` adalah cara yang efisien untuk mengelola kelas CSS pada elemen dalam DOM. Dengan berbagai metode seperti `add()`, `remove()`, `toggle()`, dan `contains()`, kita dapat dengan mudah memanipulasi tampilan elemen di halaman web tanpa perlu mengubah nilai `className` secara langsung.

