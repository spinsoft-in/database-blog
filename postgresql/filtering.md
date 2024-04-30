---
title: Filtering - 1
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

##### Task 1: Search Employee with name 'Siva'

```sql
    select * from employees where name='Siva';
```

##### Task 2: Display Employee who gets salary greater than 7500

```sql
    select * from employees where salary > 7500;
```
Note: Comparison Operators -  >,>=,<,<=, !=

##### Task 3: Display Employee who gets salary between 5000 and 15000

```sql
    select * from employees where salary > 5000 and salary < 15000;    
```

```sql
    select * from employees where salary between  5000 AND 15000;    
```

- Logical Operators - AND,OR,NOT


