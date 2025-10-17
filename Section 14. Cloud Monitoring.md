# 158. CloudWatch Metrics & CloudWatch Alarms

* CloudWatch Metrics are variables to monitor (eg. CPU utilization)
* CloudWatch Alarms: for triggering notifications for any metrics

<img width="890" height="892" alt="image" src="https://github.com/user-attachments/assets/8c2164c9-f1bc-4358-b304-92bbd75bab6a" />

## Create alarm

All Alarms > create alarm

<img width="1312" height="261" alt="image" src="https://github.com/user-attachments/assets/39744b97-4741-49b2-bcd5-4a794aa2606e" />

you can also create Cloudwatch Alarm from the EC2 instance directly.

# 160. CloudWatch Logs

* CloudWatch Logs collects logs from various AWS services

<img width="236" height="443" alt="image" src="https://github.com/user-attachments/assets/b75cb603-ee0e-4057-a2c1-43d3d579edb1" />

## CloudWatch Logs hands on

First create the *HelloWorld* Lambda function from Section 10. Other Compute Services.

in CloudWatch console > LP > Log Groups 

<img width="174" height="191" alt="image" src="https://github.com/user-attachments/assets/65376e8a-35bb-4119-9ab2-6f9288091dd0" />

you should see one log group for the Lambda function *HelloWorld*

<img width="1353" height="231" alt="image" src="https://github.com/user-attachments/assets/82388b86-c8f9-41c9-a8c7-92ff7c4475f1" />

Click on this Lambda function and you should see all the logs for this Lambda, this Lambda function was just created (2025-10-17 11:48 am) ish

### change Lambda code to test CloudWatch logs

Go to the Code tab for this Lambda and add an extra line `print("An extra line")` after `print("value3 = " + event['key3'])`

And click on deploy

<img width="579" height="445" alt="image" src="https://github.com/user-attachments/assets/721eec2c-fdbc-4155-ac3b-fa180efc298a" />


# 162. Amazon EventBridge

<img width="550" height="459" alt="image" src="https://github.com/user-attachments/assets/8c8daeca-0789-4e68-b2cc-dc8b44977400" />

<img width="606" height="574" alt="image" src="https://github.com/user-attachments/assets/48282e59-9c90-445c-93b8-209b367d8a67" />

<img width="535" height="280" alt="image" src="https://github.com/user-attachments/assets/5e51ea9a-8b51-484d-ab66-9799ae88e64f" />

## EventBridge hands on

### Time based EventBridge

<img width="327" height="366" alt="image" src="https://github.com/user-attachments/assets/e2d87575-cd72-4086-b37f-326f7c8b9b55" />

<img width="1037" height="664" alt="image" src="https://github.com/user-attachments/assets/bc92f43e-26a3-4248-9043-8b74a780b9a0" />


Schedule name: InvokeLambdaEveryHour

Occurance: Recurring schedule

Schedule type: Rate-based schedule

Flexible Time: off

Target API: AWS Lambda

Select a Lambda function and Create Schedule

you can see that a schedule has been created, which will be triggered every 1 hour.

<img width="1349" height="623" alt="image" src="https://github.com/user-attachments/assets/5939bb38-2248-4c3c-95ec-2730eb12e25b" />

### Event based EventBridge

For responding to an event within your AWS account, use Rules in your EventBridge

<img width="254" height="185" alt="image" src="https://github.com/user-attachments/assets/ae766649-6cab-4fc4-addc-49d6c14598ef" />

**Create Rule**

Rule name: *SendNotificationForLogin*

Event Bus: Default (event bus is a router device)

Rule Type: Rule with an event pattern

Event source: AWS Event

AWS Service: Sign-In portal (note this is called AWS Console Sign-in in the Maarek ccp course)

Event type: Sign-in Events

<img width="569" height="696" alt="image" src="https://github.com/user-attachments/assets/a04f0c79-eee5-4380-b31d-51256d312725" />

Target options

<img width="1043" height="808" alt="image" src="https://github.com/user-attachments/assets/ad088d0b-e67b-41f3-a0f5-854d469e27c3" />

next next create rule

<img width="1351" height="534" alt="image" src="https://github.com/user-attachments/assets/c5278aba-6dc8-42be-bf6c-aba9db11587a" />


# 164. AWS CloudTrail

<img width="596" height="531" alt="image" src="https://github.com/user-attachments/assets/6552bc81-6055-4ec5-8bc9-8a6b2dfb88c1" />


Go to CloudTrail console to see history of events

<img width="824" height="841" alt="image" src="https://github.com/user-attachments/assets/5399dac3-ee3f-497a-b401-410c3cf00dbe" />


# 166. AWS X-Ray

* is a visual analysis of your applications in AWS

<img width="569" height="287" alt="image" src="https://github.com/user-attachments/assets/3dca1c31-5f31-445c-bbbe-ba7f538ba49a" />


# 167. Amazon CodeGuru

* ML powered service for automated code reviews and application performance recommendations

<img width="682" height="294" alt="image" src="https://github.com/user-attachments/assets/9dcc56cb-e767-4cde-9443-8471a04ea6bf" />


# 168. AWS Health Dashboard

There are two types of Health Dashboard
* Service History
  - Shows all regions and all services health
* AWS Health Dashboard for your Account
  - events that might impact you.

<img width="450" height="617" alt="image" src="https://github.com/user-attachments/assets/0234e517-ab06-4237-befe-474d68afe14b" />



# Quiz

<img width="829" height="488" alt="image" src="https://github.com/user-attachments/assets/06eb5e80-70e0-424a-84d5-1bfb402a07c9" />

<img width="857" height="468" alt="image" src="https://github.com/user-attachments/assets/5f5121d6-f879-4331-bcef-215b6c9bd148" />

<img width="846" height="481" alt="image" src="https://github.com/user-attachments/assets/0f19a676-a500-4912-8afe-e6c88b73032f" />

<img width="832" height="452" alt="image" src="https://github.com/user-attachments/assets/5d0fed5c-f5f8-4276-b576-6cc3a3401d03" />

<img width="834" height="412" alt="image" src="https://github.com/user-attachments/assets/4e3e29bb-16c3-4073-be26-4ac4bc06129d" />

<img width="829" height="389" alt="image" src="https://github.com/user-attachments/assets/548641f5-1859-4d41-a6b4-88ed65dab123" />

<img width="839" height="513" alt="image" src="https://github.com/user-attachments/assets/6d08439e-ad4b-4177-a03a-e677b036a53a" />

<img width="845" height="402" alt="image" src="https://github.com/user-attachments/assets/c504609b-6005-413e-be12-0f8ba2cfbfbc" />







































