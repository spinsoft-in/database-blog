---
title: Find Records
description:
date: 2020-01-04
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Task 1.1: Find All Records ( Postman)

```
GET - {{URL}}/users/_all_docs?include_docs=true
```

- Response:
```js
{
    "total_rows": 2,
    "offset": 0,
    "rows": [
        {
            "id": "0e91afcec3d1925619930f1ba250f355",
            "key": "0e91afcec3d1925619930f1ba250f355",
            "value": {
                "rev": "1-3e2d033bf65f0d7285ca943ae0e17925"
            },
            "doc": {
                "_id": "0e91afcec3d1925619930f1ba250f355",
                "_rev": "1-3e2d033bf65f0d7285ca943ae0e17925",
                "name": "suresh",
                "email": "s@gmail.com",
                "password": "pass123",
                "role": "ADMIN"
            }
        },
        {
            "id": "51db2020c9eaf1fb428bb1ed2e8fff41",
            "key": "51db2020c9eaf1fb428bb1ed2e8fff41",
            "value": {
                "rev": "4-0de78c3336410989b118fd9570092b05"
            },
            "doc": {
                "_id": "51db2020c9eaf1fb428bb1ed2e8fff41",
                "_rev": "4-0de78c3336410989b118fd9570092b05",
                "name": "naresh",
                "email": "naresh@gmail.com",
                "password": "pass123",
                "role": "USER"
            }
        }
    ]
}

```

###### Task 1.2: Find records for the given filter

```
POST - {{DB_URL}}/users/_find
```

- Request Data:

```js
{
    "selector": {
        "email": "naresh@gmail.com",
        "password":"pass123"
    }
}
```

- Response
```js
{
    "docs": [
        {
            "_id": "51db2020c9eaf1fb428bb1ed2e8fff41",
            "_rev": "4-0de78c3336410989b118fd9570092b05",
            "name": "naresh",
            "email": "naresh@gmail.com",
            "password": "pass123",
            "role": "USER"
        }
    ],
    "bookmark": "g1AAAABweJzLYWBgYMpgSmHgKy5JLCrJTq2MT8lPzkzJBYormBqmJBkZGBkkW6YmphmmJZkYWSQlGaamGKVapKWlmRiC9HHA9BGlIwsA1wcf2w",
    "warning": "No matching index found, create an index to optimize query time."
}
```

###### Task 1.3: Select Specific Column - id,_rev,name,email,role

```
POST - {{DB_URL}}/users/_find
```

- Request Data:

```js
{
    "selector": {
        "email": "naresh@gmail.com",
        "password":"pass123"
    },
    "fields": ["_id", "_rev", "name", "email", "role"]
}
```

- Response
```js
{
    "docs": [
        {
            "_id": "51db2020c9eaf1fb428bb1ed2e8fff41",
            "_rev": "4-0de78c3336410989b118fd9570092b05",
            "name": "naresh",
            "email": "naresh@gmail.com",
            "role": "USER"
        }
    ],
    "bookmark": "g1AAAABweJzLYWBgYMpgSmHgKy5JLCrJTq2MT8lPzkzJBYormBqmJBkZGBkkW6YmphmmJZkYWSQlGaamGKVapKWlmRiC9HHA9BGlIwsA1wcf2w",
    "warning": "No matching index found, create an index to optimize query time."
}
```


##### Find by Id

```
GET {{DB_URL}}/users/0e91afcec3d1925619930f1ba250f355
```

- Response
```js
{
    "_id": "0e91afcec3d1925619930f1ba250f355",
    "_rev": "1-3e2d033bf65f0d7285ca943ae0e17925",
    "name": "naresh",
    "email": "n@gmail.com",
    "password": "pass123",
    "role": "ADMIN"
}
```

##### Search by Product Price and Brand Name

```
POST - {{DB_URL}}/products/_find
```

- Request

```js
{
    "selector": {
        "price": { "$gt": 20000},
        "brand_name": { "$eq": "MOTO" }
    }
}
```

- Response

```js
{
    "docs": [
        {
            "_id": "90fdb385aabe65f5620452a3269d7eed",
            "_rev": "1-7dff148a224c5848b048fbfd8a123a7c",
            "name": "Moto 5",
            "brand_name": "MOTO",
            "price": 20000
        },
        {
            "_id": "6f7f1662775d73830a5ebba485773206",
            "_rev": "1-646fda0a70d12a39b8b1378737e863a0",
            "name": "Moto 6",
            "brand_name": "MOTO",
            "price": 40000
        },
        {
            "_id": "50285e674fecd694439ead3fd3a82156",
            "_rev": "10-e959aeebe4da568e1a1317b2f923e4f4",
            "name": "Moto 8",
            "brand_name": "MOTO",
            "price": 50000
        }
    ],
    "bookmark": "g2wAAAACaAJkAA5zdGFydGtleV9kb2NpZG0AAAAgNTAyODVlNjc0ZmVjZDY5NDQzOWVhZDNmZDNhODIxNTZoAmQACHN0YXJ0a2V5bAAAAAFiAADDUGpq"
}
```
