---
title: Data Manipulation Language(DML)
description:
date: 2020-01-04
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Prerequisite: Create Table

```sql
   create table employees(id int,name varchar(20),city varchar(100));
   select * from employees;
```

###### Task 1.1: Insert Records

```sql
    insert into employees (id,name) values (1,'Naresh');
```

```sql
    insert into employees (id,name ) values (2,'Prabhu'),(3,'Siva');
```

###### Task 1.2: Display Records

```sql
    select * from employees;
```

###### Task 2.1: Update single column for all Rows

```sql
    update employees set city='Chennai';
```

###### Task 2.2: Update multiple column for the given employee id

```sql
    update employees set name='Naresh Kumar' , city='Chennai' where id =1 ;
```

###### Task 3: Delete a specific record

```sql
    delete from employees where id = 1;
```

###### Task 4: Delete all rows

```sql
    delete from employees;
```


