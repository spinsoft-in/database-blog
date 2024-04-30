---
title: Product Pricing App
description:
date: 2020-01-02
duration: ~60 mins
tags:
layout: layouts/post.njk
---


####  Project Overview

- This project used to manage products
  - name,price,category



##### Table 1: Create Product Category ( product_categories)

| id| name | active |
|---|---|---|
| 1 | Mobile | 1 |
| 2 | Laptop  | 1 |
| 3 | Table | 1 |



##### Table 2: Create Products table

| id| name | category_id |
|---|---|---|
| 1 | Samsung Galaxy G1 | 1 |
| 2 | OnePlus  | 1 |
| 3 | Lenova Thinkpad - E450 | 2 |
| 4 | IPhone 5s | 1 |


##### Table 3: Create Product Price table

| id| product_id | price | start_date | end_date |
|---|---|---|---|---|---|
| 1 | 1 | 10000 | 2021-01-01 | 2021-01-31 |
| 2 | 2  | 30000 |2021-01-01 |  |
| 3 | 3 | 65000 |2021-01-01 |  |
| 4 | 4 | 45000 |2021-01-01 | 2021-01-31 |
| 5 | 4 | 50000 |2021-02-01 |  |

