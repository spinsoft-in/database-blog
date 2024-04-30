---
title: Payroll App
description:
date: 2020-01-11
duration: ~120 mins
tags:
layout: layouts/post.njk
---


####  Project Overview

- This project used to manage Employee Payroll
  - name,email,date of joining, date of resignation
  - salary

##### Table 1: Create employees table ( Table name: employees)

| id| name | email | password | date_of_joining| active | date_of_relieving |
|---|---|---|---|---|---|---|---|
| 1 | Naresh | n@gmail.com | pass123 | 2021-01-01 | 1 | |
| 2 | Suresh | s@gmail.com | pass123 | 2021-04-01 | 0 | 2021-07-01 |
| 3 | Murali | m@gmail.com | pass123 | 2021-06-01 | 1 | |
| 4 | Ramesh | r@gmail.com | pass123 | 2021-01-01 | 1 | |

- Note: 0 means resigned

##### Table 2: Roles ( Table name: roles )

| id| name |
|---|---|
| 1 | CEO |
| 2 | Manager  |
| 3 | Team Lead |
| 4 | Developer |

##### Table 3: Role Salary ( Table name: role_salary )

| id| role_id | salary | hra | pf | variable_pay |
|---|---|---|---|---|---|
| 1 | 1 | 5000000 | 50000 | 100000 | 10000 |
| 2 | 2 | 1000000 | 50000 | 100000 |10000 |
| 3 | 3 | 600000 | 50000 | 100000 |10000 |
| 4 | 4 | 300000 | 50000 | 100000 |10000 |


##### Table 4: Employee Role Details ( Table name: employee_roles )

| id| employee_id | role_id |  start_date | end_date | active |
|---|---|---|---|---|---|
| 1 | 1 | 1 | 2020-01-01 | | 1 |
| 2 | 2 | 2 | 2020-01-01 |  | 1 |
| 3 | 3 | 3 | 2020-01-01 | 2020-12-31| 0 |
| 4 | 4 | 4 | 2020-01-01 | 2020-12-31| 0 |
| 5 | 3 | 2 | 2021-01-01 | | 1 |
| 6 | 4 | 3 | 2021-01-01 | | 1 |

- Note:
  - CEO has no reporting person.
  - Manager and HR reports to CEO.
  - Team Lead reports to Manager.
  - EmpId: 3 promoted from "Team Lead" to "Manager"
  - EmpId: 4 promoted from "Developer" to "Team Lead"

##### Table 5: Employee Salary ( Table name: employee_salary )

| id| employee_id | month | no_of_working_days | no_of_leaves | salary | payment_date | payment_status |
|---|---|---|---|---|---|---|---|---|
| 1 | 1 | 2021-01 | 25 | 2 | 10000 | 2021-01-01 22:00:00| PAID |
| 2 | 2 | 2021-01 | 20 | 5 | 80000 | 2021-01-01 22:10:00| PAID |
| 3 | 1 | 2021-02 | 20 | 2 | 7000 | | SCHEDULED |
| 4 | 2 | 2021-02 | 20 | 1 | 90000 | | SCHEDULED |

