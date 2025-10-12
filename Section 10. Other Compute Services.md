## 112. What is Docker?

<img width="573" height="382" alt="image" src="https://github.com/user-attachments/assets/1a5fd3f1-0811-4960-a603-d2188128f193" />

## 113. Elastic Container Service (ECS), Fargate & ECR Overview

### Elastic Container Service (ECS)

* You must provision EC2 instance
* AWS takes care of containers
* integrates with ALB

<img width="387" height="525" alt="image" src="https://github.com/user-attachments/assets/2ef65adb-6e53-409f-b701-fc6475899b7c" />

### Fargate

* No EC2 provision
* Serverless

<img width="356" height="568" alt="image" src="https://github.com/user-attachments/assets/37620edd-5389-4c6b-b3dc-0efa071e1713" />

### Elastic Container Registry (ECR)

where you store **Docker images**

<img width="354" height="405" alt="image" src="https://github.com/user-attachments/assets/7eee7220-c6fe-4541-be1a-c7a93e4a4bee" />

## 114. Amazon Elastic Kubernetes Service (EKS)

* launches Kubernetes cluster on AWS
* Kubernetes is open source system for managing docker

<img width="302" height="594" alt="image" src="https://github.com/user-attachments/assets/4142fd8a-f319-4568-99c4-c8f9cb61b703" />

## 115. Serverless Introduction

meaning that there is no need for dev to maintain servers


# 116. Lambda Overview

<img width="569" height="434" alt="image" src="https://github.com/user-attachments/assets/053aee58-021f-4cca-856a-f57ee0dac2cb" />

* pay per request and compute time
* event-driven: functions gets invoked when needed

Lambda example 1: create a thumbnail for images uploaded to S3

<img width="608" height="604" alt="image" src="https://github.com/user-attachments/assets/7e49d20e-1854-49a5-aacb-30d3c67ec137" />


Lambda example 1: serverless CRON job

<img width="443" height="322" alt="image" src="https://github.com/user-attachments/assets/ec4e1f32-b67f-4805-a2e7-e08358924b1e" />

lambda is very cheap and is based on calls and duration (compute time)

# 117. Lambda Hands On

visit https://ap-southeast-2.console.aws.amazon.com/lambda/home?region=ap-southeast-2#/begin to see demo of Lambda

<img width="971" height="347" alt="image" src="https://github.com/user-attachments/assets/2b445b0d-9f32-4900-9224-6ed063df850d" />


## Create a Lambda function

Use a blueprint

* Basic Information
  - Blueprint name: Hello world function python 3.12
  - function name: "demo-function"
  - Execution role: Create a new role with basic Lambda permissions

Click on **Create Function**

we get 

<img width="938" height="890" alt="image" src="https://github.com/user-attachments/assets/05e9f3c8-7bd5-4fe2-9358-505165795ae1" />


Test tab > Test

The test will complete

<img width="1056" height="558" alt="image" src="https://github.com/user-attachments/assets/09bba1dc-78bb-4d54-b938-128b8e4cfa7a" />

if you remove a line from Event JSON from 

```
{
  "key1": "value1",
  "key2": "value2",
  "key3": "value3"
}
```

to 

```
{
  "key2": "value2",
  "key3": "value3"
}
```

and test again, the Lambda function will fail

<img width="717" height="688" alt="image" src="https://github.com/user-attachments/assets/54c84a9f-1e6b-447d-944f-646f175ea482" />

Configuration > Edit

<img width="1320" height="224" alt="image" src="https://github.com/user-attachments/assets/69db68ea-a3e7-4392-8dcc-063ae146d9a0" />

view the role

<img width="1580" height="789" alt="image" src="https://github.com/user-attachments/assets/ea693d56-dce4-4937-84cc-d1ce0a05f2d5" />

Click no the Policy name

<img width="728" height="257" alt="image" src="https://github.com/user-attachments/assets/570294a0-7b7e-4f6e-bd46-422cf5174c66" />

you can see what services are allowed in this policy

<img width="1056" height="256" alt="image" src="https://github.com/user-attachments/assets/5c65ab8f-fd00-4b41-b689-7e9f9f4b0221" />




















































