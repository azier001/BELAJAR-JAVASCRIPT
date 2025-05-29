# Menggunakan Axios untuk Mengambil Data dari API

Axios adalah library JavaScript berbasis promise yang memudahkan proses HTTP request ke API. Dibandingkan dengan `fetch`, Axios menyediakan fitur-fitur tambahan seperti:

- Interceptor request dan response
- Transformasi otomatis JSON
- Timeout request
- Cancel token

## Instalasi Axios

### Menggunakan NPM
```bash
npm install axios
```

### Menggunakan CDN
```html
<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
```

## Contoh Penggunaan Axios

### 1. Menggunakan `.then()` dan `.catch()`

```javascript
axios
  .get('https://jsonplaceholder.typicode.com/posts/1')
  .then((response) => {
    console.log('Data fetched with Axios:', response.data);
  })
  .catch((error) => {
    console.error('Axios error:', error);
  });
```

#### Output:
```
Data fetched with Axios: {
  userId: 1,
  id: 1,
  title: "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  body: "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
}
```

### 2. Menggunakan `async/await`

```javascript
async function getData() {
  try {
    const response = await axios.get(
      'https://jsonplaceholder.typicode.com/posts/1'
    );
    console.log(response.data);
  } catch (error) {
    console.error('Error:', error.message);
  }
}

getData();
```

#### Output:
```
{
  userId: 1,
  id: 1,
  title: "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  body: "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
}
```

## Struktur Dasar Kode Axios

```javascript
axios({
  method: 'get',
  url: 'https://jsonplaceholder.typicode.com/posts/1',
  headers: {
    'Content-Type': 'application/json'
  }
})
.then(response => console.log(response.data))
.catch(error => console.error(error));
```

## Contoh Request POST

```javascript
async function postData() {
  try {
    const payload = {
      title: 'foo',
      body: 'bar',
      userId: 1
    };

    const response = await axios.post(
      'https://jsonplaceholder.typicode.com/posts',
      payload
    );

    console.log('Post response:', response.data);
  } catch (error) {
    console.error('Post error:', error.message);
  }
}

postData();
```

#### Output:
```
Post response: {
  title: "foo",
  body: "bar",
  userId: 1,
  id: 101
}
```

