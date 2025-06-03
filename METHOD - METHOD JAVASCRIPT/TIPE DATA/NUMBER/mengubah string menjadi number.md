# 🔢 Mengubah String ke Number di JavaScript

> **Dokumentasi Lengkap untuk Belajar JavaScript**  
> Panduan praktis dengan contoh dan penjelasan detail

---

## 📋 Daftar Isi

1. [Pengenalan](#-pengenalan)
2. [Metode Konversi](#-metode-konversi)
3. [Perbandingan Metode](#-perbandingan-metode)
4. [Contoh Praktis](#-contoh-praktis)
5. [Tips dan Peringatan](#-tips-dan-peringatan)
6. [Kesimpulan](#-kesimpulan)

---

## 🎯 Pengenalan

Dalam JavaScript, sering kali kita perlu mengubah data string menjadi number untuk melakukan operasi matematika. Ada beberapa cara untuk melakukan konversi ini, masing-masing dengan karakteristik dan kegunaan yang berbeda.

### Mengapa Perlu Konversi?

```javascript
// Masalah tanpa konversi
let a = "10";
let b = "20";
console.log(a + b); // "1020" (string concatenation)

// Dengan konversi
let c = Number("10");
let d = Number("20");
console.log(c + d); // 30 (mathematical addition)
```

---

## 🛠️ Metode Konversi

### 1. `parseInt()` - Konversi ke Integer

**Deskripsi:** Mengubah string menjadi bilangan bulat (integer)

**Sintaks:**
```javascript
parseInt(string, radix)
```

**Contoh:**
```javascript
// Contoh dasar
let str1 = "123";
let str2 = "123.45";
let str3 = "123abc";
let str4 = "abc123";

console.log(parseInt(str1));     // ✅ 123
console.log(parseInt(str2));     // ✅ 123 (bagian desimal diabaikan)
console.log(parseInt(str3));     // ✅ 123 (karakter non-angka diabaikan)
console.log(parseInt(str4));     // ❌ NaN (dimulai dengan huruf)

// Dengan radix (basis bilangan)
console.log(parseInt("1010", 2));  // ✅ 10 (biner ke desimal)
console.log(parseInt("FF", 16));   // ✅ 255 (hex ke desimal)
console.log(parseInt("77", 8));    // ✅ 63 (oktal ke desimal)
```

**Karakteristik:**
- ✅ Toleran terhadap karakter non-angka di akhir
- ✅ Mendukung berbagai basis bilangan
- ❌ Mengabaikan bagian desimal
- ❌ Gagal jika dimulai dengan huruf

---

### 2. `parseFloat()` - Konversi ke Float

**Deskripsi:** Mengubah string menjadi bilangan desimal (floating point)

**Sintaks:**
```javascript
parseFloat(string)
```

**Contoh:**
```javascript
let str1 = "123.45";
let str2 = "123.45abc";
let str3 = "abc123.45";
let str4 = "3.14159";
let str5 = "123.45.67";

console.log(parseFloat(str1));   // ✅ 123.45
console.log(parseFloat(str2));   // ✅ 123.45 (karakter non-angka diabaikan)
console.log(parseFloat(str3));   // ❌ NaN (dimulai dengan huruf)
console.log(parseFloat(str4));   // ✅ 3.14159
console.log(parseFloat(str5));   // ✅ 123.45 (titik kedua diabaikan)
```

**Karakteristik:**
- ✅ Menangani bilangan desimal
- ✅ Toleran terhadap karakter non-angka di akhir
- ❌ Gagal jika dimulai dengan huruf
- ❌ Tidak mendukung radix

---

### 3. `Number()` - Konversi Ketat

**Deskripsi:** Mengubah berbagai tipe data menjadi number dengan aturan ketat

**Sintaks:**
```javascript
Number(value)
```

**Contoh:**
```javascript
// String number
let str1 = "123";
let str2 = "123.45";
let str3 = "123abc";
let str4 = "";
let str5 = "   456   ";

console.log(Number(str1));    // ✅ 123
console.log(Number(str2));    // ✅ 123.45
console.log(Number(str3));    // ❌ NaN (ketat, harus angka semua)
console.log(Number(str4));    // ✅ 0 (string kosong = 0)
console.log(Number(str5));    // ✅ 456 (whitespace diabaikan)

// Boolean
console.log(Number(true));    // ✅ 1
console.log(Number(false));   // ✅ 0

// Null dan undefined
console.log(Number(null));    // ✅ 0
console.log(Number(undefined)); // ❌ NaN
```

**Karakteristik:**
- ✅ Konversi lengkap untuk berbagai tipe data
- ✅ Menangani boolean, null, undefined
- ✅ Mengabaikan whitespace di awal/akhir
- ❌ Sangat ketat dengan format string

---

### 4. Unary Plus `(+)` - Cara Tercepat

**Deskripsi:** Operator unary plus untuk konversi cepat

**Sintaks:**
```javascript
+value
```

**Contoh:**
```javascript
let str1 = "123";
let str2 = "123.45";
let str3 = "abc";
let str4 = "";
let bool1 = true;
let bool2 = false;

console.log(+str1);    // ✅ 123
console.log(+str2);    // ✅ 123.45
console.log(+str3);    // ❌ NaN
console.log(+str4);    // ✅ 0
console.log(+bool1);   // ✅ 1
console.log(+bool2);   // ✅ 0
```

**Karakteristik:**
- ✅ Paling ringkas dan cepat
- ✅ Setara dengan `Number()`
- ✅ Sering digunakan oleh developer berpengalaman

---

### 5. `Math.floor()`, `Math.ceil()`, `Math.round()` - Konversi + Pembulatan

**Deskripsi:** Mengubah ke number sekaligus pembulatan

**Sintaks:**
```javascript
Math.floor(value)   // Bulatkan ke bawah
Math.ceil(value)    // Bulatkan ke atas  
Math.round(value)   // Bulatkan normal
```

**Contoh:**
```javascript
let str = "123.67";

console.log(Math.floor(str));  // ✅ 123 (bulatkan ke bawah)
console.log(Math.ceil(str));   // ✅ 124 (bulatkan ke atas)
console.log(Math.round(str));  // ✅ 124 (bulatkan normal)

// Contoh dengan bilangan negatif
let negStr = "-123.67";
console.log(Math.floor(negStr));  // ✅ -124
console.log(Math.ceil(negStr));   // ✅ -123
console.log(Math.round(negStr));  // ✅ -124
```

---

### 6. `.valueAsNumber` - Khusus HTML Input

**Deskripsi:** Properti khusus untuk elemen input HTML

**Sintaks:**
```javascript
inputElement.valueAsNumber
```

**Contoh HTML:**
```html
<input type="number" id="myInput" value="123.45">
<input type="range" id="slider" min="0" max="100" value="50">
<input type="date" id="dateInput" value="2024-01-01">
```

**Contoh JavaScript:**
```javascript
let numberInput = document.getElementById("myInput");
let rangeInput = document.getElementById("slider");
let dateInput = document.getElementById("dateInput");

console.log(numberInput.value);         // "123.45" (string)
console.log(numberInput.valueAsNumber); // 123.45 (number)

console.log(rangeInput.value);          // "50" (string)
console.log(rangeInput.valueAsNumber);  // 50 (number)

console.log(dateInput.value);           // "2024-01-01" (string)
console.log(dateInput.valueAsNumber);   // 1704067200000 (timestamp)
```

**Input Types yang Mendukung:**
- `number`
- `range`
- `date`
- `datetime-local`
- `month`
- `time`
- `week`

---

## 📊 Perbandingan Metode

| Input | `parseInt()` | `parseFloat()` | `Number()` | `+(unary)` | Keterangan |
|-------|--------------|----------------|------------|------------|------------|
| `"123"` | `123` | `123` | `123` | `123` | ✅ Semua berhasil |
| `"123.45"` | `123` | `123.45` | `123.45` | `123.45` | parseInt hilangkan desimal |
| `"123abc"` | `123` | `123` | `NaN` | `NaN` | parse* toleran, Number ketat |
| `"abc123"` | `NaN` | `NaN` | `NaN` | `NaN` | ❌ Semua gagal |
| `""` | `NaN` | `NaN` | `0` | `0` | String kosong |
| `"   456   "` | `456` | `456` | `456` | `456` | Whitespace diabaikan |
| `true` | `NaN` | `NaN` | `1` | `1` | Boolean ke number |
| `false` | `NaN` | `NaN` | `0` | `0` | Boolean ke number |
| `null` | `NaN` | `NaN` | `0` | `0` | Null ke number |
| `undefined` | `NaN` | `NaN` | `NaN` | `NaN` | Undefined ke number |

---

## 💡 Contoh Praktis

### 1. Validasi Input Form

```javascript
function validateNumberInput(input) {
    const value = input.value;
    const number = Number(value);
    
    if (isNaN(number)) {
        console.log("❌ Input bukan angka valid");
        return false;
    }
    
    console.log(`✅ Angka valid: ${number}`);
    return true;
}

// Penggunaan
const userInput = document.getElementById('userNumber');
validateNumberInput(userInput);
```

### 2. Konversi Mata Uang

```javascript
function convertCurrency(amount, rate) {
    // Pastikan kedua parameter adalah number
    const numAmount = Number(amount);
    const numRate = Number(rate);
    
    if (isNaN(numAmount) || isNaN(numRate)) {
        return "Error: Input harus berupa angka";
    }
    
    return numAmount * numRate;
}

// Penggunaan
console.log(convertCurrency("100", "15000")); // 1500000
console.log(convertCurrency("abc", "15000")); // Error: Input harus berupa angka
```

### 3. Parsing Data dari API

```javascript
function processApiData(data) {
    return {
        id: parseInt(data.id),
        price: parseFloat(data.price),
        quantity: Number(data.quantity),
        isActive: Boolean(+data.isActive) // konversi "1"/"0" ke boolean
    };
}

// Contoh data dari API
const apiResponse = {
    id: "123",
    price: "99.99",
    quantity: "5",
    isActive: "1"
};

console.log(processApiData(apiResponse));
// Output: { id: 123, price: 99.99, quantity: 5, isActive: true }
```

### 4. Calculator Sederhana

```javascript
function simpleCalculator(a, b, operation) {
    // Konversi input ke number
    const numA = +a; // menggunakan unary plus
    const numB = +b;
    
    // Validasi
    if (isNaN(numA) || isNaN(numB)) {
        return "Error: Input harus berupa angka";
    }
    
    switch(operation) {
        case '+': return numA + numB;
        case '-': return numA - numB;
        case '*': return numA * numB;
        case '/': return numA / numB;
        default: return "Error: Operasi tidak valid";
    }
}

// Penggunaan
console.log(simpleCalculator("10", "5", "+")); // 15
console.log(simpleCalculator("10.5", "2.5", "*")); // 26.25
```

---

## ⚠️ Tips dan Peringatan

### ✅ Best Practices

1. **Selalu Validasi Hasil Konversi**
   ```javascript
   const userInput = "123abc";
   const number = Number(userInput);
   
   if (Number.isNaN(number)) {
       console.log("Input tidak valid");
   } else {
       console.log(`Angka: ${number}`);
   }
   ```

2. **Gunakan Metode yang Tepat**
   ```javascript
   // Untuk ID atau index (integer)
   const userId = parseInt(userIdString);
   
   // Untuk harga atau nilai desimal
   const price = parseFloat(priceString);
   
   // Untuk validasi ketat
   const strictNumber = Number(inputString);
   
   // Untuk konversi cepat
   const quickNumber = +inputString;
   ```

3. **Handling Edge Cases**
   ```javascript
   function safeNumberConversion(value, defaultValue = 0) {
       const number = Number(value);
       return Number.isNaN(number) ? defaultValue : number;
   }
   
   console.log(safeNumberConversion("123"));    // 123
   console.log(safeNumberConversion("abc"));    // 0
   console.log(safeNumberConversion("abc", -1)); // -1
   ```

### ⚠️ Peringatan Penting

1. **Perbedaan `isNaN()` vs `Number.isNaN()`**
   ```javascript
   console.log(isNaN("abc"));        // true (konversi dulu)
   console.log(Number.isNaN("abc")); // false (cek tipe dulu)
   
   // Lebih aman menggunakan Number.isNaN()
   console.log(Number.isNaN(Number("abc"))); // true
   ```

2. **Floating Point Precision**
   ```javascript
   console.log(0.1 + 0.2);                    // 0.30000000000000004
   console.log(parseFloat((0.1 + 0.2).toFixed(2))); // 0.3
   ```

3. **String Kosong vs Undefined**
   ```javascript
   console.log(Number(""));        // 0
   console.log(Number(undefined)); // NaN
   console.log(Number(null));      // 0
   ```

4. **Octal Parsing dengan parseInt**
   ```javascript
   console.log(parseInt("08"));    // 8 (modern JS)
   console.log(parseInt("08", 10)); // 8 (lebih aman)
   ```

---

## 🎯 Kapan Menggunakan Metode Mana?

### 🔧 `parseInt()` - Gunakan untuk:
- ✅ Mengambil ID dari string
- ✅ Parsing integer dari input campuran
- ✅ Konversi basis bilangan
- ✅ Mengabaikan unit (contoh: "100px" → 100)

### 🔧 `parseFloat()` - Gunakan untuk:
- ✅ Harga, nilai desimal
- ✅ Koordinat, dimensi
- ✅ Parsing angka dari string campuran

### 🔧 `Number()` - Gunakan untuk:
- ✅ Validasi input ketat
- ✅ Konversi boolean/null
- ✅ API yang membutuhkan number murni

### 🔧 `Unary +` - Gunakan untuk:
- ✅ Konversi cepat dalam expression
- ✅ Code yang perlu ringkas
- ✅ Performance critical code

### 🔧 `.valueAsNumber` - Gunakan untuk:
- ✅ Input HTML number/range/date
- ✅ Menghindari manual parsing
- ✅ Konsistensi dengan DOM API

---

## 📝 Kesimpulan

Pemahaman tentang konversi string ke number adalah fundamental dalam JavaScript. Setiap metode memiliki kegunaan spesifik:

1. **`parseInt()`** - Terbaik untuk integer dan string campuran
2. **`parseFloat()`** - Ideal untuk bilangan desimal
3. **`Number()`** - Konversi universal dan validasi ketat
4. **`+` (unary)** - Cara tercepat dan tersingkat
5. **`.valueAsNumber`** - Solusi terbaik untuk HTML input

Kunci sukses adalah memahami karakteristik masing-masing metode dan memilih yang tepat sesuai kebutuhan. Selalu ingat untuk memvalidasi hasil konversi dan menangani edge cases dengan baik.

---

## 📚 Referensi Tambahan

- [MDN Web Docs - parseInt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)
- [MDN Web Docs - parseFloat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)
- [MDN Web Docs - Number()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
- [MDN Web Docs - HTMLInputElement.valueAsNumber](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/valueAsNumber)

