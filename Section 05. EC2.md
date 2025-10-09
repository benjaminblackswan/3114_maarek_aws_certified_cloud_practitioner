# 34. AWS Budget Setup

## Monitoring

In Root: to allow IAM users access to billing information, you must make sure it is activivated in **Billing and Cost Managemnet**

<img width="320" height="408" alt="image" src="https://github.com/user-attachments/assets/0310c52d-360c-4ba0-8e81-40ed66f74176" />

<img width="1449" height="151" alt="image" src="https://github.com/user-attachments/assets/4a8da301-d5d7-483c-8eb4-6b7d008fca9e" />

Go to **Bills**

<img width="313" height="479" alt="image" src="https://github.com/user-attachments/assets/aec70506-08cc-4ec2-8022-b8325e63e8e8" />

here is where we can see charges by service

<img width="1457" height="683" alt="image" src="https://github.com/user-attachments/assets/e1e7668e-ffd3-4285-b77f-d86ef8d992a5" />

Under Cost and Usage Analysis, you can see information about **Free Tier**

<img width="273" height="233" alt="image" src="https://github.com/user-attachments/assets/b9d0f042-64b0-4a67-80ea-8b7d76152135" />

<img width="1498" height="723" alt="image" src="https://github.com/user-attachments/assets/45b3f255-6995-4e6c-b2b5-0e8b25964c13" />

## Budget

To create a Budget, go to Budgets and Planning > Budgets

<img width="253" height="142" alt="image" src="https://github.com/user-attachments/assets/5973d80a-8186-4a2b-b8be-8ae41174a336" />

<img width="360" height="282" alt="image" src="https://github.com/user-attachments/assets/f753024e-b276-4f69-a0f5-51f04eff315f" />

We are going to use a **template** called *zero spend budget*

<img width="1424" height="483" alt="image" src="https://github.com/user-attachments/assets/6696b26c-04a9-4243-95f8-4d482adaf6bc" />


add your email to Email recipients field and create a budget 


<img width="1470" height="198" alt="image" src="https://github.com/user-attachments/assets/29c17c49-f3a4-40c5-a0d1-5b92b6ba6353" />

Create a second budget using monthly template with $10 budget

<img width="1431" height="239" alt="image" src="https://github.com/user-attachments/assets/a13da771-2e18-46f1-873c-aa954d394b3e" />






# 35. EC2 Basics

EC2 is a VM offering from aws.

you must choose compute, memory, network, storage etc, these are determined by choosing the appropriate EC2 **instance type**.


<img width="898" height="257" alt="image" src="https://github.com/user-attachments/assets/1a16189a-b92c-4a96-a13f-36c546391d6d" />


# 36. Create an EC2 Instance with EC2 User Data to have a Website Hands On

go into EC2 console

First choose a region

<img width="338" height="853" alt="image" src="https://github.com/user-attachments/assets/ab3135d5-fdf1-4caf-9cf8-4b3fe0cea1f9" />


Go to Instance on the left panel and click on **Launch instances**.

<img width="1760" height="428" alt="image" src="https://github.com/user-attachments/assets/fabdc695-6994-4b43-96bf-a73bb03d9eea" />

Give it a name and choose AWs Linux and the AMI is Amazon Linux 2023 kernel-6.1 (free tier)

<img width="1143" height="762" alt="image" src="https://github.com/user-attachments/assets/fbdef4ec-6592-435a-8596-7293c656a303" />

choose t3.micro as our instance type

<img width="1081" height="217" alt="image" src="https://github.com/user-attachments/assets/a8a64efc-12d3-48af-b4a2-21c2ba487fe1" />

## Create Key Pair

A key pair is needed if we want to use SSH to get into our EC2 instance.

### RSA vs. ED25519

RSA is older and less secure but more widely adopted, so use RSA

### .pem vs .ppk

ppk is for older operating systems.

For newer systems use .pem, however, PuTTY uses .ppk, you can convert pem to ppk using PuTTYgen

Create the key, download it and keep it safe.

## Network settings

enable auto-assign public IP

Create security group to allow SSH and HTTP

<img width="1116" height="647" alt="image" src="https://github.com/user-attachments/assets/bf2d7502-f77d-4558-a4b7-aa3cbd28465d" />

## storage setting

<img width="1141" height="392" alt="image" src="https://github.com/user-attachments/assets/6ddb8be8-bb2c-459c-a36c-b7c2cf0e2e60" />


if you click on Advanced

<img width="1118" height="667" alt="image" src="https://github.com/user-attachments/assets/5cc324be-ea94-4927-9596-460f668017c6" />


## User data


paste the following code into **User Data** field

```
#!/bin/bash
# Use this for your user data (script from top to bottom)
# install httpd (Linux 2 version)
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello World from $(hostname -f)</h1>" > /var/www/html/index.html
```


<img width="792" height="485" alt="image" src="https://github.com/user-attachments/assets/0d780276-0341-47cb-befb-91af16e3759a" />

## Summary


<img width="537" height="737" alt="image" src="https://github.com/user-attachments/assets/8f2ce7ac-17b2-452d-a9ce-f54a43803a42" />

**Launch instance**

## understand the instance

<img width="1497" height="931" alt="image" src="https://github.com/user-attachments/assets/4ae5b249-9cae-41c8-957a-0a7a54a793bf" />

* Instance State = running
* public IPv4 address: communicating with the ec2 outside AWS
* private IPv4 address: communicating with the ec2 inside AWS
* Key pair name: EC2 tutorial

Security group is found under the security tab

## How to add or remove rules in security group?

<img width="218" height="188" alt="image" src="https://github.com/user-attachments/assets/7cf6e7e6-f975-4e67-9d1e-edcefadcfdb1" />

<img width="1081" height="243" alt="image" src="https://github.com/user-attachments/assets/a26a5466-041d-4f3a-8c24-11b24479dee2" />

<img width="1523" height="312" alt="image" src="https://github.com/user-attachments/assets/620ed724-b230-4bb2-90d3-39b40c98840e" />


copy the public IPv4 address <img width="306" height="66" alt="image" src="https://github.com/user-attachments/assets/d8139a63-0f13-4325-af9b-95547533848f" />

and add http:// in front to get `http://3.95.170.216`

and paste it into browser

<img width="999" height="268" alt="image" src="https://github.com/user-attachments/assets/35a2a162-7f5a-493d-b15d-7e5b2532b67a" />

without http://, it will not load.

The address used in the url is the public address but the message uses the private address

<img width="767" height="203" alt="image" src="https://github.com/user-attachments/assets/988e0e3f-a704-4bf9-ab00-17ab98ddfe7f" />

## Stopping the instance

<img width="304" height="214" alt="image" src="https://github.com/user-attachments/assets/31f59ca4-44f9-4a37-9f76-720a1d305bb1" />

refresh the previous url  `http://3.95.170.216` will get error because the EC2 is no longer running

<img width="792" height="728" alt="image" src="https://github.com/user-attachments/assets/8e0ac14f-2493-475a-887b-7c9e2112bb27" />

Restart the instance

note that the public ipv4 has changed but the private ipv4 remains the same.


<img width="698" height="71" alt="image" src="https://github.com/user-attachments/assets/0965c8d4-a2ca-44fc-96c2-b33a4b1e7f6a" />


there you must update the url with the new ipv4 to get `http://18.232.173.135`

<img width="725" height="99" alt="image" src="https://github.com/user-attachments/assets/6a2d253f-fba6-4116-b544-dc74630fd872" />

note that the internal ipv4 remains the same in the message.

# 37. EC2 Instance Types Basics

1. General purpose
2. Compute Optimized
3. Memory optimised
4. Storage optimised
5. accelerated computing

https://instances.vantage.sh for comparison.

# 38. Security Groups & Classic Ports Overview

A security group (SG) controls the traffic that is allowed to reach and leave the resources that it is associated with.

<img width="558" height="296" alt="image" src="https://github.com/user-attachments/assets/23abc8b9-51e0-41ea-ae7c-bada6353b6ea" />

<img width="1095" height="409" alt="image" src="https://github.com/user-attachments/assets/8dbf7a28-b744-41e0-8a46-ebb196b10196" />

SG are locked down to a region / vpc combination

By default, all inbound traffic is allowed, all outbound traffic is authorised.

## some important ports to remember

* 22 SSH
* 21 FTP
* 22 SFTP
* 80 HTTP
* 443 HTTPS
* 3389 Remote desktop protocol

# 39. Security Groups Hands On

In your EC2 console, go to Security Groups

<img width="239" height="190" alt="image" src="https://github.com/user-attachments/assets/4f9cfd2a-1acb-4166-92e6-a78616bf2e88" />

You can see which SG are created together by looking at their VPC IDs 

<img width="1906" height="243" alt="image" src="https://github.com/user-attachments/assets/d8af6f63-0337-430d-a245-91046c00b84b" />

in this case, you can see that sg085 and sg051 are created together.

have a look at sg-051b4c80aae4cbd2d which is attached to our current instance, it has two inbound rules

<img width="1382" height="201" alt="image" src="https://github.com/user-attachments/assets/de662582-73e4-4277-ae28-f7e03e3f1f0e" />

to get to this instance via the internet via http, we need the second inbound rule sgr-0792d91c6d6ee2b94, which is http via port 80, if we delete this rule, the internet test will fail.


<img width="1626" height="272" alt="image" src="https://github.com/user-attachments/assets/d9ff9237-2bfa-474a-bcaf-45e11d5dace6" />

`http://18.232.173.135` will fail

Lets add http on port 80 inbound rule back to sg-051b4c80aae4cbd2d, now `http://18.232.173.135` will work


<img width="1074" height="160" alt="image" src="https://github.com/user-attachments/assets/ab82523d-e009-4e72-8cb1-db0487bc7374" />

# 40. SSH Overview

<img width="1176" height="670" alt="image" src="https://github.com/user-attachments/assets/e44b51dd-da48-4dab-af80-61f991608b70" />

# 42. How to SSH using Putty (for all versions of Windows)

Download and install PuTTY.

### PuTTYgen to create .ppk file

Remember when we created the **key pair** step of Launching EC2, we chose .pem private key format, PuTTY can not work with .pem, therefore we need to convert the .pem to .ppk file using PuTTYgen app
that was installed with PuTTY.

<img width="609" height="478" alt="image" src="https://github.com/user-attachments/assets/62a20662-8d27-4609-b47a-460293a9e175" />

make sure you remove all the spaces in the .pem file name

<img width="1187" height="896" alt="image" src="https://github.com/user-attachments/assets/52bdb775-545d-4169-8064-3687fb5e8d4f" />

click save private key and save the file as .ppk and close PuTTYgen.

### Open PuTTY app

In the Host Name field type in ec2-user@ public ipv4, ie `ec2-user@18.232.173.135`

save the session as `EC2 Instance`

<img width="454" height="446" alt="image" src="https://github.com/user-attachments/assets/f59dbb0a-b2fb-42af-acbf-a15a64f6d3bc" />

Then go to

Connection
  └── SSH
        └── Auth
              └── Credentials

and load the .ppk file

go back to session and save again and click on open, you should see the following screen.

<img width="666" height="421" alt="image" src="https://github.com/user-attachments/assets/157ef425-e8ee-4e2c-80b8-f3a554bd0d43" />


# 43. How to SSH using Powershell or Command Prompt (for Windows 10 or above)

To test whether you have SSH on your computer, type in SSH into cmd or powershell and see if you get a response.

<img width="862" height="668" alt="image" src="https://github.com/user-attachments/assets/60fe54d1-a61f-4c79-a25d-50c76ac17755" />

first navigate to the directorary where the .pem file is located.. 

`cd .\OneDrive\Onedrive\Self-Studies\3114_Maarek, Ultimate AWS Certified Cloud Practitioner CLF-C02`



C:\Users\benja\OneDrive\Onedrive\Self-Studies\3114_Maarek, Ultimate AWS Certified Cloud Practitioner CLF-C02










