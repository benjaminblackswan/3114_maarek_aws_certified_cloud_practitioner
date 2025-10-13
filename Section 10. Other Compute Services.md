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
* up to 15 minutes runtime

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

### Monitor tab

<img width="237" height="53" alt="image" src="https://github.com/user-attachments/assets/54152c3b-8e68-4677-9420-296da901d18d" />

here you can see all the logs of the two events you ran

<img width="1318" height="222" alt="image" src="https://github.com/user-attachments/assets/574870f2-b18d-4a18-970b-cbf27d3ed3c5" />


### Configuration tab

#### General Configuration

<img width="1267" height="187" alt="image" src="https://github.com/user-attachments/assets/5e1e0dda-d797-4215-8216-49c4f80300e0" />

Click on Edit to edit the basic settings

Click on the role

<img width="1503" height="708" alt="image" src="https://github.com/user-attachments/assets/0b208c18-e9e7-4203-9c18-0b81b5aa763a" />

<img width="1210" height="252" alt="image" src="https://github.com/user-attachments/assets/fccc3fed-d418-428a-94b9-65c21b6da9bc" />

<img width="1220" height="313" alt="image" src="https://github.com/user-attachments/assets/28d4228f-c7e9-438c-bfa3-566919b5024b" />

### Triggers

Use trigger to trigger the Lambda function.

<img width="462" height="534" alt="image" src="https://github.com/user-attachments/assets/a91ebe0b-fdd1-4fa4-bd37-c47aacb98200" />

## 118. API Gateway Overview

<img width="879" height="203" alt="image" src="https://github.com/user-attachments/assets/e48b015e-ad3c-4856-9d86-cb86df0871f8" />

## 119. AWS Batch Overview

* A batch job has a star and end time as oppose to continuous
* defined as a Docker images and run on Elastic Container Service (ECS)
* Batch has no time limit
* not serverless, relies on EC2 and EBS

<img width="790" height="498" alt="image" src="https://github.com/user-attachments/assets/7238e01f-2065-4678-9137-0fc9fe234b9f" />

## 120. Amazon Lightsail

Designed for people who don't have limited Cloud experience.

<img width="611" height="1123" alt="image" src="https://github.com/user-attachments/assets/67352074-166b-47af-859d-45a59cf4f073" />

<img width="628" height="538" alt="image" src="https://github.com/user-attachments/assets/83f11433-0998-44d3-a2cd-fc60ddc805e0" />

# Other Compute Services Quiz

<img width="840" height="436" alt="image" src="https://github.com/user-attachments/assets/58646179-8007-475f-97c7-cb517c20de15" />

<img width="836" height="537" alt="image" src="https://github.com/user-attachments/assets/e576dd67-65bd-48fb-b64b-716230b9e560" />

<img width="845" height="534" alt="image" src="https://github.com/user-attachments/assets/3cedc64a-e2bb-46ad-86bb-1ae6e150976f" />

<img width="831" height="482" alt="image" src="https://github.com/user-attachments/assets/d7077c3b-c139-48e8-9450-ca799deca948" />

<img width="830" height="433" alt="image" src="https://github.com/user-attachments/assets/4091ae3e-842b-4d29-badd-9746ca8502ff" />

<img width="833" height="485" alt="image" src="https://github.com/user-attachments/assets/780a929b-c39f-49e2-980f-a410c35e8ca1" />

<img width="837" height="459" alt="image" src="https://github.com/user-attachments/assets/00ee980d-d0d5-4c89-9ff6-a3f6a967f960" />

<img width="841" height="444" alt="image" src="https://github.com/user-attachments/assets/d43f826c-4b26-43a7-bc78-edb7d0d11b63" />

<img width="842" height="554" alt="image" src="https://github.com/user-attachments/assets/b8faf415-8ccb-49fa-95de-32c7d165e89e" />

<img width="845" height="457" alt="image" src="https://github.com/user-attachments/assets/9aa16025-690b-4dec-9894-62e97f2ba29c" />

<img width="828" height="387" alt="image" src="https://github.com/user-attachments/assets/be3e2f19-e497-4275-aaef-061400dcc444" />
