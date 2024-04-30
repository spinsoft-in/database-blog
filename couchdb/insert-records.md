---
title: Create Document Records
description:
date: 2020-01-03
duration: ~10 mins
tags:
layout: layouts/post.njk
---



###### Task 1.1: Create Document in "users" collection

- Click "Create Document"

```js
{
  "_id": "69868fc1d00e7b679b676392368afee5",

}
```

- Add User Details
```js
 {
   "_id": "69868fc1d00e7b679b676392368afee5",
   "name":"Naresh",
   "email":"n@live.com",
   "password":"pass123",
   "role":"ADMIN"
}
 ```

- After entering details, click "Create Document".

- View the inserted data, it will add an extra field revision id "_rev".
- Note: Revision id is required to update the document.


```js
    {
  "_id": "69868fc1d00e7b679b676392368afee5",
  "_rev": "1-cb3e705a9310dd99fa9d21b14efa46cd",
  "name": "siva",
  "email": "s@gmail.com",
  "password": "pass123",
  "role": "USER"
}
```



##### Task 1.2: Insert Document via REST API

```
- POST -{{DB_URL}}/users
```

- Request Data
```js
{
    "name":"Ram",
    "email": "ram@gmail.com",
    "password":"pass123",
    "role":"USER"
}
```

- Response

```js
  {
    "ok": true,
    "id": "f784bc0b0750fdc06a32bce6871e95a6",
    "rev": "1-50e9d7326b482741ea43bf6593aef3be"
  }
```
