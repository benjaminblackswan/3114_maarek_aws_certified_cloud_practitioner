# 123. AWS CloudFormation

* Infracstructure as Code (IoC)
* productivity
* declarative programming

## Infrastructure Composer

<img width="745" height="347" alt="image" src="https://github.com/user-attachments/assets/ef10dcb8-e70e-4a7b-ac7e-eee4f557a3d4" />

## CloudFormation hands on

Set region to **us-east-1** N. Virginia

<img width="1048" height="712" alt="image" src="https://github.com/user-attachments/assets/c1e828a0-b4c3-4b98-83d5-4eb2d789c507" />

upload *0-just-ec2.yaml*

Click on **application Composor**

<img width="963" height="337" alt="image" src="https://github.com/user-attachments/assets/63907cf8-3750-41df-87a5-81efc5c161f0" />

Stack name : Demo-CloudFormation

add a tag name: 

<img width="983" height="164" alt="image" src="https://github.com/user-attachments/assets/43db8ee5-291a-40fc-b790-5b1250a137cc" />

**Submit**

You can see under Resources tab that an resource was created for EC2 instance

<img width="903" height="291" alt="image" src="https://github.com/user-attachments/assets/0d28faac-459b-49cd-99dc-deaa87744383" />


## Update Stack

Replace existing template

upload *1-ec2-with-sg-eip.yaml*

<img width="1049" height="780" alt="image" src="https://github.com/user-attachments/assets/6c11767a-3900-4398-935f-69c9093c3d14" />

Specify Stack details

<img width="1048" height="303" alt="image" src="https://github.com/user-attachments/assets/2212d173-62c4-4b2e-94b1-8758b008b67b" />

Review > Change set preview

<img width="1070" height="334" alt="image" src="https://github.com/user-attachments/assets/be50d7a6-70a2-4d40-8636-aa72438897bd" />

Submit

template 

<img width="890" height="199" alt="image" src="https://github.com/user-attachments/assets/5a095e08-7a71-42b8-b5cc-47cfb34bf4ca" />


# 125. AWS Cloud Development Kit (CDK)

Define AWS infrastructure using a familiar language

<img width="825" height="303" alt="image" src="https://github.com/user-attachments/assets/bc8738e0-0c37-4200-a930-40b1f5e3fb3f" />

# 126. AWS Elastic Beanstalk

For deploying and scaling web applications and services

Typical Web app 3 - tier architecture

<img width="704" height="552" alt="image" src="https://github.com/user-attachments/assets/49832a03-9ae7-4039-b86e-8ac61b4e76bf" />

* Developer centric view of deploying on AWS
* One view
* considered PaaS
* Managed services
* Health agent on EC2

## Elastic Beanstalk hands on

### Step 1. Configuration environment

Environment tier : web server

Application name : MyApplication

Platform : note.js

Application code: sample

Presets : Single instance free tier

### Step 2. Configuration service access

<img width="1214" height="404" alt="image" src="https://github.com/user-attachments/assets/7cbc5d4c-5f08-451f-a2b5-3f9f1067a3c9" />

Skip to review



## Now go to CloudFormation 

find the stack > template > View in Infracstruture Composer

<img width="991" height="533" alt="image" src="https://github.com/user-attachments/assets/9fae3305-060c-4cca-80fc-a2496e0a64cc" />


### CloudFormation vs. Beanstalk
<img width="843" height="615" alt="image" src="https://github.com/user-attachments/assets/09a75b5f-7e96-4463-99fc-cb6cb5d802e3" />

# 128. CodeDeploy Overview

# 130. CodeCommit

Github competitor, Deprecated already.

# 131. CodeBuild

# Compile source code, run, test and produces packages.
* fully managed and serverless

<img width="507" height="102" alt="image" src="https://github.com/user-attachments/assets/079e2abe-ddb6-408f-a048-81f31bc1aab2" />


# 132. CodePipeline

Orchestrate code pipelines

<img width="733" height="270" alt="image" src="https://github.com/user-attachments/assets/890bc031-1d83-416b-bff8-a6eceecd9c3e" />

# 133. CodeArtifact

* software artifact management system

# 134. Systems Manager (SSM) Overview
* manages fleet of EC2 and on-prem systems (servers) at scale
* Hybrid AWS service.

<img width="430" height="330" alt="image" src="https://github.com/user-attachments/assets/5dbef186-7d36-4c1b-8960-35e0c0863758" />


## 135. SSM Session Manager



* allows to start secure shell on EC2 and on-prem servers

<img width="239" height="342" alt="image" src="https://github.com/user-attachments/assets/504ef5dd-e22a-4fe7-9287-358b4cef6023" />

First create EC2 Instance

* do NOT allow SSH Traffic from

create new IAM role profile, with AmazonSSMManagedInstanceCore policy

<img width="1147" height="940" alt="image" src="https://github.com/user-attachments/assets/70786671-1144-4aa1-a31a-4ae166a0f500" />

Attach this role to the instance.

<img width="1219" height="608" alt="image" src="https://github.com/user-attachments/assets/8bfc3e4d-374c-40e2-b896-b2fb90f8c638" />

Go to Systems Manager  > Lp > **Fleet Manager**

<img width="1060" height="796" alt="image" src="https://github.com/user-attachments/assets/a7d5af06-1010-4277-b526-39f5eec665c6" />

<img width="1345" height="470" alt="image" src="https://github.com/user-attachments/assets/e733bf51-60b4-44e2-8696-7eb09c55d9f5" />

### three ways of SSH into EC2

There are three ways to SSH into an EC2 Instance.
* SSH using access key through PuTTY or PowerSHell etc
* EC2 Instance Connect
* SSM Session Manager

# 136. SSM Parameter Store

secure storage for configuration and secrets

<img width="1079" height="445" alt="image" src="https://github.com/user-attachments/assets/6b359fef-defe-42cf-b455-3dbdacec0a26" />































































































