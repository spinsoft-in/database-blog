---
title: Sort Records
description:
date: 2020-01-10
duration: ~10 mins
tags:
layout: layouts/post.njk
---


###### Task 1.1: Sort by Price Descending ( Postman)

```
POST - {{DB_URL}}/products/_find
```

- Request Data:
```js
{
    "selector": {
        "price": { "$gte": 20000}
    },
    "sort": [{"price": "desc"}]
}
```

- Response
```js
{
    "docs": [
        {
            "_id": "50285e674fecd694439ead3fd3a82156",
            "_rev": "10-e959aeebe4da568e1a1317b2f923e4f4",
            "name": "Moto 8",
            "brand_name": "MOTO",
            "price": 50000
        },
        {
            "_id": "6f7f1662775d73830a5ebba485773206",
            "_rev": "1-646fda0a70d12a39b8b1378737e863a0",
            "name": "Moto 6",
            "brand_name": "MOTO",
            "price": 40000
        },
        {
            "_id": "90fdb385aabe65f5620452a3269d7eed",
            "_rev": "1-7dff148a224c5848b048fbfd8a123a7c",
            "name": "Moto 5",
            "brand_name": "MOTO",
            "price": 20000
        }
    ],
    "bookmark": "g2wAAAACaAJkAA5zdGFydGtleV9kb2NpZG0AAAAgOTBmZGIzODVhYWJlNjVmNTYyMDQ1MmEzMjY5ZDdlZWRoAmQACHN0YXJ0a2V5bAAAAAFiAABOIGpq"
}
```
