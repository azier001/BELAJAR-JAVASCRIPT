# event.stopPropagation()

## **Apa itu event.stopPropagation()?**

`event.stopPropagation()` adalah metode dalam JavaScript yang digunakan untuk menghentikan penyebaran (propagasi) event dari elemen target ke elemen induknya dalam DOM.

## **Konsep Dasar**

Secara default, event dalam JavaScript mengikuti model **Event Bubbling** dan **Event Capturing**:

1. **Event Bubbling**: Event naik dari elemen yang diklik ke elemen induknya.
2. **Event Capturing**: Event turun dari elemen induk ke elemen target.

`event.stopPropagation()` menghentikan proses bubbling atau capturing, sehingga event tidak akan menyebar lebih jauh.

## **Contoh Penggunaan**

Berikut contoh penggunaan `event.stopPropagation()` dalam DOM:

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Demo stopPropagation</title>
    <style>
        .parent {
            padding: 20px;
            background-color: lightblue;
        }
        .child {
            padding: 10px;
            background-color: coral;
        }
    </style>
</head>
<body>

    <div class="parent">
        Parent (Klik di sini juga akan menangkap event jika bubbling tidak dihentikan)
        <div class="child">
            Child (Klik aku!)
        </div>
    </div>

    <script>
        document.querySelector('.parent').addEventListener('click', function() {
            alert('Event di Parent');
        });

        document.querySelector('.child').addEventListener('click', function(event) {
            alert('Event di Child');
            event.stopPropagation(); // Mencegah event naik ke parent
        });
    </script>

</body>
</html>
```

### **Penjelasan**

1. Jika mengklik **elemen `child`**, hanya akan muncul alert `'Event di Child'` karena propagasi dihentikan.
2. Jika mengklik **elemen `parent`**, akan muncul alert `'Event di Parent'` karena event tidak dihentikan pada level ini.

## **Kapan Menggunakan event.stopPropagation()?**

`event.stopPropagation()` berguna dalam berbagai situasi, seperti:

1. **Mencegah event handler dari elemen induk ikut terpicu**
   - Misalnya, dalam menu dropdown yang berada dalam elemen lain yang memiliki event click.
2. **Menghentikan propagasi pada event listener global**
   - Jika ada event listener global (misalnya di `document`) yang menangani klik, Anda bisa menggunakan `event.stopPropagation()` untuk mencegahnya menangani klik pada elemen tertentu.
3. **Mengisolasi event dalam komponen UI tertentu**
   - Dalam aplikasi berbasis framework seperti React atau Vue, sering kali kita ingin event hanya terjadi dalam komponen tanpa mempengaruhi elemen di luar komponen tersebut.

## **Perbedaan dengan event.preventDefault()**

`event.stopPropagation()` berbeda dengan `event.preventDefault()`, yaitu:

- `event.stopPropagation()`: Mencegah event menyebar ke elemen induk.
- `event.preventDefault()`: Mencegah perilaku default elemen (misalnya, menghentikan submit form).

## **Kesimpulan**

- `event.stopPropagation()` berguna untuk mencegah event naik ke elemen induk.
- Cocok digunakan jika ingin mengisolasi event pada elemen tertentu.
- Berbeda dengan `event.preventDefault()`, yang lebih fokus pada mencegah aksi bawaan elemen.
- Digunakan dalam kasus di mana event bubbling bisa menyebabkan perilaku yang tidak diinginkan.

