---
title: Delete Records
description: 
date: 2020-01-05
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Prerequisite: List Collection Records

```sql
   db.users.find();
```


###### Reference

- https://docs.mongodb.com/manual/crud/


 ###### Task 1.1: Delete a Specific Record ( )

 ```sql
    db.users.remove({email:"nareshkumarh@live.com"});
```

```js
    WriteResult({ "nRemoved" : 1 })
```    

###### Task 1.2: Delete all  Records in a collection

 ```sql
    db.users.remove({});

```

```js
    WriteResult({ "nRemoved" : 2 })
```