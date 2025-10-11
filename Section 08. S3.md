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

### Policy Generator



















































































































