---
title: Limit
description:
date: 2020-01-14
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Prerequisite

```sql
    create table employees (id int primary key,name varchar(100) not null,salary int not null);
    insert into employees (id,name,salary) values
    (1, 'Ramesh',10000),
    (2, 'Siva',8000),
    (3, 'Naresh',70000),
    (4, 'Prabhu',55000),
    (5, 'Dinesh',35000);
```


##### Task 1: Find the top 3 employees who gets highest salary

```sql
    select * from employees order by salary desc limit 3;
```
