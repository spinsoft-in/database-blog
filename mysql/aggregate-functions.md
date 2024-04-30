---
title: Aggregate Functions
description: 
date: 2020-01-20
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Prerequisite: Create Table

```sql
   create table employees(id int,name varchar(20),department varchar(100),salary int);
   insert into employees (id,name,department,salary) values 
   (1,'Naresh','HR',10000),
   (2,'Siva','HR',8000),
   (3,'Rajesh','DEV',70000),
   (4,'Arjun','DEV',40000);
   select * from employees;
``` 

###### Task 1: Find Total no of employees

```sql
    select count(*) from employees;
```

###### Task 2: Find Min,Max,Sum,Avg salary

```sql
    select min(salary),max(salary),sum(salary),avg(salary) from employees;
```


###### Task 3: Find Min,Max,Sum,Avg salary for each department

```sql
     select department, min(salary),max(salary),sum(salary),avg(salary) from employees group by department;
```

###### Task 3: Find Min,Max,Sum,Avg salary for each department who is having avg salary greater than Rs.50,000

```sql
     select department, min(salary),max(salary),sum(salary),avg(salary) from employees group by department having avg(salary) > 50000 ;
```