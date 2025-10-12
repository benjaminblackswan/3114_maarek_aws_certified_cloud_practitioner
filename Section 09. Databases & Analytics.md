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

## 106. Amazon Neptune Overview

Used for graph database

## 107. Amazon Timestream Overview

For time series database

## 108. Amazon Managed Blockchain (AMB) Overview
making blockchain

## 109 AWS Glue

fully managed Serverless service for ETL.

<img width="595" height="230" alt="image" src="https://github.com/user-attachments/assets/4ff9b977-b4e0-43ef-a71e-6548cdb7431e" />

## 110. Data Migration Service (DMS) Overview

for data migration into AWS

<img width="157" height="461" alt="image" src="https://github.com/user-attachments/assets/2632000f-211c-4be4-b94a-421fc59c8735" />

# Databases & Analytics Quiz

<img width="843" height="485" alt="image" src="https://github.com/user-attachments/assets/24474efd-a8f7-4db6-9c2c-ce95c58dcf2c" />

<img width="857" height="439" alt="image" src="https://github.com/user-attachments/assets/47d0bd24-fbe4-4747-a433-279faa302c00" />

<img width="810" height="598" alt="image" src="https://github.com/user-attachments/assets/990e3874-a21f-49ea-a26b-f7a93d8f6ca9" />

<img width="837" height="454" alt="image" src="https://github.com/user-attachments/assets/2d4e9315-16fc-4148-9085-ced31da8c1d7" />

<img width="832" height="451" alt="image" src="https://github.com/user-attachments/assets/2fd2c257-ad75-475b-a750-279f2087b7cd" />

<img width="830" height="479" alt="image" src="https://github.com/user-attachments/assets/0d2b606e-bc88-4d5f-8425-e99022bae2f5" />

<img width="831" height="460" alt="image" src="https://github.com/user-attachments/assets/55276333-2233-4995-9cbe-7d30a4c89cdc" />

<img width="831" height="484" alt="image" src="https://github.com/user-attachments/assets/4abf479c-6b88-4e2f-b633-5d1957967858" />

<img width="837" height="522" alt="image" src="https://github.com/user-attachments/assets/6f18a210-3eff-4afb-80f4-2b6d042792e0" />

<img width="841" height="434" alt="image" src="https://github.com/user-attachments/assets/fe04d8de-b21f-42f1-b5a9-3de41d19a54e" />

<img width="830" height="483" alt="image" src="https://github.com/user-attachments/assets/f23dea8f-d268-42d3-aca7-f1efff78ef1b" />


<img width="837" height="490" alt="image" src="https://github.com/user-attachments/assets/c9f58df1-0407-4f6d-a768-0f650d8bba2a" />

<img width="830" height="498" alt="image" src="https://github.com/user-attachments/assets/3472cf4f-f7fc-459b-9066-57911b7c5382" />

<img width="827" height="487" alt="image" src="https://github.com/user-attachments/assets/f3dc6dc7-cf90-4727-874e-4a0af7527372" />

<img width="836" height="484" alt="image" src="https://github.com/user-attachments/assets/d6767dbe-ba35-4f34-ab38-723b1a10d65e" />

<img width="842" height="342" alt="image" src="https://github.com/user-attachments/assets/28b9d144-c685-4dd8-831c-e0327a900f8c" />



























































































