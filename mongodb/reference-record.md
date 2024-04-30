---
title: Reference  Record
description: 
date: 2020-01-10
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Prerequisite: Sample Data

```sql
   db.users.insertMany([{name:"Naresh", email:"nareshkumarh@live.com", password:"pass123", role:"ADMIN"},{name:"Suresh", email:"suresh@gmail.com", password:"pass123", role:"USER"},
 {name:"Prabu", email:"prabhu@gmail.com", password:"pass123", role:"USER"}]);
```

```js
db.users.find();
{ "_id" : ObjectId("5fc074d548cb2dbe817558eb"), "name" : "Naresh", "email" : "nareshkumarh@live.com", "password" : "newpassword", "role" : "ADMIN", "active" : 1 }
{ "_id" : ObjectId("5fc074d548cb2dbe817558ec"), "name" : "Suresh", "email" : "suresh@gmail.com", "password" : "pass123", "role" : "USER", "active" : 1 }
{ "_id" : ObjectId("5fc074d548cb2dbe817558ed"), "name" : "Prabu", "email" : "prabhu@gmail.com", "password" : "pass123", "role" : "USER", "active" : 1 }
```

###### Task 1: Create Accounts ( add userId value from users table)

```sql
db.accounts.insert({balance:0,accountType:"Savings",userId: 
{ "$ref": "users", "$id": ObjectId("5fc074d548cb2dbe817558ec"), "$db":"bankapp_db"}});
```

```js
WriteResult({ "nInserted" : 1 })
```

###### Task 2:  List All Accounts

```sql
    db.accounts.find();
```

```js
{ "_id" : ObjectId("5fc09c938034d96ca06df65e"), "balance" : 0, "accountType" : "Savings", "userId" : DBRef("users", ObjectId("5fc074d548cb2dbe817558ec"), "bankapp_db") }
```

