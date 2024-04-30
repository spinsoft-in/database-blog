---
title: Constraints
description:
date: 2020-01-05
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Prerequisite: Create Table

```sql
    create table departments (id NUMBER, name VARCHAR2(100));
    insert into departments(id,name) values (101,'HR');
```

```sql
   create table employees(id NUMBER,name VARCHAR2(20),email VARCHAR2(30) ,gender CHAR(1),department_id NUMBER, salary NUMBER);
```

```sql
   insert into employees (id,name,email,department_id,salary) values
   (1,'Naresh','n@gmail.com',101,10000);
```

```sql
   select * from employees;

```

###### Constraints

- NOT NULL
- UNIQUE
- PRIMARY KEY ( UNIQUE + NOT NULL )
- CHECK
- FOREIGN KEY

###### Task 1: Employee Table Rules

- id - is mandatory and must be unique ( Primary Key)
- name - is mandatory  ( Not Null )
- email - is not null  and unique ( Not Null + Unique )
- gender - optional and valid values are "M" for Male and "F" for Female
- department_id - must be a valid department
- salary - is optional, must be greater than zero.


```sql
    create table employees (
        id NUMBER primary key,
        name VARCHAR2(30) not null,
        email VARCHAR2(40) not null,
        gender CHAR(1),
        department_id NUMBER not null,
        salary NUMBER,
        unique (email),
        check ( gender in ('M','F')),
        foreign key (department_id) references departments(id),
        check (salary > 0 )
    );
```

