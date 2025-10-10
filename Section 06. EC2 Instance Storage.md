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

### EBS with the same AZ

Before you create a new EBS volume, you must find the EC2 instance that you want to attach to's AZ code, this is found under the instance's **Networking** tab.

<img width="1262" height="225" alt="image" src="https://github.com/user-attachments/assets/21525eb6-7f3f-4d98-92d0-6d3c24916d80" />

choose
* gp2
* 2 gb
* us-east-1d

<img width="865" height="700" alt="image" src="https://github.com/user-attachments/assets/1be7c5e7-64f3-4dc2-8f18-56bd8ca48689" />

To see all the EBS volumes that you currently have (attached and non-attached), go to the left panel and click on **Volumes**

<img width="232" height="127" alt="image" src="https://github.com/user-attachments/assets/d5f5415f-a1d1-4440-9e89-be385f7351fd" />

If you select the EBSs we just created, you can see that under volume state, it says "Available", meaning that it is not attached.

<img width="1327" height="668" alt="image" src="https://github.com/user-attachments/assets/c3aabddb-1f1f-49e9-a3ee-bb47e8eaa748" />


now if you go to Storage of the instance, you can see there are now two EBS attached under Block devices

<img width="966" height="94" alt="image" src="https://github.com/user-attachments/assets/2360853d-982c-467b-97f9-be840ecc8aa4" />

### EBS in a different AZ

lets create another EBS with us-east-1c AZ (instead of 1d)



<img width="882" height="101" alt="image" src="https://github.com/user-attachments/assets/7d9ae43c-2abd-4ec3-b637-384cc2bb1702" />

as you can see, there is no instance found under this AZ, therefore you can not attach it to our instance.

<img width="625" height="386" alt="image" src="https://github.com/user-attachments/assets/e16d2b16-05f4-4acd-865e-79d302f07a93" />

## Delete on Instance Termination

go to the storage of the instance, you can see the values for delete on termination 

<img width="1338" height="710" alt="image" src="https://github.com/user-attachments/assets/3098a9cf-6d4a-4251-a59b-771f468ef876" />

yes for root EBS (8GB), and no for the auxilliary EBS (2GB) we attached.

lets delete (terminate) the instance and check the EBS volumes

as you can see only the 2GB left

<img width="1382" height="183" alt="image" src="https://github.com/user-attachments/assets/df2c7704-ffea-4f4b-9514-c2e8c9951ee9" />



#  53. EBS Snapshots

Snapshot is used to copy data from one EBS to another to or for backup.

## demo

## Create snapshot

select the volume that you want then Action > Create snapshot

<img width="252" height="400" alt="image" src="https://github.com/user-attachments/assets/f649dad8-30b1-47fc-92e6-15fe18ea68b0" />

Then go to Snapshot on the left panel

<img width="212" height="124" alt="image" src="https://github.com/user-attachments/assets/0f84b76c-18c4-4cbc-809d-77b5ad0669d6" />

## copy snapshot

Copies an existing snapshot (of an EBS volume) to:

The same AWS Region, or

A different Region (cross-region copy).

The copied snapshot remains a backup, not an active disk or volume.

Often used for:

Cross-region disaster recovery

Backup management

Sharing snapshots across accounts

<img width="347" height="311" alt="image" src="https://github.com/user-attachments/assets/aa3ed477-81d4-480f-b387-8c73145092ee" />

## Create Volume from Snapshot

<img width="788" height="308" alt="image" src="https://github.com/user-attachments/assets/0b7ce071-4732-4d59-a4ec-90b8a943a661" />

<img width="306" height="302" alt="image" src="https://github.com/user-attachments/assets/a3bdaeb3-4acd-4121-92ce-19698c1541bd" />

Creates a new EBS volume that you can attach to an EC2 instance — based on data stored in a snapshot.

I create a new volume from the snapshot, in us-east-1f

<img width="1365" height="206" alt="image" src="https://github.com/user-attachments/assets/565522b5-d897-4b05-ab48-0223891c2833" />

## Recycle Bin

In your snapshots console, click on Recycle Bin

<img width="340" height="73" alt="image" src="https://github.com/user-attachments/assets/38769858-68a6-452a-9e81-ee38f736768a" />

## create retention rule

retention rule rule: demoRetentionRule

resource type: EBS snapshots

Retention period: 5 days

rule lock settings: unlock

In Recycle Bin console, under Retention rules

<img width="1644" height="322" alt="image" src="https://github.com/user-attachments/assets/2e88cc92-3e86-447a-baa7-d283ba3f9712" />

lets delete the snapshot

# 55 AMI

<img width="522" height="398" alt="image" src="https://github.com/user-attachments/assets/19a88ee3-ceca-42ae-a315-45c311b3a00d" />

Create a new EC2 instance, everything is the same except in the Data User field, it is one line less

```
#!/bin/bash
# Use this for your user data (script from top to bottom)
# install httpd (Linux 2 version)
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
```

To create an AMI, Action > Image & Template > Create Image

<img width="719" height="301" alt="image" src="https://github.com/user-attachments/assets/156db700-403e-4d9a-af98-b8fd68eb5715" />

Give the image a name and create the image, it will take a few minutes, so be patient.

Go to the LP and click on AMIs

<img width="173" height="101" alt="image" src="https://github.com/user-attachments/assets/0c8984c9-ca1d-48c2-b6d1-ad8cef13c979" />

And check the status of the AMI just created, make sure the status is "available"

<img width="1387" height="190" alt="image" src="https://github.com/user-attachments/assets/532e8d9b-aa7d-4ad9-bb04-303737d78ac5" />

## Creating Instance from AMI

now when you create a new EC2 instance,  you can choose the image you created under the **My AIMs** tab

<img width="1061" height="730" alt="image" src="https://github.com/user-attachments/assets/56f1632f-acd8-491d-b3b1-723f43e0240f" />


# 58. EC2 Instance Store

<img width="493" height="289" alt="image" src="https://github.com/user-attachments/assets/4591c3dd-d95f-430a-a4bd-1a8d629095ce" />


# 59. Elastic File System (EFS) Overview

<img width="459" height="364" alt="image" src="https://github.com/user-attachments/assets/0d171482-c19d-4df3-b0e1-d527972cfb2c" />

### EBS vs. EFS

<img width="783" height="548" alt="image" src="https://github.com/user-attachments/assets/99838cfa-ba20-48de-b007-bfae5ae64c43" />

### EFS-IA

This is the Infrequent Access version of EFS, optimized for cheap storage.

<img width="308" height="570" alt="image" src="https://github.com/user-attachments/assets/b5dd16e6-82ae-4451-a3bf-4870365d1b33" />


# 61. Amazon FSx Overview

## 61.1 Amazon FSx for Windows File Server

fully managed Windows native shared file system, support SMB and NTFS.


<img width="556" height="579" alt="image" src="https://github.com/user-attachments/assets/ffa84348-6f35-42a3-98d0-3ee1c385deda" />





## 61.2 Amazon FSx for Lustre

Full managed for high performance computing, for linux or mac only.



# 62 Clean up

In the EC2 console, the **Resources** display all resources in use.

<img width="886" height="267" alt="image" src="https://github.com/user-attachments/assets/8e0f2380-3bc2-40b8-a324-8fe8b2b6740a" />

Delete all the resources ie all the instances, volumes and AMIs

Note: Deleted instances will remain on AWs for a while, but the Instance State should say "Terminated".

# Quiz 4: EC2 Instance Storage Quiz

<img width="833" height="453" alt="image" src="https://github.com/user-attachments/assets/a6eebb83-1fcf-43b0-a5ca-242f0d748988" />


<img width="839" height="461" alt="image" src="https://github.com/user-attachments/assets/6f0187a4-336f-409d-a93c-fbd35857cd8b" />

<img width="849" height="421" alt="image" src="https://github.com/user-attachments/assets/6258f551-684d-4686-8607-216c55a4b7d1" />

<img width="830" height="426" alt="image" src="https://github.com/user-attachments/assets/8aadeaa2-e54a-4d02-86b9-5ef765978c86" />


<img width="853" height="317" alt="image" src="https://github.com/user-attachments/assets/e195a91c-2598-49bc-a852-f7bb2d721ff9" />

<img width="834" height="319" alt="image" src="https://github.com/user-attachments/assets/3a55c611-0306-49fa-bfb2-7b222971acdf" />

<img width="830" height="391" alt="image" src="https://github.com/user-attachments/assets/382dc742-1acd-4a15-bff2-f87eaa8f64b5" />


<img width="821" height="361" alt="image" src="https://github.com/user-attachments/assets/45c4b6b1-62eb-4c3d-9375-804f11fdf3a1" />


<img width="847" height="370" alt="image" src="https://github.com/user-attachments/assets/3e212fa2-f03c-4863-8046-e11c74b6b82c" />

<img width="827" height="428" alt="image" src="https://github.com/user-attachments/assets/5505b4b3-9517-4c2b-ac53-61b212aa3705" />











