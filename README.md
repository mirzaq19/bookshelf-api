# Bookshelf API

API to manage book

Book object:

```
{
    "id": "Qbax5Oy7L8WKf74l",
    "name": "Buku A",
    "year": 2010,
    "author": "John Doe",
    "summary": "Lorem ipsum dolor sit amet",
    "publisher": "Dicoding Indonesia",
    "pageCount": 100,
    "readPage": 25,
    "finished": false,
    "reading": false,
    "insertedAt": "2021-03-04T09:11:44.598Z",
    "updatedAt": "2021-03-04T09:11:44.598Z"
}
```

## 1. Add Book

method: `POST`
URL: `/books`

- Success

```
{
    "status": "success",
    "message": "Buku berhasil ditambahkan",
    "data": {
        "bookId": "1L7ZtDUFeGs7VlEt"
    }
}
```

- Name is empty

```
{
    "status": "fail",
    "message": "Gagal menambahkan buku. Mohon isi nama buku"
}
```

- readPage > pageCount

```
{
    "status": "fail",
    "message": "Gagal menambahkan buku. readPage tidak boleh lebih besar dari pageCount"
}
```

- Server Error

```
{
    "status": "error",
    "message": "Buku gagal ditambahkan"
}
```

## 2. Get All Books

method: `GET`
URL: `/books`

- Success with data

```
{
    "status": "success",
    "data": {
        "books": [
            {
                "id": "Qbax5Oy7L8WKf74l",
                "name": "Buku A",
                "publisher": "Dicoding Indonesia"
            },
            {
                "id": "1L7ZtDUFeGs7VlEt",
                "name": "Buku B",
                "publisher": "Dicoding Indonesia"
            },
            {
                "id": "K8DZbfI-t3LrY7lD",
                "name": "Buku C",
                "publisher": "Dicoding Indonesia"
            }
        ]
    }
}
```

- When empty

```
{
    "status": "success",
    "data": {
        "books": []
    }
}
```

## 3. Get Specified Book

method: `GET`
URL: `/books/{bookId}`

- Success with data

```
{
    "status": "success",
    "data": {
        "book": {
            "id": "aWZBUW3JN_VBE-9I",
            "name": "Buku A Revisi",
            "year": 2011,
            "author": "Jane Doe",
            "summary": "Lorem Dolor sit Amet",
            "publisher": "Dicoding",
            "pageCount": 200,
            "readPage": 26,
            "finished": false,
            "reading": false,
            "insertedAt": "2021-03-05T06:14:28.930Z",
            "updatedAt": "2021-03-05T06:14:30.718Z"
        }
    }
}
```

- Book not found

```
{
    "status": "fail",
    "message": "Buku tidak ditemukan"
}
```

## 4. Update Book

method: `PUT`
URL: `/books/{bookId}`

- Success with data

```
{
    "status": "success",
    "message": "Buku berhasil diperbarui"
}
```

- Name is empty

```
{
    "status": "fail",
    "message": "Gagal memperbarui buku. Mohon isi nama buku"
}
```

- readPage > pageCount

```
{
    "status": "fail",
    "message": "Gagal memperbarui buku. readPage tidak boleh lebih besar dari pageCount"
}
```

- ID not found

```
{
    "status": "fail",
    "message": "Gagal memperbarui buku. Id tidak ditemukan"
}
```

- Server Error

```
{
    "status": "error",
    "message": "Buku gagal diperbarui"
}
```

## 5. Delete Book

method: `DELETE`
URL: `/books/{bookId}`

- Success with data

```
{
    "status": "success",
    "message": "Buku berhasil dihapus"
}
```

- ID not found

```
{
    "status": "fail",
    "message": "Buku gagal dihapus. Id tidak ditemukan"
}
```
