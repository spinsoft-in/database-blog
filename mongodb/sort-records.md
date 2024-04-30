---
title: Sort Records
description: 
date: 2020-01-09
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Prerequisite: Sample Data

```sql
   db.users.insertMany([{name:"Naresh", email:"nareshkumarh@live.com", password:"pass123", role:"ADMIN"},{name:"Suresh", email:"suresh@gmail.com", password:"pass123", role:"USER"},
 {name:"Prabu", email:"prabhu@gmail.com", password:"pass123", role:"USER"}]);
```


###### Reference

- https://docs.mongodb.com/manual/crud/

###### Task 1.1: Sort Records  ( name ascending ) 

```sql
    db.users.find().sort({name:1});
```

```js
{ "_id" : ObjectId("5fc074d548cb2dbe817558eb"), "name" : "Naresh", "email" : "nareshkumarh@live.com", "password" : "newpassword", "role" : "ADMIN", "active" : 1 }
{ "_id" : ObjectId("5fc074d548cb2dbe817558ed"), "name" : "Prabu", "email" : "prabhu@gmail.com", "password" : "pass123", "role" : "USER", "active" : 1 }
{ "_id" : ObjectId("5fc074d548cb2dbe817558ec"), "name" : "Suresh", "email" : "suresh@gmail.com", "password" : "pass123", "role" : "USER", "active" : 1 }
```

###### Task 2: Sort Records  ( name descending ) 

```sql
    db.users.find().sort({name:-1});
```

```js
{ "_id" : ObjectId("5fc074d548cb2dbe817558ec"), "name" : "Suresh", "email" : "suresh@gmail.com", "password" : "pass123", "role" : "USER", "active" : 1 }
{ "_id" : ObjectId("5fc074d548cb2dbe817558ed"), "name" : "Prabu", "email" : "prabhu@gmail.com", "password" : "pass123", "role" : "USER", "active" : 1 }
{ "_id" : ObjectId("5fc074d548cb2dbe817558eb"), "name" : "Naresh", "email" : "nareshkumarh@live.com", "password" : "newpassword", "role" : "ADMIN", "active" : 1 }
```

