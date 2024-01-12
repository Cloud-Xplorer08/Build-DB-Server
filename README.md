# Build Your DB Server and Interact With Your DB Using an App

Amazon Relational Database Service (Amazon RDS) makes it easy to set up, operate, and scale a relational database in the cloud. It provides cost-efficient and resizable capacity while managing time-consuming database administration tasks, which allows you to focus on your applications and business. Amazon RDS provides you with six familiar database engines to choose from: Amazon Aurora, Oracle, Microsoft SQL Server, PostgreSQL, MySQL and MariaDB.

## Scenario Infrastructure
![architecture1](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/fafc2967-5f90-40b2-9faa-f6221cb1420e)

## Task 1: Create a Security Group for the RDS DB Instance
We will create a security group to allow your web server to access your RDS DB instance. The security group will be used when you launch the database instance.

![create security grp](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/b8ed62eb-1b70-48e1-a908-ecb415828225)

![add inbound rule](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/a643f015-8018-4a66-8667-9ad79bd0c67e)

![security grp created](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/503efd81-b366-4194-b337-5d685a2f3028)


We will use this security group when launching the Amazon RDS database.

## Task 2: Create a DB Subnet Group

In this task, we will create a DB subnet group that is used to tell RDS which subnets can be used for the database. Each DB subnet group requires subnets in at least two Availability Zones.

![create subnet group](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/c82308d4-fddb-486d-a254-8e20cdaf3d28)

![configure subnet details](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/f078b6d8-37c0-4042-8e5f-e6c6eaf29a07)

This adds Private Subnet 1 (10.0.1.0/24) and Private Subnet 2 (10.0.3.0/24). You will use this DB subnet group when creating the database in the next task.

## Task 3: Create an Amazon RDS DB Instance
In this task, we will configure and launch a Multi-AZ Amazon RDS for MySQL database instance.

Amazon RDS Multi-AZ deployments provide enhanced availability and durability for Database (DB) instances, making them a natural fit for production database workloads. When you provision a Multi-AZ DB instance, Amazon RDS automatically creates a primary DB instance and synchronously replicates the data to a standby instance in a different Availability Zone (AZ).

![create database](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/8bfa9d82-cbbe-4393-a059-a48b2712354f)

![choose mysql](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/069721ad-9e27-4b48-b685-245877e5ec4a)

![configure database](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/720f27d4-6a9d-4bf7-b813-1abbadec29d5)

![connectivity](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/25a12127-8b77-4098-b008-fa084f2b84e2)

![template avaibility setting](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/82285304-a1ed-43a4-b6cf-4ff06e29a134)

![additional configuration](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/90c620b8-6f81-4cf2-9ebb-fba838ef8fc0)

![database created](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/7be1e636-0ac4-4f46-8adb-627bd1ad03c8)

Wait until Info changes to Modifying or Available. Scroll down to the Connectivity & Security section and copy the Endpoint field.
It will look similar to: lab-db.cggq8lhnxvnv.us-west-2.rds.amazonaws.com. Paste the Endpoint value into a text editor. You will use it later in the lab


## Task 4: Interact with Your Database
In this task, we will open a web application running on your web server and configure it to use the database.

![webserver web application](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/cdf48862-6505-4230-a0eb-f17ce0bd9279)

![RDS tab on web application](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/6cbaf182-3afa-4ecb-a9a3-d239d9cbe1a9)

![RDS fill info](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/b09d799b-a2b9-403e-9406-d919fdaea683)

![address book](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/840a4291-a554-42b5-9fb0-2f3948d3b74b)

![edit addressbook](https://github.com/Cloud-Xplorer08/Build-DB-Server/assets/71820244/c52dc78b-26ea-4d15-87aa-8575ed524c12)





