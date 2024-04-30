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
    create table departments (id int, name varchar(100));
    insert into departments(id,name) values (101,'HR');
```

```sql
   create table employees(id int,name varchar(20),email varchar(30) ,gender char(1),department_id int, salary int);
   insert into employees (id,name,email,department_id,salary) values 
   (1,'Naresh','n@gmail.com',101,10000);
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
        id int primary key,
        name varchar(30) not null,
        email varchar(40) not null,
        gender char(1),
        department_id int not null,
        salary int,
        unique (email),
        check ( gender in ('M','F')),
        foreign key (department_id) references departments(id),
        check (salary > 0 )
    );
```

