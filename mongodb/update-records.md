---
title: Update Records
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

```js
{ "_id" : ObjectId("5fc072c348cb2dbe817558e5"), "name" : "Naresh", "email" : "nareshkumarh@live.com", "password" : "pass123", "role" : "ADMIN" }
{ "_id" : ObjectId("5fc072c348cb2dbe817558e6"), "name" : "Suresh", "email" : "suresh@gmail.com", "password" : "pass123", "role" : "USER" }
{ "_id" : ObjectId("5fc072c348cb2dbe817558e7"), "name" : "Prabu", "email" : "prabhu@gmail.com", "password" : "pass123", "role" : "USER" }
```


###### Reference

- https://docs.mongodb.com/manual/crud/


 ###### Task 1.1: Update Password for the given email

 ```sql
    db.users.updateOne({email:"nareshkumarh@live.com"},{$set:{password:"newpassword"}});
```

```js
{ "acknowledged" : true, "matchedCount" : 1, "modifiedCount" : 1 }
```

###### Task 1.2: Update many records ( update all users with active =1 )

 ```sql
    db.users.updateMany({},{$set:{active:1}});
```

```js
{ "acknowledged" : true, "matchedCount" : 3, "modifiedCount" : 3 }
```
