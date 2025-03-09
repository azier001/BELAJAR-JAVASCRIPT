# Array di JavaScript

## Apa Itu Array?
Array adalah struktur data yang digunakan untuk menyimpan koleksi elemen, seperti angka atau string, dalam satu variabel. Di JavaScript, array dapat menyimpan berbagai tipe data sekaligus dan memiliki indeks yang dimulai dari 0.

## Membuat Array
### 1. Menggunakan Notasi Array Literal:
```javascript
let fruits = ['apple', 'banana', 'mango'];
console.log(fruits); // Output: [ 'apple', 'banana', 'mango' ]
```

### 2. Menggunakan `new Array()`:
```javascript
let num = new Array(1, 2, 3);
console.log(num); // Output: [ 1, 2, 3 ]
```

## Mengakses Elemen Array
```javascript
console.log(fruits[0]); // Output: 'apple'
console.log(fruits[1]); // Output: 'banana'
console.log(fruits[2]); // Output: 'mango'

console.log(num[0]); // Output: 1
console.log(num[1]); // Output: 2
console.log(num[2]); // Output: 3
```

## Menambah atau Mengubah Elemen Array
```javascript
fruits[3] = 'strawberry';
console.log(fruits); // Output: [ 'apple', 'banana', 'mango', 'strawberry' ]

fruits[0] = 'orange';
console.log(fruits); // Output: [ 'orange', 'banana', 'mango', 'strawberry' ]
```

## Manipulasi Array
```javascript
let numbers = [1, 2, 3];

// Metode `push()` mengembalikan nilai berupa **angka** yang menunjukkan panjang array setelah elemen baru ditambahkan.

let pushNumber =  numbers.push(4); // menambah elemen diakhir array
let pushNumber2 =  numbers.push(5, 6); // menambah elemen diakhir array
console.log(pushNumber); // output : 4 -> menambahkan 1 elemen, jadi panjang array menjadi 4
console.log(pushNumber2); // output : 6-> menambahkan 2 elemen, jadi panjang array menjadi 6
console.log(numbers); // output : [ 1, 2, 3, 4 ]

numbers.pop(); // Menghapus elemen terakhir array
console.log(numbers); // Output: [ 1, 2, 3 ]

numbers.shift(); // Menghapus elemen pertama array
console.log(numbers); // Output: [2, 3]

numbers.unshift(0); // Menambah elemen ke awal array
console.log(numbers); // Output: [0, 2 , 3]
```

### Menggabungkan Dua atau Lebih Array
```javascript
let numbers2 = [6, 7];
let newNumber = numbers.concat(numbers2);
console.log(newNumber); // Output: [ 0, 2, 3, 6, 7 ]
```

### Mengambil Bagian Tertentu dari Array
```javascript
let newSlice = newNumber.slice(1, 4);
console.log(newSlice); // Output: [ 2, 3, 6 ]
```

### Menggunakan `splice()`
```javascript
console.log(`Sebelum diterapkan method splice(): ${newNumber}`); // Output: 'Sebelum diterapkan method splice(): 0,2,3,6,7'

let newSplice = newNumber.splice(0, 1, 10);
console.log(newSplice); // Output: [0] -> Angka 0 yang dihapus
console.log(`Setelah diterapkan method splice(): ${newNumber}`); // Output: 'Setelah diterapkan method splice(): 10,2,3,6,7'
```

### Mencari Index dari Elemen Tertentu
```javascript
let findIndex = newNumber.indexOf(10);
console.log(findIndex); // Output: 0 -> Angka 10 berada di index ke-0
```

### Mengecek Keberadaan Elemen dalam Array
```javascript
let checkInclude = newNumber.includes(10);
console.log(checkInclude); // Output: true -> Karena angka 10 ada di dalam array
```

## Multidimensional Array (Array of Arrays)
```javascript
let matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
];

console.log(matrix[0][1]); // Output: 2 -> Elemen pada baris index ke-0, kolom index ke-1
console.log(matrix[1][2]); // Output: 6 -> Elemen pada baris index ke-1, kolom index ke-2
console.log(matrix[2][0]); // Output: 7 -> Elemen pada baris index ke-2, kolom index ke-0
```

