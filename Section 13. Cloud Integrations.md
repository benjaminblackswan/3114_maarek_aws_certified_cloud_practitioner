# 150. Cloud Integrations

<img width="556" height="177" alt="image" src="https://github.com/user-attachments/assets/d2acbbc1-2270-48dd-9d8c-121fe93a30cf" />

Some AWS services that can be used to decouple your applications are
* SQS
* SNS
* Kinesis

# 151. Simple Queue Service (SQS)

<img width="458" height="321" alt="image" src="https://github.com/user-attachments/assets/bd051b2d-b04d-467f-823d-a1344aac6305" />

* AWS oldest offering
* retention 4 days, max 14 days

<img width="538" height="348" alt="image" src="https://github.com/user-attachments/assets/28cbf4e3-1fb3-45d2-8d03-ae2ddb3d01ac" />

## FIFO queue

<img width="807" height="114" alt="image" src="https://github.com/user-attachments/assets/d78732b0-3cca-420a-b08d-178e783cdbc2" />

SQS concole > Create Queue

1. Create Queue > Standard, name: demo-sqs

create queue

<img width="1392" height="184" alt="image" src="https://github.com/user-attachments/assets/db8b2cc0-5ee8-45fb-bc9f-89fa1df74ff0" />

type in "hello world" into the message body and send message

<img width="1362" height="324" alt="image" src="https://github.com/user-attachments/assets/f6c7e2f4-d83c-4a89-a72c-3a8e8f7df1bd" />

<img width="1370" height="411" alt="image" src="https://github.com/user-attachments/assets/dc603f02-e5f5-49be-847a-5d1f69ca1306" />

# 153. Kinesis Overview

<img width="530" height="373" alt="image" src="https://github.com/user-attachments/assets/6e150c25-71d6-4a7c-b7fa-a4b1024a0e71" />

# 154. Simple Notification Service (SNS)

<img width="547" height="297" alt="image" src="https://github.com/user-attachments/assets/12b23db6-8b8f-4dc5-b736-0ab66ceacdd2" />

<img width="506" height="326" alt="image" src="https://github.com/user-attachments/assets/de5dcdf1-7b87-4911-8795-65a11725a82a" />


## SNS hands-on

Go to SNS console and create a topic *demo-sns*

<img width="1183" height="683" alt="image" src="https://github.com/user-attachments/assets/5fe0394c-c262-4199-b785-807792b091d3" />

Click Create subscription

* protocol: email
* Endpoint: @gmail.com

Click Create subscription

<img width="1205" height="346" alt="image" src="https://github.com/user-attachments/assets/41be4b39-2e3f-4389-950d-0d7e79e96b1a" />

now if you go back to the subscription *demo-sns* Topics > subscriptions tab

<img width="1188" height="314" alt="image" src="https://github.com/user-attachments/assets/c08abb9c-1d84-4305-b783-820551373802" />

you can see all the subscriptions we just created.

# 156. Amazon MQ (message queue)

* SQS and SNS are AWS cloud proprietary prococols.
* If you want to use on-prem protocols such as MQTT, AMQP etc, you have to use Amazon MQ


# Cloud Integrations Quiz

<img width="848" height="521" alt="image" src="https://github.com/user-attachments/assets/ce1f60f9-4195-45a9-b7ac-35c3ded16bc0" />

<img width="834" height="441" alt="image" src="https://github.com/user-attachments/assets/f4248fe1-423e-403d-913d-78de5f166b4b" />

<img width="825" height="336" alt="image" src="https://github.com/user-attachments/assets/6c42a693-0725-41bb-8e9c-10697ac8ce12" />

<img width="834" height="414" alt="image" src="https://github.com/user-attachments/assets/0464a738-6f94-41ff-951a-60bbb2c14d0e" />

<img width="829" height="412" alt="image" src="https://github.com/user-attachments/assets/590c35d1-ad73-49ce-b2d6-2ff5255d9079" />
