---
title: BloodBank App
description:
date: 2020-03-02
duration: ~60 mins
tags:
layout: layouts/post.njk
---


####  Project Overview

- This project used to manage blood bank.
  - Donor details
  - Blood Donations Stock



##### Table 1: Create Blood Groups ( blood_groups)

| id| name | active |
|---|---|---|
| 1 | B+ | 1 |
| 2 | AB+  | 1 |
| 3 | A+ | 1 |
| 4 | O+ | 1 |


##### Table 2: Create Users table ( Table name: users )


| user_id| name  | email  | mobile_no  | password  | gender | blood_group_id| address | last_donated_on |
|---|---|---|---|---|---|---|---|---|
| 1 | Naresh   | n@gmail.com  | 1234567890  | pass123  | M | 1 | Chennai | 2021-06-25 18:59:51 |
| 2| Selvi  |  s@gmail.com | 2345678901  |  pass234 | F | 2| Adyar | 2021-04-30 18:59:51 |
| 3| Murali  | m@gmail.com  | 3456789012  |  pass123 | M | 3| Ambattur | 2021-05-25 18:59:51 |

##### Table 3: Posts ( posts )

| id| title | description | contact_no | requested_date |  verified| status | modified_date |
|---|---|---|---|---|---|---|---|---|
| 1 | B+ Required | 5 units for surgery |1234567890| 2021-04-30 18:59:51| true | CLOSED |2021-04-30 18:59:51|
| 2 | AB+ Required | 2 units for surgery |1234567890| 2021-05-30 18:59:51| false | OPEN|2021-05-30 18:59:51|
| 3 | A+ Required | 1 unit for surgery |1234567890| 2021-06-10 18:59:51| true| OPEN |2021-06-20 18:59:51|
| 4 | O+ Required | 1 unit for surgery |1234567890| 2021-07-03 18:59:51| true | CLOSED| 2021-07-10 18:59:51|


##### Table 4: Blood Donations ( Table name: blood_donations )

| id| donor_id | quantity | donated_on | status | modified_date |
|---|---|---|---|---|---|---|---|---|
|1|1|1|2021-07-10 18:59:51|DONATED|2021-07-10 18:59:51|
|2|2|1|2021-07-10 18:59:51|REJECTED|2021-07-10 18:59:51|
