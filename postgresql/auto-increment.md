---
title: Auto Increment
description:
date: 2020-01-10
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Prerequisite: Create Table

```sql
    create table employees (
        id int primary key,
        name varchar(100) not null
    );
    insert into employees(id,name) values (1,'Naresh');
    insert into employees(id,name) values (2,'Siva');
```

##### Generate employee id automatically

```sql
     drop table employees;
     create table employees (
         id int primary key serial,
         name varchar(100) not null
    );
```

```sql
     insert into employees(name) values ('Naresh');
     insert into employees(name) values ('Siva');
```
