# Tantangan DOM Manipulation di JavaScript

## Tantangan
Buat sebuah halaman HTML sederhana yang memiliki:
1. Sebuah input field dengan id "inputText".
2. Sebuah tombol dengan id "addButton" yang ketika diklik akan menambahkan nilai dari input field sebagai item baru dalam sebuah daftar (ul).
3. Setiap item dalam daftar (ul) harus memiliki tombol "Hapus" di sebelahnya yang ketika diklik akan menghapus item tersebut dari daftar.

### Petunjuk:
- Gunakan `document.createElement()` untuk membuat elemen baru.
- Gunakan `element.appendChild()` untuk menambahkan elemen ke dalam DOM.
- Gunakan event listener untuk menangani event klik pada tombol.

# Solusi Tantangan DOM Manipulation di JavaScript

```html
<!DOCTYPE html>
<html lang="id">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>DOM Challenge</title>
  </head>
  <body>
    <input type="text" id="text" placeholder="Masukkan item" />

    <button id="btn-tambah">Tambahkan</button>
    <ul id="list-item"></ul>

    <script>
      const inputText = document.getElementById('text');
      const addBtn = document.getElementById('btn-tambah');
      const listItem = document.getElementById('list-item');

      addBtn.addEventListener('click', () => {
        if (inputText.value === '') {
          alert('Masukkan item dulu');
          return;
        }

        const newLi = document.createElement('li');
        newLi.textContent = inputText.value;

        const elBtnHapus = document.createElement('button');
        elBtnHapus.textContent = 'Hapus';

        elBtnHapus.addEventListener('click', () => {
          newLi.remove();
        });

        newLi.append(elBtnHapus);
        listItem.append(newLi);

        inputText.value = '';
      });
    </script>
  </body>
</html>
```

## Penjelasan:


## Kode
```javascript
const inputText = document.getElementById('text');
const addBtn = document.getElementById('btn-tambah');
const listItem = document.getElementById('list-item');

addBtn.addEventListener('click', () => {
  if (inputText.value === '') {
    alert('Masukkan item dulu');
    return;
  }

  const newLi = document.createElement('li');
  newLi.textContent = inputText.value;

  const elBtnHapus = document.createElement('button');
  elBtnHapus.textContent = 'Hapus';

  elBtnHapus.addEventListener('click', () => {
    newLi.remove();
  });

  newLi.append(elBtnHapus);
  listItem.append(newLi);

  inputText.value = '';
});
```

## Penjelasan
1. **Mengambil elemen HTML**  
   - `inputText`: Elemen input teks.  
   - `addBtn`: Tombol untuk menambahkan item.  
   - `listItem`: Elemen `<ul>` atau `<ol>` tempat item ditambahkan.  

2. **Menambahkan Event Listener ke tombol "Tambah"**  
   - Jika input kosong, akan muncul peringatan (`alert`).  
   - Membuat elemen `<li>` baru dengan teks dari input.  
   - Membuat tombol "Hapus" yang akan menghapus item saat diklik.  
   - Menambahkan `<li>` baru ke dalam daftar.  
   - Mengosongkan input setelah item ditambahkan.  

## Cara Menggunakan
1. Masukkan teks ke dalam input.
2. Klik tombol "Tambah".
3. Item akan muncul di daftar.
4. Klik tombol "Hapus" untuk menghapus item dari daftar.

