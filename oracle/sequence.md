---
title: Sequence
description:
date: 2020-01-10
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Prerequisite: Create Table

```sql
    create table employees (
        id NUMBER primary key,
        name VARCHAR2(100) not null
    );
    insert into employees(id,name) values (1,'Naresh');
    insert into employees(id,name) values (2,'Siva');
```

##### Create Sequence ( To Generate employee id automatically )

```sql
     CREATE SEQUENCE employees_id_seq START WITH 1 INCREMENT BY 1;
```

```sql
     insert into employees(id,name) values ( employees_id_seq.nextval, 'Naresh');
     insert into employees(id,name) values (employees_id_seq.nextval,'Siva');
```

##### Sequence Value

- To get next value.

```sql
  select employees_id_seq.nextval from dual;
```

- To get current value.

```sql
  select employees_id_seq.currval from dual;
```

##### Drop sequence

```sql
 drop table employees_id_seq;
```
