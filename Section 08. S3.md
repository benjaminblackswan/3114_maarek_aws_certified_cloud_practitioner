# 73. S3 Hands On
## create a new S3 bucket

make sure the name of your bucket is unique in the **entire AWS S3**.

**Object owership**: ACLs disabled

**Block public Access**: block all public access to make secure.

**Bucket versioning**: Diabled

**Tags**: no

**Default encryption**: Server-side encryption with Amazon S3 managed keys (SSE-S3)

**backet key**: enable

<img width="1074" height="377" alt="image" src="https://github.com/user-attachments/assets/95c8543b-c3a0-4d7d-8315-3cf3a879b167" />

## uploading to S3

upload the coffee.jpg in the S3 folder

Click on Open and also copy the **Object URL** into a browser

<img width="1314" height="601" alt="image" src="https://github.com/user-attachments/assets/8a00a421-8ee0-45b9-a777-ff6249495554" />

The Open function works

<img width="1162" height="1005" alt="image" src="https://github.com/user-attachments/assets/3660cdf8-b77a-4f39-878a-b53b01d8bdf8" />

however Object URL does not

<img width="826" height="203" alt="image" src="https://github.com/user-attachments/assets/adfc9a6d-109d-42a7-ad0a-8c54fef22008" />


WHy? The Open function actually has my own credential after the Object URL


Go back to the bucket console and create a folder called *images*

<img width="435" height="140" alt="image" src="https://github.com/user-attachments/assets/a29cc377-b7ca-4e44-a55b-b263a18f2756" />

upload beach.jpg into this folder


# 74. S3 Security: Bucket Policy

types of security

* User-based
* Resource-Based
  - Bucket policies
  - Object ACL
  - Bucket ACL

The bucket policies is json based.

## hand-on set up policy

Permission tab > edit Block public access

<img width="1584" height="444" alt="image" src="https://github.com/user-attachments/assets/b01fc2ca-d7af-4517-b4c1-6c26e50b3178" />

Then we go to **Edit Policy** and click on **Policy Generator**

# 76. S3 Website

S3 Bucket console > Properties > scroll down to website hosting > edit

<img width="1584" height="260" alt="image" src="https://github.com/user-attachments/assets/61c9508f-2629-42b2-849d-aa08812bb017" />


static website hosting > enable 

hosting type : host a static website

type in `index.html` into the Index document field


Save

Then upload the index.html file to the stephane bucket. Then copy the bucket website endpoint into browser

<img width="1533" height="409" alt="image" src="https://github.com/user-attachments/assets/37f1c958-bb3b-4b39-938e-df58894f5afe" />

`http://3114-stephane.s3-website-ap-southeast-2.amazonaws.com`

<img width="779" height="547" alt="image" src="https://github.com/user-attachments/assets/cb4202ca-db4a-47fb-b5f7-4dfa0a744989" />



# 78. S3 Versioning

Bucket console > Properties > Edit > enable

<img width="1593" height="277" alt="image" src="https://github.com/user-attachments/assets/5121b03c-2b64-44e3-88f5-00515641d31d" />

## Testing versioning

lets edit the `index.html` from 

```
<html>
    <head>
        <title>My First Webpage</title>
    </head>
    <body>
        <h1>I love coffee</h1>
        <p>Hello world!</p>
    </body>

    <img src="coffee.jpg" width=500/>
</html>
```


to

```
<html>
    <head>
        <title>My First Webpage</title>
    </head>
    <body>
        <h1>I REALLY love coffee</h1>
        <p>Hello world!</p>
    </body>

    <img src="coffee.jpg" width=500/>
</html>
```


and upload to the bucket, then turn on **show version**

<img width="1586" height="394" alt="image" src="https://github.com/user-attachments/assets/f47762dd-f89b-4a61-8828-ad2ae8eab2e7" />

You can see that only the new index.html have version ID, all files uploaded before versioning was turned on have Version ID value of null.

To go back to the previous version, you must delete the new `index.html`, the deletion is permanent.

if you delete the one with the null version ID, it will put a delete marker on it. 

<img width="1563" height="406" alt="image" src="https://github.com/user-attachments/assets/e64dcf12-793d-4406-b7d9-6482b8734dc5" />

to undo the delete, delete the **delete marker**


# 80. S3 Replication

Cross region replication (CRR) vs. Single region replication (SRR)

<img width="785" height="558" alt="image" src="https://github.com/user-attachments/assets/2ef0aaf2-6e8d-4222-8df6-1a242fdb87c7" />

CRR = different regions

SRR = same region

## S3 Replication hands on

let create two new buckets called `3114-stephane-v2` and `3114-stephane-v3`

upload the beach.jpg to  `3114-stephane-v2`

our goal is to replicate v2 to v3

### Replication Rule

In `3114-stephane-v2` bucket console > management > Replication rules > Create replication rule

<img width="1307" height="316" alt="image" src="https://github.com/user-attachments/assets/93db9709-62be-4ac4-8fcd-3d002e549735" />


rule name : demo-replication-rule

Status : Enabled

Rule scope: All objects in the bucket

Destination bucket name : 3114-stephane-v3

IAM Role : create new role

This is the rule I recreated

<img width="1444" height="286" alt="image" src="https://github.com/user-attachments/assets/68486ece-afdf-456c-aca0-2bd617559080" />

Upload the coffee.jpg to v2

in v2
<img width="737" height="51" alt="image" src="https://github.com/user-attachments/assets/298a81ac-60c7-4b81-a66a-29978ed9d249" />

in v3 

<img width="717" height="50" alt="image" src="https://github.com/user-attachments/assets/3042ca89-ef2a-4ea8-9282-ae2ac0424610" />

you can see that there two version ID are the same.


# 83. S3 Storage Classes Hands On

In the Upload page, after selecting a file for upload

Go to properties and see all the storage classes

<img width="1427" height="686" alt="image" src="https://github.com/user-attachments/assets/c5baf35e-2079-46f0-9e1e-f38aa38398c8" />

you can edit the storage class after upload.

## Lifecycle rules

in the bucket console > Management

<img width="1472" height="340" alt="image" src="https://github.com/user-attachments/assets/39d23cb2-a091-48c9-90f7-459d7336905d" />

<img width="1431" height="248" alt="image" src="https://github.com/user-attachments/assets/ee1a515c-c43c-4527-af5d-03a934df0932" />


# S3 encryption

default : server side encryption

client - side encryption : done by client

<img width="616" height="586" alt="image" src="https://github.com/user-attachments/assets/21abec8e-2eb0-4ea8-bcc0-a9f1ded5d5c5" />



#  91. Storage Gateway Overview


<img width="307" height="619" alt="image" src="https://github.com/user-attachments/assets/e97b5321-5162-44de-a7a3-21ddb2a43d00" />

bridge between on-prem and cloud data  in S3


# S3 Quiz


<img width="841" height="464" alt="image" src="https://github.com/user-attachments/assets/52038e6c-cb7d-4d10-a1fc-3d56998969cb" />

<img width="839" height="481" alt="image" src="https://github.com/user-attachments/assets/42b34db5-24c6-4437-aa2a-4470443ce47e" />

<img width="844" height="439" alt="image" src="https://github.com/user-attachments/assets/c9b46b71-7e70-4fde-8a2d-ee2a3640a235" />

<img width="825" height="437" alt="image" src="https://github.com/user-attachments/assets/583f4b45-0130-416d-8eb7-e676486fb6f1" />

<img width="833" height="452" alt="image" src="https://github.com/user-attachments/assets/c83e79a4-f496-4cc5-a639-ffbcbf13ff98" />

<img width="853" height="509" alt="image" src="https://github.com/user-attachments/assets/182b6e71-7573-473e-a66d-3302359bf179" />

<img width="842" height="520" alt="image" src="https://github.com/user-attachments/assets/96eea0d1-3c6d-45e5-986f-089c5e6b81c6" />

































