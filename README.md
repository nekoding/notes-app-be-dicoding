### About
Silabus [https://www.dicoding.com/academies/261](https://www.dicoding.com/academies/261)

#### Data

Struktur data :  

```js
{
    id: string,
    title: string,
    createdAt: string,
    updatedAt: string,
    tags: array of string,
    body: string,
}
```

Contoh data create :  

```js
{
    id: 'notes-V1StGXR8_Z5jdHi6B-myT',
    title: 'Sejarah JavaScript',
    createdAt: '2020-12-23T23:00:09.686Z',
    updatedAt: '2020-12-23T23:00:09.686Z',
    tags: ['NodeJS', 'JavaScript'],
    body: 'JavaScript pertama kali dikembangkan oleh Brendan Eich dari Netscape di bawah nama Mocha, yang nantinya namanya diganti menjadi LiveScript, dan akhirnya menjadi JavaScript. Navigator sebelumnya telah mendukung Java untuk lebih bisa dimanfaatkan para pemrogram yang non-Java.',
}
```

Contoh data update :

```json
{
    "title":"Judul Catatan Revisi",
    "tags":[
    "Tag 1",
    "Tag 2"
    ],
    "body":"Konten catatan"
}
```


#### Kriteria API

```
POST /notes 201
---
{
    "status": "success",
    "message": "Catatan berhasil ditambahkan",
    "data": {
    "noteId": "V09YExygSUYogwWJ"
    }
}

POST /notes 500
---
{
    "status": "error",
    "message": "Catatan gagal untuk ditambahkan"
}

GET /notes 200
---
{
    "status": "success",
    "data": {
        "notes": [
            {
            "id":"notes-V1StGXR8_Z5jdHi6B-myT",
            "title":"Catatan 1",
            "createdAt":"2020-12-23T23:00:09.686Z",
            "updatedAt":"2020-12-23T23:00:09.686Z",
            "tags":[
                "Tag 1",
                "Tag 2"
            ],
            "body":"Isi dari catatan 1"
            },
            {
            "id":"notes-V1StGXR8_98apmLk3mm1",
            "title":"Catatan 2",
            "createdAt":"2020-12-23T23:00:09.686Z",
            "updatedAt":"2020-12-23T23:00:09.686Z",
            "tags":[
                "Tag 1",
                "Tag 2"
            ],
            "body":"Isi dari catatan 2"
            }
        ]
    }
}

or

{
    "status": "success",
    "data": {
        "notes": []
    }
}

GET /notes/:id 200
---
{
    "status": "success",
    "data": {
    "note": {
        "id":"notes-V1StGXR8_Z5jdHi6B-myT",
        "title":"Catatan 1",
        "createdAt":"2020-12-23T23:00:09.686Z",
        "updatedAt":"2020-12-23T23:00:09.686Z",
        "tags":[
        "Tag 1",
        "Tag 2"
        ],
        "body":"Isi dari catatan 1"
    }
    }
}

GET /notes/:id 404
---
{
    "status": "fail",
    "message": "Catatan tidak ditemukan"
}

PUT /notes/:id 200
---
{
    "status": "success",
    "message": "Catatan berhasil diperbaharui"
}

PUT /notes/:id 404
---
{
    "status": "fail",
    "message": "Gagal memperbarui catatan. Id catatan tidak ditemukan"
}

DELETE /notes/:id 200
---
{
    "status": "success",
    "message": "Catatan berhasil dihapus"
}

DELETE /notes/:id 404
---
{
    "status": "fail",
    "message": "Catatan gagal dihapus. Id catatan tidak ditemukan"
}
```

