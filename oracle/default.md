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
  id NUMBER primary key auto_increment,
  name VARCHAR2(100) not null,
  status VARCHAR2(20) DEFAULT 'ACTIVE',
  created_date TIMESTAMP DEFAULT SYSTIMESTAMP,
  modified_date DATETIME DEFAULT SYSTIMESTAMP
);
```
