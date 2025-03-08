# Date Object di JavaScript

## Apa itu Date Object?
**Date Object** di JavaScript digunakan untuk bekerja dengan tanggal dan waktu. Objek ini memungkinkan kita untuk mendapatkan, mengatur, dan memanipulasi tanggal dan waktu.

---

## Membuat Date Object

### 1. Tanggal dan Waktu Saat Ini
```javascript
let now = new Date();
console.log(now);
// Output: Sun Mar 09 2025 00:00:00 GMT+0700 (Western Indonesia Time)
```

### 2. Menggunakan String
```javascript
let specificDate = new Date('March 09, 2025 10:20:20');
console.log(specificDate);
// Output: Sun Mar 09 2025 10:20:20 GMT+0700 (Western Indonesia Time)
```

### 3. Menggunakan Parameter (tahun, bulan, hari, jam, menit, detik, milidetik)
```javascript
let customDate = new Date(2025, 2, 9, 10, 20);
console.log(customDate);
// Output: Sun Mar 09 2025 10:20:00 GMT+0700 (Western Indonesia Time)
// Bulan ke-3 (Maret), karena bulan dimulai dari 0
```

---

## Mengambil Informasi Tanggal dan Waktu
```javascript
let today = new Date();
console.log(today.getFullYear()); // Output: 2025
console.log(today.getMonth()); // Output: 2 (karena bulan dimulai dari 0)
console.log(today.getDate()); // Output: 9
console.log(today.getDay()); // Output: 0 (karena hari dimulai dari 0, Ahad)
console.log(today.getHours()); // Output: 1
console.log(today.getMinutes()); // Output: 13
console.log(today.getSeconds()); // Output: 16
console.log(today.getMilliseconds()); // Output: 433
console.log(today.getTime()); // Output: 1741457712148
```

---

## Mengatur Tanggal dan Waktu
```javascript
let date = new Date();

// Mengatur tahun menjadi 2026
date.setFullYear(2026);
console.log(date);
// Output: Mon Mar 09 2026 01:18:12 GMT+0700 (Western Indonesia Time)

// Mengatur bulan menjadi Desember (11, karena bulan dimulai dari 0)
date.setMonth(11);
console.log(date);
// Output: Wed Dec 09 2026 01:19:43 GMT+0700 (Western Indonesia Time)

// Mengatur hari menjadi 25
date.setDate(25);
console.log(date);
// Output: Fri Dec 25 2026 01:21:17 GMT+0700 (Western Indonesia Time)
```

---

## Perhitungan Waktu dengan Date Object
```javascript
let startDate = new Date(2025, 2, 9, 10, 3);
let endDate = new Date(2025, 2, 14, 6);

let diff = endDate - startDate;
console.log(diff);
// Output: 13291020000 (hasil dalam miliseconds)

let diffInDays = diff / (1000 * 3600 * 24);
console.log(diffInDays);
// Output: 4.833333333333333
```

---

**Catatan:**
- Bulan pada `Date` dimulai dari **0** (Januari = 0, Februari = 1, Maret = 2, ...).
- Hari dalam `getDay()` dimulai dari **0** (Minggu = 0, Senin = 1, ..., Sabtu = 6).
- Perhitungan waktu dalam JavaScript menggunakan **milidetik** sejak 1 Januari 1970 (Unix Timestamp).


