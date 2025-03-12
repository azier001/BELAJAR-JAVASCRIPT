# Function Expression dalam JavaScript

## Pengertian
Function Expression adalah cara mendeklarasikan fungsi dalam JavaScript dengan menyimpannya ke dalam sebuah variabel. Berbeda dengan Function Declaration, function expression tidak di-hoisting sehingga harus dideklarasikan terlebih dahulu sebelum digunakan.

## Jenis Function Expression
### 1. Anonymous Function Expression
Fungsi tanpa nama yang disimpan dalam variabel:
```js
const greet = function() {
    return "Hello, World!";
};

console.log(greet()); // Output: Hello, World!
```

### 2. Named Function Expression
Fungsi dengan nama yang disimpan dalam variabel:
```js
const factorial = function fact(n) {
    return (n === 0) ? 1 : n * fact(n - 1);
};

console.log(factorial(5)); // Output: 120
```

### 3. Function Expression dengan Parameter
Function expression juga bisa menerima parameter:
```js
const add = function(a, b) {
    return a + b;
};

console.log(add(3, 5)); // Output: 8
```

### 4. Arrow Function Expression
Arrow function adalah bentuk ringkas dari function expression:
```js
const multiply = (x, y) => x * y;

console.log(multiply(4, 6)); // Output: 24
```

## Perbedaan dengan Function Declaration
| Aspek | Function Expression | Function Declaration |
|-------|----------------------|----------------------|
| Hoisting | Tidak di-hoist | Di-hoist |
| Nama Fungsi | Bisa anonymous atau named | Harus memiliki nama |
| Kapan Bisa Dipanggil? | Setelah dideklarasikan | Bisa sebelum dideklarasikan |

## Kesimpulan
Function Expression adalah cara fleksibel untuk mendefinisikan fungsi dalam JavaScript. Dengan pemahaman yang baik, kita dapat memilih antara function expression dan function declaration sesuai kebutuhan dalam pengembangan aplikasi.

