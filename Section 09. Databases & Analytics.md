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

## Read Replicas


<img width="307" height="311" alt="image" src="https://github.com/user-attachments/assets/8fc1fd4a-4fa9-4aec-8d50-48b63e055419" />

you can crease up to 15 **Read Replicas**

data can only be written to the main RDS DB.

# Multi-AZ

<img width="334" height="317" alt="image" src="https://github.com/user-attachments/assets/bd73b570-4da7-4017-8618-59615316e19c" />

























































































































































