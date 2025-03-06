# **Penjelasan Detail tentang `split()` di JavaScript**

Method **`split()`** pada JavaScript digunakan untuk **memecah sebuah string menjadi array** berdasarkan pemisah tertentu (separator). Hasilnya adalah **array** yang berisi potongan-potongan string yang dipisahkan oleh separator yang diberikan.

----------

## **Sintaks:**


`string.split(separator, limit);` 

-   **`separator`** _(opsional)_ → String atau **Regular Expression (RegExp)** yang digunakan sebagai pemisah.
-   **`limit`** _(opsional)_ → Batas jumlah elemen dalam array hasil pemisahan.

> Jika **tidak ada `separator`**, maka hasilnya adalah **array dengan satu elemen** berisi string asli.  
> Jika **separator tidak ditemukan**, maka string tetap **tidak terpecah**.

----------

## **1. Menggunakan `split()` dengan Separator String**

### **Contoh 1: Memisahkan String Berdasarkan Spasi**

```javascript
let text = "Saya suka JavaScript";
let result = text.split(" ");

console.log(result);
// Output: [ 'Saya', 'suka', 'JavaScript' ]
```

> **Penjelasan:**
> 
> -   `" "` (spasi) digunakan sebagai pemisah.
> -   String dipecah menjadi tiga bagian: `"Saya"`, `"suka"`, dan `"JavaScript"`.

----------

## **2. Menggunakan `split()` dengan Batas (`limit`)**

### **Contoh 2: Memisahkan String dengan Batas Jumlah Elemen**

```javascript
let text = "apel, mangga, pisang, jeruk";
let result = text.split(", ", 2);

console.log(result);
// Output: [ 'apel', 'mangga' ]
```

> **Penjelasan:**
> 
> -   Separator `", "` digunakan untuk memisahkan string.
> -   `limit = 2` berarti hanya mengambil **dua elemen pertama** dalam array.

----------

## **3. Menggunakan `split()` dengan Karakter Tertentu**

### **Contoh 3: Memisahkan String Berdasarkan Huruf Tertentu**


```javascript
let text = "10-20-30-40";
let result = text.split("-");

console.log(result);
// Output: [ '10', '20', '30', '40' ]
```

> **Penjelasan:**
> 
> -   Separator `"-"` digunakan untuk memisahkan angka dalam string.

----------

## **4. Memisahkan String Menggunakan `split("")`**

Jika separator adalah `""` (string kosong), maka setiap **karakter dalam string** akan menjadi elemen array.

### **Contoh 4: Memecah String menjadi Array Karakter**

```javascript
let text = "Hello";
let result = text.split("");

console.log(result);
// Output: [ 'H', 'e', 'l', 'l', 'o' ]
```

> **Penjelasan:**
> 
> -   Setiap huruf dipisahkan menjadi elemen tersendiri dalam array.

----------

## **5. Menggunakan `split()` dengan Regular Expression (`RegExp`)**

Jika separator berupa **RegExp**, maka kita bisa lebih fleksibel dalam pemisahan string.

### **Contoh 5: Memisahkan dengan Beberapa Jenis Pemisah**

```javascript
let text = "apel; mangga, pisang jeruk";
let result = text.split(/[,; ]+/);

console.log(result);
// Output: [ 'apel', 'mangga', 'pisang', 'jeruk' ]
```

> **Penjelasan:**
> 
> -   **Regular Expression `/[,; ]+/`** berarti memisahkan string berdasarkan:
>     -   `,` (koma)
>     -   `;` (titik koma)
>     -   `" "` (spasi)
>     -   `+` berarti jika ada lebih dari satu separator berturut-turut, tetap dihitung satu kali.

----------

## **6. Menggunakan `split()` untuk Mengambil Ekstensi File**

Method ini sering digunakan untuk mengambil **bagian tertentu dari string**, misalnya **ekstensi file**.

### **Contoh 6: Mengambil Ekstensi File**


```javascript
let filename = "gambar.png";
let result = filename.split(".");

console.log(result);
// Output: [ 'gambar', 'png' ]
console.log("Ekstensi file:", result[result.length - 1]);
// Output: Ekstensi file: png
```

> **Penjelasan:**
> 
> -   `"."` digunakan sebagai separator.
> -   `result[result.length - 1]` mengambil bagian terakhir dari array (`"png"`).

----------

## **7. Menggunakan `split()` untuk Membalikkan String**

Dengan menggabungkan `split()`, `reverse()`, dan `join()`, kita bisa membalikkan string.

### **Contoh 7: Membalikkan Urutan Huruf dalam String**


```javascript
let text = "JavaScript";
let result = text.split("").reverse().join("");

console.log(result);
// Output: "tpircSavaJ"
```

> **Penjelasan:**
> 
> -   `split("")` → Memisahkan string menjadi array karakter.
> -   `reverse()` → Membalikkan urutan elemen dalam array.
> -   `join("")` → Menggabungkan kembali array menjadi string.

----------

## **Kesimpulan**

-   **`split(separator, limit)`** digunakan untuk **memecah string menjadi array**.
-   Separator bisa berupa **string biasa** atau **RegExp** untuk pemisahan lebih kompleks.
-   Jika separator **tidak ditemukan**, hasilnya **array dengan satu elemen** berisi string asli.
-   `split("")` bisa digunakan untuk **memisahkan setiap karakter dalam string**.
-   Bisa dikombinasikan dengan **`reverse()`** dan **`join()`** untuk membalikkan string.

Method `split()` sangat berguna untuk **pengolahan string**, seperti parsing data, manipulasi teks, dan pemrosesan input! 🚀
