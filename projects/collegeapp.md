---
title: College Admission App
description:
date: 2020-01-02
duration: ~60 mins
tags:
layout: layouts/post.njk
---


####  Project Overview

- This project used to manage college admission information like
  - name,email,mobileNo,password
  - degree, department

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
| 2| Sanjay  |  sa@gmail.com | 4567890123  |  pass234 | M |  | 2020-11-30 18:59:51 |

##### Table 2: Department Details

```sql
  create table departments (
    id int primary key,
    name varchar(100) not null,
    unique (name)
  );
```

| id| name |
|---|---|
| 101 | CSE  |
| 102 | MECH  |
| 103 | EEE  |
| 104 | ECE  |



##### Table 3: Student Department Information

```sql
  create table student_class (
    id int primary key auto_increment,
    student_id int not null,
    department_id int not null,
    active boolean not null default 1,
    foreign_key (student_id) references students(id),
    foreign_key (department_id) references department(id)
  );
  ```

| id| student_id  | department_id  | active  |
|---|---|---|---|
| 1001 | 1   | 101  | 1 |
| 1002 | 2  |  101 | 1 |
| 1003 | 3  | 102 | 1  |
| 1004 | 4  | 102 | 0  |


##### Feature 1: Find Students who are enrolled in the given department

- Find Students who are studying in "CSE" department.

```sql
  select * from student_class where department_id = ( select id from departments where name='CSE');
```


##### Feature 2: Update Student Department information

- Update student department to "MECH" department.


```sql
  update student_class set department_id = (select id from departments where name='MECH') where student_id = 1 ;
```

##### Feature 3: Remove Student from a College

```sql
update student_class set active=0 where student_id = 1;
```

##### Feature 4: Find Total no of students in each department

```sql
select department_id, count(*) as no_of_students from student_class sc, departments d
where sc.department_id = d.id and sc.active=1
group by department_id;
```

##### Feature 5: Find Total no of students actively studying each department which has less than  5 students.

```sql
select department_id, count(*) as no_of_students from student_class  where active = 1 group by department_id having count(*)<= 5;
```

##### Feature 6: Display student and department details

- Using Joins (Inner Join)
```sql
select s.id, s.name,  sc.department_id from students s, student_class sc where s.id = sc.student_id ;
```

- Using Subqueries ( Scalar SubQuery)
```sql
select s.id, s.name,  (select sc.department_id from student_class sc where sc.student_id = s.id) as department_id from students s;
```

##### Feature 7: Display Student Details for the given input department

- Department : CSE

- Using Joins
```sql
select s.id, s.name from students s, student_class sc where s.id = sc.student_id and sc.department_id=(select id from departments where name='CSE');
```

- Using Subqueries (Correlated SubQuery)
```sql
select s.id, s.name from students s and exists
(select 1 from student_class sc where sc.student_id = s.id  and sc.department_id =
(select id from departments where name='CSE')
);
```

##### Feature 8: Find Department for the given student email id

- Email: n@gmail.com

- Using Subquery ( single row subquery )
```sql
  select d.name from departments d where d.id =
  ( select sc.department_id  from student_class sc where sc.student_id = ( select id from students where email='n@gmail.com'));
```

##### Feature 9: Find Students who has not enrolled in a class

- Using Subquery ( multiple row subquery )
```sql
select * from students where id not in ( select student_id from student_class );
```

##### Feature 10: Display all students name with class - include both enrolled and not enrolled

- Using Joins ( Left outer join)
```sql
select s.id, s.name, s.email, sc.department_id from students s left outer join student_class sc on s.id = sc.student_id;
```

- Using Joins ( Right outer join)
```sql
select s.id, s.name, s.email, sc.department_id from student_class sc right outer join students s on s.id = sc.student_id;
```

