---
title: Sorting
description:
date: 2020-01-02
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
    (3, 'Naresh',70000);
```

###### Task 1: Sort the employees by name

```sql
    select * from employees order by name; -- Default - ASC
    select * from employees order by name ASC;
```

###### Task 2: Sort the employees by highest salary and name ascending

```sql
    select * from employees order by salary DESC, name ASC;
```

