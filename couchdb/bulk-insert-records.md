---
title: Insert Bulk Documents
description:
date: 2020-01-11
duration: ~10 mins
tags:
layout: layouts/post.njk
---


##### Task 1.1: Insert multiple Documents via REST API

```
- POST -{{DB_URL}}/users/_bulk_docs
```

- Request Data
```js
{
    "docs": [
        {
            "name": "Ram",
            "email": "ram@gmail.com",
            "password": "pass123",
            "role": "USER"
        },
        {
            "name": "Naresh",
            "email": "naresh@gmail.com",
            "password": "pass123",
            "role": "USER"
        }
    ]
}
```

- Response

```js
  [
    {
        "ok": true,
        "id": "95b499c8443c7f6823929ff3e1e46857",
        "rev": "1-50e9d7326b482741ea43bf6593aef3be"
    },
    {
        "ok": true,
        "id": "95b499c8443c7f6823929ff3e1e47621",
        "rev": "1-5f2f852da6a158b5ee8c73d445eaa359"
    }
 ]
```
