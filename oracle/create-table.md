---
title: Create/Drop Table
description:
date: 2020-01-03
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Task 1: Create Table

```sql
    create table employees(id NUMBER, name VARCHAR2(20));
```

###### Task 2: Describe Table

```sql
    desc employees;
```

###### Task 3: Insert Records

```sql
    insert into employees(id,name) values (1,'Naresh');
    insert into employees(id,name) values (2,'Prabhu');
```

###### Task 4: Select Records

```sql
    select * from employees;
```



###### Task 5: Drop table

```sql
    drop table employees;
```

