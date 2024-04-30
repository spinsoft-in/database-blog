---
title: Create Database
description: 
date: 2020-01-01
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Prerequisite: Mongo Atlas URL

- Create Mongo DB Cluster 

###### Connect Database in Mongo Atlas

-   Create Database 'bankapp_db'

###### Connect Database using MongoShell

```sql
    mongo "mongodb+srv://cluster0.y9bq7.mongodb.net/bankapp_db" --username naresh
    Enter Password: 
```

###### List Collections(List Tables)

```sql
    show collections;
```
