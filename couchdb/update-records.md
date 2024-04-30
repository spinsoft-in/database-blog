---
title: Update Records
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

##### Task 1.1: Update Password for the given id

- Update password from "pass123" to "pass1234"

- URL Syntax :
```
PUT - {{DB_URL}}/users/{{_id}}?rev={{_rev}}
```
```
PUT - {{DB_URL}}/users/0e91afcec3d1925619930f1ba250f355?rev=1-3e2d033bf65f0d7285ca943ae0e17925
```
- Note: we need to pass latest revision id to update the record.

- Request Data:

```js
{
            "name": "naresh",
            "email": "n@gmail.com",
            "password":"pass1234",
            "role": "USER"
}
```

- Response:

```js
{
    "ok": true,
    "id": "0e91afcec3d1925619930f1ba250f355",
    "rev": "2-032c74b94743b6e96fb987aa0cf19322"
}
```

- Notes:
  - Updating an existing document is same as updating the entire document.
