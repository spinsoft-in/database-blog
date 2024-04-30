---
title: Create Server
description:
date: 2020-01-01
duration: ~10 mins
tags:
layout: layouts/post.njk
---

###### Create IBM Cloudant Server

- https://www.ibm.com/in-en/cloud/cloudant
-

###### Register Account and Login

- https://cloud.ibm.com/registration
-

###### Search cloudant

- Choose "Cloudant Service"


###### Create Server

- Environment:
  - Multitenant
  - Choose region : "Chennai"

- Configure Cloundant Instance
  - Enter instance name : training

- Authentication Method
  - IAM and legacy credentials

- Click "Create"

###### Resource List

- Select "Services and Softwares"
  - Click db instance - training
    - External Endpoint (preferred) link
    - Note : copy - External Endpoint link ( save it in a notepad file for future reference)
  - Click Launch Dashboard


###### Create Service Credentials

- Select "Service Credentials" ( Sidebar )
  - Click New Credential
  - Enter Name: development
  - Select Role: Manager

- Note : copy - username/password ( save it in a notepad file for future reference)

##### Launch Dashboard

- Click "Manage" (Sidebar)
- Click "Launch Dashboard"

##### Enable CORS(Cross-Origin Resource Sharing)

- Account => CORS => Enable Cors => All domains


##### Postman - Store Credentials to test database REST APIs

- Create Collection
  - Create Variables
    - DB_URL: https://3d805feb-be8e-4768-ae9a-sssssssss-bluemix.cloudantnosqldb.appdomain.cloud
    - DB_USERNAME: username
    - DB_PASSWORD: password
  - Authorization
    - Type : Basic Auth
    - Username: {{DB_USERNAME}}
    - Password: {{DB_USERNAME}}
