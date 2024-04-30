---
title: Create Database
description:
date: 2020-01-02
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Prerequisite: Launch Cloudant Dashboard

##### 1. Create Database

- Click "Create Database"
  - Enter Database name: users
  - Select : Non Partitioned


##### 2. List all Databases ( Postman)

```
GET Request - {{DB_URL}}/_all_dbs
```

```js
[
    "companies",
    "users",
    "wallet"
]
```
