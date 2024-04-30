---
title: Alter Table
description:
date: 2020-01-04
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Prerequisite: Create Table

```sql
   create table employees(id int,name varchar(20));
   insert into employees(id,name) values (1,'Naresh');
   select * from employees;
```

###### Task 1: Alter Table - add column

```sql
    alter table employees add  dob date;
    alter table employees add  created_date timestamp;
```

```sql
    desc employees;
```

###### Task 2: Alter Table - Drop column

```sql
    alter table employees drop column created_date;
```


```sql
    desc employees;
```

###### Task 3: Alter table - Modify column

```sql
    alter table employees modify column name varchar(100);
```


```sql
    desc employees;
```

