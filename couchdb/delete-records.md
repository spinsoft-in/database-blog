---
title: Delete Records
description:
date: 2020-01-05
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Prerequisite: Get Record for the given id

```
GET - {{DB_URL}}/users/0e91afcec3d1925619930f1ba250f355
```

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

##### Task 1.1: Delete record for the given id

URL Syntax :

```
 DELETE - {{DB_URL}}/users/{{_id}}?rev={{_rev}}
 ```

```
- DELETE - {{DB_URL}}/users/0e91afcec3d1925619930f1ba250f355?rev=1-3e2d033bf65f0d7285ca943ae0e17925
```
- Note: we need to pass latest revision id to update the record.

- Response:

```js
{
    "ok": true,
    "id": "0e91afcec3d1925619930f1ba250f355",
    "rev": "2-65f187daa74fdf95b337a0e8ba48a159"
}
```

