---
title: GroceryApp
description:
date: 2020-03-02
duration: ~60 mins
tags:
layout: layouts/post.njk
---


####  Project Overview

- This project used to manage grocery products and order items.
  - product name,price
  - user details
  - order details


##### Table 1: Create Products table (Table name: products)

| id| name | active |
|---|---|---|
| 1 | Sugar  | 1 |
| 2 | Salt  | 1 |
| 3 | Tea | 1 |
| 4 | Toothbrush | 0 |



##### Table 2: Create Products Price ( Table name: product_price)

| id| product_id | price |
|---|---|---|
| 1 | 1  | 100 |
| 2 | 2  | 20 |
| 3 | 3 | 15 |
| 4 | 4 | 25 |


##### Table 3: Create Users table ( Table name: users )


| user_id| name  | email  | mobile_no  | password  | gender | address | created_date |
|---|---|---|---|---|---|---|---|
| 1 | Naresh   | n@gmail.com  | 1234567890  | pass123  | M | Chennai | 2020-09-25 18:59:51 |
| 2| Selvi  |  s@gmail.com | 2345678901  |  pass234 | F | Adyar | 2020-09-30 18:59:51 |
| 3| Murali  | m@gmail.com  | 3456789012  |  pass123 | M | Ambattur | 2020-10-25 18:59:51 |


##### Table 4: Orders table ( Table name: orders )

| id| user_id | total_amount | ordered_date | modified_date | status | comments |
|---|---|---|---|---|---|---|
| 1 | 1  | 160 | 2021-01-01 10:00 | 2021-01-01 16:00 | DELIVERED |On time delivery |
| 2 | 1  | 20 |2021-01-01 10:00 |2021-01-01 10:00  | ORDERED | |
| 3 | 2 | 15 |2021-02-01 10:00 | 2021-02-01 10:00 | ORDERED | |
| 4 | 3 | 40 |2021-02-11 10:00 | 2021-02-12 12:00 | CANCELLED | Delivery Delayed |


##### Table 5: Order Items table (Table name: order_items)

| id| order_id | product_id | price | quantity | total_amount | status |
|---|---|---|---|---|---|---|
| 1 | 1  | 1 |  100 | 2 | 200 | ORDERED |
| 2 | 1  | 2 | 20 | 3 |60 | ORDERED |
| 3 | 2 | 2 | 20 | 1 |20 | ORDERED |
| 4 | 3 | 3 | 15 | 2 | 30 | CANCELLED |

