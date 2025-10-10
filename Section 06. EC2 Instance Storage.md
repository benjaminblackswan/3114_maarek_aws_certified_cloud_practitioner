# 50. Elastic Block Store (EBS) Overview

see https://docs.aws.amazon.com/ebs/

You can attach an EBS volume to an EC2 instance, one EBS can attached to only one instance (except those with **EBS multi-attach** feature) but an instance can have one or more EBSs. Just like an USB stick.

EBS is persistant, meaning the data persist even after the EC2 termination.

EBSs are AZ specific, meaning that they can not move to a different AZ.

<img width="565" height="674" alt="image" src="https://github.com/user-attachments/assets/c809445c-14ee-4831-b481-3955fe68e681" />


## Delete on termination

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/preserving-volumes-on-termination.html

<img width="1198" height="233" alt="image" src="https://github.com/user-attachments/assets/52a63bfd-df2c-4e18-90c3-fdba004e53a2" />

# 52. EBS Hands On

Info regarding EBS for an instance can be found under the Security tab

<img width="1400" height="611" alt="image" src="https://github.com/user-attachments/assets/771cb1b8-41cf-42e3-b1d9-b82cb0de04d8" />

if you click on the volume ID, it will take you to the volume page. 

<img width="228" height="130" alt="image" src="https://github.com/user-attachments/assets/0639b829-3749-4cb9-8000-468d55738459" />


## Create new EBS volume

Before you create a new EBS volume, you must find the EC2 instance that you want to attach to's AZ code, this is found under the instance's **Networking** tab.

<img width="1262" height="225" alt="image" src="https://github.com/user-attachments/assets/21525eb6-7f3f-4d98-92d0-6d3c24916d80" />

choose
* gp2
* 2 gb
* us-east-1d

<img width="865" height="700" alt="image" src="https://github.com/user-attachments/assets/1be7c5e7-64f3-4dc2-8f18-56bd8ca48689" />

To see all the EBS volumes that you currently have (attached and non-attached), go to the left panel and click on **Volumes**

<img width="232" height="127" alt="image" src="https://github.com/user-attachments/assets/d5f5415f-a1d1-4440-9e89-be385f7351fd" />






























