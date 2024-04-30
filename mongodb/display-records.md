---
title: Find Records
description: 
date: 2020-01-04
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

###### Task 1.1: Find All Records

```sql
    db.users.find();
```

```js
{ "_id" : ObjectId("5fc072c348cb2dbe817558e5"), "name" : "Naresh", "email" : "nareshkumarh@live.com", "password" : "pass123", "role" : "ADMIN" }
{ "_id" : ObjectId("5fc072c348cb2dbe817558e6"), "name" : "Suresh", "email" : "suresh@gmail.com", "password" : "pass123", "role" : "USER" }
{ "_id" : ObjectId("5fc072c348cb2dbe817558e7"), "name" : "Prabu", "email" : "prabhu@gmail.com", "password" : "pass123", "role" : "USER" }
```

###### Task 1.2: Find the first matching record

```sql
    db.users.findOne()
```

```js
{
        "_id" : ObjectId("5fc072c348cb2dbe817558e5"),
        "name" : "Naresh",
        "email" : "nareshkumarh@live.com",
        "password" : "pass123",
        "role" : "ADMIN"
}
```

###### Task 1.3: Find records for the given filter

```sql
 db.users.find({role:"ADMIN"})
 ```

 ```js
{ "_id" : ObjectId("5fc072c348cb2dbe817558e6"), "name" : "Suresh", "email" : "suresh@gmail.com", "password" : "pass123", "role" : "USER" }
{ "_id" : ObjectId("5fc072c348cb2dbe817558e7"), "name" : "Prabu", "email" : "prabhu@gmail.com", "password" : "pass123", "role" : "USER" }
 ```


###### Task 1.4: Select Specific Column - Display name,email

- 0 refers - hide the column
- 1 refers - select the column
- 
```sql
db.users.find({},{name:1,email:1});
```

```js
{ "_id" : ObjectId("5fc074d548cb2dbe817558eb"), "name" : "Naresh", "email" : "nareshkumarh@live.com" }
{ "_id" : ObjectId("5fc074d548cb2dbe817558ec"), "name" : "Suresh", "email" : "suresh@gmail.com" }
{ "_id" : ObjectId("5fc074d548cb2dbe817558ed"), "name" : "Prabu", "email" : "prabhu@gmail.com" }
```


###### Task 1.5: Display all records excluding the specified Column (Exclude password and id)

- 0 refers - hide the column
- 1 refers - select the column
```sql
db.users.find({},{password:0,_id:0});
```

```js
{ "name" : "Naresh", "email" : "nareshkumarh@live.com", "role" : "ADMIN" }
{ "name" : "Suresh", "email" : "suresh@gmail.com", "role" : "USER" }
{ "name" : "Prabu", "email" : "prabhu@gmail.com", "role" : "USER" }
```


###### Task 1.6: Write query for Login Scenario  (Combining multiple conditions)

- find - returns Array
  
```sql
    db.users.find({email:"nareshkumarh@live.com", password:"pass123"})
```

- findOne - returns 1st matching record

```sql
    db.users.findOne({email:"nareshkumarh@live.com", password:"pass123"})
```


##### Task 1.7: Limit the records  ( Display only 2 records)

```sql
    db.users.find().limit(2);
```

##### Task 1.8: Eq

```sql
 db.users.find({active:{"$eq":1}});
 ```
```js
{ "_id" : ObjectId("5fc074d548cb2dbe817558ec"), "name" : "Suresh", "email" : "suresh@gmail.com", "password" : "pass123", "role" : "USER", "active" : 1 }
{ "_id" : ObjectId("5fc074d548cb2dbe817558ed"), "name" : "Prabu", "email" : "prabhu@gmail.com", "password" : "pass123", "role" : "USER", "active" : 1 }
{ "_id" : ObjectId("5fc074d548cb2dbe817558eb"), "name" : "Naresh", "email" : "nareshkumarh@live.com", "password" : "newpassword", "role" : "ADMIN", "active" : 1 }