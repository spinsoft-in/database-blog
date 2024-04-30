---
title: Create Collection
description: 
date: 2020-01-02
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Prerequisite: Connect to Database 

```sql
    mongo "mongodb+srv://cluster0.y9bq7.mongodb.net/bankapp_db" --username naresh
    Enter Password: 
```


###### Reference

- https://docs.mongodb.com/manual/crud/

###### List Collections(List Tables)

```sql
    show collections;
```

###### Task: Insert a Document in Users Table

```json
    {name:"Naresh", email:"nareshkumarh@live.com", password:"pass123", role:"ADMIN"}
```

###### Task 1.1: Create Users Table and insert single data

```sql
 db.users.insertOne({name:"Naresh", email:"nareshkumarh@live.com", password:"pass123", role:"ADMIN"});
 ```

- Output
  

```js
    {
        "acknowledged" : true,
        "insertedId" : ObjectId("5fc06ede48cb2dbe817558dd")
    }
```

- Note: MongoDB generates unique Id - ObjectId

- Check the table
``` js
    db.user.find();
```
- Output
```js
{ "_id" : ObjectId("5fc0702948cb2dbe817558e1"), 
"name" : "Naresh", "email" : "nareshkumarh@live.com",
 "password" : "pass123", "role" : "ADMIN" }
```


 ###### Task 1.2: Insert Many Records to  Users Table

```sql
 db.users.insertMany([{name:"Suresh", email:"suresh@gmail.com", password:"pass123", role:"USER"},
 {name:"Prabu", email:"prabhu@gmail.com", password:"pass123", role:"USER"}]);
 ```

- Output:
```js
{
        "acknowledged" : true,
        "insertedIds" : [
                ObjectId("5fc06fb348cb2dbe817558df"),
                ObjectId("5fc06fb348cb2dbe817558e0")
        ]
}
```
