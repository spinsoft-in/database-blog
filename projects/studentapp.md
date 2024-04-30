---
title: Student Management App
description:
date: 2020-01-01
duration: ~60 mins
tags:
layout: layouts/post.njk
---


####  Project Overview

- This project used to manage Student information like
  - name,email,mobileNo,password,dob
  - class

##### Table 1: Create students table


```sql
  create table students (
    id int primary key auto_increment,
    name varchar(100) not null,
    email varchar(100) not null,
    mobile_no bigint not null,
    password varchar(100) not null,
    gender char(1) not null,
    dob date,
    created_date timestamp not null default current_timestamp,
    unique (email),
    check ( gender in ('M','F'))
  );
```
- Note: MySQL Syntax

| student_id| name  | email  | mobile_no  | password  | gender | dob | created_date |
|---|---|---|---|---|---|---|---|
| 1 | Naresh   | n@gmail.com  | 1234567890  | pass123  | M | 2000-01-01 | 2020-09-25 18:59:51 |
| 2| Selvi  |  s@gmail.com | 2345678901  |  pass234 | F |  | 2020-09-30 18:59:51 |
| 3| Murali  | m@gmail.com  | 3456789012  |  pass123 | M |  | 2020-10-25 18:59:51 |

##### Table 2: Student Class Information

```sql
  create table student_class (
    id int primary key auto_increment,
    student_id int not null,
    class int not null,
    status varchar(20) not null,
    foreign_key (student_id) references students(id),
    check( class >= 1 and class <=12),
    check (status in ('ACTIVE','INACTIVE'))
  );
  ```

| id| student_id  | class  | status  |
|---|---|---|---|
| 101 | 1   | 5  | ACTIVE |
| 102 | 2  |  6 | INACTIVE |
| 103 | 3  | 6 | ACTIVE  |


##### Feature 1: Student Registration

```sql
insert into students ( name, email,mobile_no,password) values ('Naresh','n@gmail.com',1234567890,'pass123');
```

##### Feature 2: List All Students

```sql
select * from students;
```

##### Feature 3: Login with email and password

```sql
select * from students where email = 'n@gmail.com' and password = 'pass123';
```

##### Feature 4: Update Password

```sql
update students set password='pass1234' where  email = 'n@gmail.com';
```


##### Feature 5: Enroll Student into Class

```sql
  insert into student_class ( student_id, class, status) values ( 1, 5, 'ACTIVE');
```

##### Feature 6: Find Students who are enrolled in the given class

- Find Students who are studying in 5th standard.

```sql
  select * from student_class where class = 5;
```


##### Feature 7: Update Student Class information

- Update student from 5th standard to 6th standard.


```sql
  update student_class set class=6 where student_id = 1;
```

##### Feature 8: Student withdrawn from a Class

```sql
update student_class set status='INACTIVE' where student_id = 1;
```

##### Feature 9: Find student details who have not updated their Date Of Birth

```sql
select * from students where dob is null;
```

##### Feature 10: Find Total no of students actively studying in this school

```sql
select count(*) as no_of_students from student_class  where status ='ACTIVE';
```


##### Feature 11: Find Total no of students actively studying in each class

```sql
select class, count(*)  as no_of_students from student_class  where status ='ACTIVE' group by class;
```

##### Feature 12: Find Total no of students actively studying each class which has less than  5 students.

```sql
select class, count(*) as no_of_students from student_class  where status ='ACTIVE' group by class having count(*)<= 5;
```

##### Feature 13: Display student and class details

- Using Joins (Inner Join)
```sql
select s.id, s.name,  sc.class from students s, student_class sc where s.id = sc.student_id ;
```

- Using Subqueries ( Scalar SubQuery)
```sql
select s.id, s.name,  (select sc.class from student_class sc where sc.student_id = s.id) as class from students s;
```

##### Feature 14: Display Student Details for the given input class

- Class : 5th Standard

- Using Joins
```sql
select s.id, s.name from students s, student_class sc where s.id = sc.student_id and sc.class=5;
```

- Using Subqueries (Correlated SubQuery)
```sql
select s.id, s.name from students s and exists
(select 1 from student_class sc where sc.student_id = s.id and sc.class=5);
```

###### Feature 15: Find Class for the given student email id

- Email: n@gmail.com

- Using Subquery ( single row subquery )
```sql
  select student_id, class from student_class where student_id = ( select id from students where email='n@gmail.com');
```

###### Feature 16: Find Students who has not enrolled in a class

- Using Subquery ( multiple row subquery )
```sql
select * from students where id not in ( select student_id from student_class );
```

###### Feature 16: Display all students name with class - include both enrolled and not enrolled

- Using Joins ( Left outer join)
```sql
select s.id, s.name, s.email, sc.class from students s left outer join student_class sc on s.id = sc.student_id;
```

- Using Joins ( Right outer join)
```sql
select s.id, s.name, s.email, sc.class from student_class sc right outer join students s on s.id = sc.student_id;
```
