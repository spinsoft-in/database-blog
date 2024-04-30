---
title: DEFAULT 
description: 
date: 2020-01-07
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Default Timestamp 

```sql
CREATE TABLE employees (
  id int primary key auto_increment,
  name varchar(100) not null,
  status varchar(20) DEFAULT 'ACTIVE',
  created_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  modified_date DATETIME DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP  
);
```