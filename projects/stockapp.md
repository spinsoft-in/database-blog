---
title: Stock Management App
description:
date: 2020-01-02
duration: ~60 mins
tags:
layout: layouts/post.njk
---


####  Project Overview

- This project used to manage product stocks.
  - name,price,category
  - stock



##### Table 1: Create Product Category ( product_categories)

| id| name | active |
|---|---|---|
| 1 | Mobile | 1 |
| 2 | Laptop  | 1 |
| 3 | Table | 1 |



##### Table 2: Create Products table ( Table name: products )

| id| name | price|category_id |
|---|---|---|---|
| 1 | Samsung Galaxy G1 | 10000| 1 |
| 2 | OnePlus  |30000| 1 |
| 3 | Lenova Thinkpad - E450 | 65000| 2 |
| 4 | IPhone 5s | 45000| 1 |


##### Table 3: Create Product Stock table ( Table name:product_stocks)

| id| product_id | quantity |
|---|---|---|
| 1 | 1 | 5 |
| 2 | 2  | 10 |
| 3 | 3 | 10 |
| 4 | 4 | 0 |

##### Table 4: Create Product Stock History table ( Table name:product_stock_history)

| id| product_id | quantity | created_date |
|---|---|---|---|
| 1 | 1 | 5 |2021-01-01 10:00:00 |
| 2 | 1  | 5 | 2021-02-01 10:00:00 |
| 3 | 2 | 10 |2021-05-01 10:00:00 |
| 4 | 4 | 2 |2021-06-01 10:00:00 |


