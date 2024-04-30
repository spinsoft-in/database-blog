---
title: Installation
description: 
date: 2020-01-01
duration: ~20 mins
tags:
layout: layouts/post.njk
---


###### Task 1: Download MySQL Server 

- https://dev.mysql.com/downloads/mysql/
- MySQL Community Server 8.0.22

###### Task 2: Install MySQL Server 

- Set root user credentials - root/password
- Default Port: 3306
- Machine : localhost

###### Task 2.1: Restart MySQL Server

- services.msc (Type in run command in Windows)
- MySQL - restart the service

###### Task 3: Install Workbench Editor

- Install Workbench

###### Task 3.1 : Open workbench and Test the credential

- New Connection
  - Connection Name: local-db
  - Hostname: 127.0.0.1
  - Port: 3306
  - Username: root
  - Password: password
- Test Connection
- Connect