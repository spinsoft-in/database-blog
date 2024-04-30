---
title: Skip and Limit Records
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


###### Reference

- https://docs.mongodb.com/manual/crud/

###### Task 1.1: Find All Records

```sql
    db.users.find();
```

###### Task 1.2: Limit the records  ( Display only 2 records)

```sql
    db.users.find().limit(2);
```

###### Task 1.3: Skip the records  ( Skip the 1st record,Display only 2 records)

```sql
    db.users.find().skip(1).limit(2);
```

