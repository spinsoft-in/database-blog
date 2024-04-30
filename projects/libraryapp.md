---
title: Library App
description:
date: 2020-05-02
duration: ~60 mins
tags:
layout: layouts/post.njk
---


####  Project Overview

- This project used to manage library books.
  - Book Details  - title,category



##### Table 1: Create Book Category (categories)

| id| name | active |
|---|---|---|
| 1 | Technical | 1 |
| 2 | Novel  | 1 |


##### Table 2: Create Book Publishers (publishers)

| id| name | active |
|---|---|---|
| 1 | Orielly | 1 |
| 2 | PackPub  | 1 |
| 3| Bloomsbury | 1 |


##### Table 3: Create Books table (books)

| id| title | edition| author | publisher_id | category_id | published_date|price|
|---|---|---|---|---|---|---|---|
| 1 | Java Programming |1 | Sanjay | 1 | 1 | 2019-01-01| 300 |
| 2 | Head First JavaScript |2 | Saravanan | 1 | 1 |2020-05-01| 400 |
| 3 | Harry Potter | 10 | Rowling| 2 | 1 |2021-06-01| 600|


##### Table 4: Create Book Stock (book_stocks)

| id| book_id | quantity |
|---|---|---|
| 1 | 1 | 10 |
| 2 | 2  | 2 |
| 3| 3 | 3 |

##### Table 5: Create Users table ( Table name: users )


| user_id| name  | email  | mobile_no  | password  | gender | address | created_date |
|---|---|---|---|---|---|---|---|
| 1 | Naresh   | n@gmail.com  | 1234567890  | pass123  | M | Chennai | 2020-09-25 18:59:51 |
| 2| Selvi  |  s@gmail.com | 2345678901  |  pass234 | F | Adyar | 2020-09-30 18:59:51 |
| 3| Murali  | m@gmail.com  | 3456789012  |  pass123 | M | Ambattur | 2020-10-25 18:59:51 |


##### Table 6: Create Book Orders ( Table name: book_orders)

| id| user_id| book_id | start_date | return_date | due_date |fine_amount | status| comments |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 1 | 1| 2021-01-01 |  2021-01-10 | 2021-01-15 | 0 | RETURNED | |
| 2 | 2  | 2|2021-01-01 |  2021-01-20 | 2021-01-31 | 50 | RETURNED | 5 days fine |
| 3 | 3 | 3| 2021-01-01 |   | 2021-01-15 | 0 | PENDING | |
| 4 | 4 | 2|2021-01-01 | 2021-01-31 | 2021-01-31 | 0 | RENEWED | |
| 4 | 4 | 2|2021-01-01 |  | 2021-01-31 | 400 | BOOK_LOST | Book Lost |

- Note:
  - Fine: Rs.10 per day
  - Due Date: 15 days

