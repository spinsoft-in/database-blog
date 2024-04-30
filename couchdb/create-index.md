---
title: Create Index
description:
date: 2020-01-09
duration: ~10 mins
tags:
layout: layouts/post.njk
---


###### Task 1.1: Create index for Price column Descending ( Postman)

```
POST - {{DB_URL}}/products/_index
```

- Request Data:
```js
{
"index": {
	"fields": ["price"]
},
"name" : "products-price-index",
"type" : "json",
"partitioned": false
}
```
