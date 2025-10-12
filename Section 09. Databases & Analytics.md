# 94. RDS & Aurora Overview

## Relational Database Service
Why is it better than create a RDBMS on EC2? Because
* automated provisioning and os patching
* continuous backups
* multi Az set up

but we can not SSH into RDS

<img width="640" height="545" alt="image" src="https://github.com/user-attachments/assets/44a54e07-9b97-4102-a835-cda354c261a5" />

## Aurora

Aurora is AWS proprietary technology based on PostgreSQL and mySQL, it is claimed to be 3 to 5x faster than PostgreSQL and mySQL on RDS.

### Aurora Serverless

pay as you go model version of Aurora, good for infrequent and intermittent workloads.

<img width="352" height="600" alt="image" src="https://github.com/user-attachments/assets/a02b00d7-a7ef-4946-8217-75fa18eb9a9a" />

# 95. RDS Hands On

Search for RDS > PL > Databases > Create Database

Creation Method: standard

Engine options: MySQL

Edition: 8.0.42

Template: Free Tier

DB Instance Identifier: database-1

Credential Settings: master username: admin

Instance Configuration: db.t3.micro

storage: gp2 @ 20gb

Connectivity: choose the default VPC

Public Access: yes

create a new VPC sg name

AZ : no preference

database port: 3306

DB authentication: password

and create database, it will take a few minutes 


## Create a snapshot


# 96. RDS Deployments Options

## Read Replicas same region

you can crease up to 15 **Read Replicas**

data can only be written to the main RDS DB.

<img width="307" height="311" alt="image" src="https://github.com/user-attachments/assets/8fc1fd4a-4fa9-4aec-8d50-48b63e055419" />


## Read Replicas cross region for DR

<img width="883" height="360" alt="image" src="https://github.com/user-attachments/assets/f0a2395d-080d-4bf5-8625-f2bc112f492e" />



## Multi-AZ failover

data can only be read/written to the main database

there can only be one failover.

<img width="334" height="317" alt="image" src="https://github.com/user-attachments/assets/bd73b570-4da7-4017-8618-59615316e19c" />


# 97. ElastiCache Overview

<img width="750" height="572" alt="image" src="https://github.com/user-attachments/assets/f5f1a6d1-c6be-43de-b03c-efd6753b074d" />


# 98. DynamoDB Overview

* NoSQL database
* serverless
* low latency retrieval

## DynavoDB accelerator DAX

in-memory cache for DynanoDB, similar to ElastiCache

## 99. DynamoDB Hands On

Create a DynamoDB called *3114-Demo-Table*

<img width="808" height="35" alt="image" src="https://github.com/user-attachments/assets/71b4890d-58af-4e44-bd68-9b1395d0c0fc" />

Click on Explore Table items 

<img width="686" height="590" alt="image" src="https://github.com/user-attachments/assets/4b114b2a-d9f3-4261-8c3f-64515649d2f2" />

<img width="669" height="297" alt="image" src="https://github.com/user-attachments/assets/c7d70ea5-521d-4aa0-97db-d91aa8da3f77" />

<img width="1282" height="260" alt="image" src="https://github.com/user-attachments/assets/693f9862-4c5f-481d-98b8-4ead6f39830b" />

Now we have an item in DynamoDB

<img width="742" height="177" alt="image" src="https://github.com/user-attachments/assets/17dc3624-b75b-4399-81db-671fd1601419" />


<img width="754" height="246" alt="image" src="https://github.com/user-attachments/assets/aff97b4c-c86f-49f1-912c-0436b43f2d5a" />

## 100. DynamoDB Global Tables

makes DynamoDB accessible in multiple regions

it is active-active replication.

<img width="753" height="480" alt="image" src="https://github.com/user-attachments/assets/0ef16a2d-d6d5-484d-b7be-2890de200980" />


# 101. Redshift Overview

### overview

* based on PostgreSQL
* for OLAP
* Columnar storage
* MPP

### Redshift Serverless

* autoscale
* PAYG


## 102. EMR Overview

Elastic MapReduce for creating Hadoop clusters from EC2 instances.

## 103. Athena Overview

* Serverless query service to perform analytics against S3 Objects
* Built on Presto

<img width="208" height="594" alt="image" src="https://github.com/user-attachments/assets/7b9f07c4-c471-46ae-a8aa-eda16c19f1fb" />


## 105. DocumentDB Overview

AWS implementation of MongoDB

























































































































