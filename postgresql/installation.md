---
title: Installation
description:
date: 2020-01-01
duration: ~20 mins
tags:
layout: layouts/post.njk
---


###### Task 1: Download PostgreSQL Server ( postgresql-13.3-2-windows-x64.exe)

- https://www.postgresql.org

- Download - https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
- https://get.enterprisedb.com/postgresql/postgresql-13.3-2-windows-x64.exe

###### Task 2: Install Database Server

- Set root user credentials(username/password)
- Username: postgres
- Password: postgres
- Default Port: 3306
- Machine : localhost


###### Task 3: Install Editor - pgAdmin

- https://www.pgadmin.org/download/pgadmin-4-windows/
- pgAdmin 4 v5.4 (released June 17, 2021)

###### Task 3.1 : Open pgAdmin and Set Master Password

- Master Password: postgres

###### Task 3.2 : Create Connection

- Servers -> Right Click -> Create Server

- General Tab
  - Name: local-db
- Connection
  - Host: localhost
  - Port: 5432
  - Username: postgres
  - Password: postgres

###### Task 3.3 : Connect Database

- Double click on the Servers -> local-db to connect

##### Task 3.4 : View Tables

- Database -> postgres->Schemas-> public -> Tables


##### Task 3.6: Query Editor

- Tools -> Query Tool
