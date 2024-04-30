---
title: Leave Management System App
description:
date: 2020-01-11
duration: ~120 mins
tags:
layout: layouts/post.njk
---


####  Project Overview

- This project used to manage Employee Leaves
  - name,email,date of joining, date of resignation
  - leave balance

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
| 4 | HR |



##### Table 3: Employee Role Details ( Table name: employee_roles )

| id| employee_id | role_id | reporting_manager_id |
|---|---|---|---|
| 1 | 1 | 1 |  |
| 2 | 2  | 2 | 1 |
| 3 | 3 | 3 | 2 |
| 4 | 4 | 4 | 1 |

- Note:
  - CEO has no reporting person.
  - Manager and HR reports to CEO.
  - Team Lead reports to Manager.

##### Table 4: Leave Types ( Table name: leave_types )

| id| name | description |
|---|---|---|
| 1 | SL | Sick Leave |
| 2 | CL  | Casual Leave |
| 3 | EL | Earned Leave |



##### Table 5: Employee Leave Balance ( Table name: employee_leave_balance )

| id| employee_id | leave_type | no_of_days |
|---|---|---|---|
| 1 | 1 | SL | 2 |
| 2 | 1  | CL | 2 |
| 3 | 1 | EL | 0.5 |
| 4 | 2 | SL | 1 |
| 5 | 2  | CL | 1 |
| 6 | 2 | EL | 3 |
| 7 | 3 | SL | 0 |
| 8 | 3  | CL | 0 |
| 9 | 3 | EL | 0 |

##### Table 6: Employee Leave Details ( Table name: employee_leave_details )

| id| emp_id | leave_type | start_date | end_date| no_of_days | leave_reason | status | applied_on | manager_id | comments |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | 2 | CL | 2021-05-03 | 2021-05-04 | 2 | Going to hometown | APPROVED | 2021-05-01 10:00:00| 1 | |
| 2 | 3 | SL | 2021-06-04 | 2021-06-07 | 2 | Not Feeling well | APPROVED | 2021-05-25 11:00:00 | 2 |
| 3 | 2 | CL | 2021-06-04 | 2021-06-04 | 0.5 | Friend Birthday | REJECTED | 2021-06-03 16:00:00| 1 | Project Delivery |
| 4 | 2 | EL | 2021-09-04 | 2021-09-04 | 1 | Vacation | PENDING | 2021-07-03 11:00:00 | 1 | |
| 5 | 2 | CL | 2021-07-03 | 2021-07-03 | 2 | Going to hometown | CANCELLED | 2021-07-01 10:00:00| 1 | |


