# 138. Why Global Applications?
* Decreased Latency
* Disaster Recovery
* Attack protection

# 139 139. Route 53

* Managed DNS

Types of records
* A record (IPv4) : www.google.com to 12.34.56.78
* AAAA IPv6 : www.google.com to 2001:0db8:85a3:0000:000:8a2e:0370:7334
* CNAME: search.google.com to www.google.com
* Alias: example.com to AWS resource

<img width="731" height="423" alt="image" src="https://github.com/user-attachments/assets/87f5799a-1bc4-4b03-b4a3-750c1306f896" />

## the 4 Route 53 Routing Policies
* Simple routing policy
  - <img width="388" height="257" alt="image" src="https://github.com/user-attachments/assets/44a729a1-f87e-4979-8b21-b90723b0ff4a" />
* weighted Routing Policy
  - <img width="368" height="302" alt="image" src="https://github.com/user-attachments/assets/c557ae86-fa96-4d31-b6ff-91dbac020a0d" />
* Latency Routing Policy
  - <img width="395" height="298" alt="image" src="https://github.com/user-attachments/assets/476b786c-3d50-4beb-8d46-75cffa96dcce" />
* Failover rounting Policy
  - <img width="386" height="300" alt="image" src="https://github.com/user-attachments/assets/381bb1d7-12a6-430e-b3d1-30bcb9ec898c" />


# 140. Route 53 Hands On

### Create first instance
1. Go to Route 53 console
2. register a domain.. will cost money
   - <img width="1096" height="85" alt="image" src="https://github.com/user-attachments/assets/e8d5b716-bb06-469e-bbde-8c6226d26bef" />
3. Create an EC2 in Ireland.. instance ending in **d0cc**
   - currently if you check the Hosted zone details, you should there are only two DNS...
   - <img width="1155" height="389" alt="image" src="https://github.com/user-attachments/assets/7d75abee-02bf-4989-bac5-10375cb38f53" />
5. copy the IPv4 address, which is 34.242.90.201

### Create a second instance
1. change region to US-oregon
2. create another EC2 Instance, ending in **ba31** with IPv4 address of 52.36.113.1

### Go to Route 53
1. create a record
2. routing policy : Latency

### Check the Records of Route 53 again

<img width="887" height="436" alt="image" src="https://github.com/user-attachments/assets/9fc9bd44-44dd-44a5-ade5-8e8202354a9f" />

# 141. CloudFront
* it is a Content Delivery Network (CDN)
* Cached at the edge
* DDoS protection

<img width="500" height="433" alt="image" src="https://github.com/user-attachments/assets/a9a40b61-7dea-4227-89c1-f538697c866d" />


## 142. CloudFront Hands On 

### Create an S3 bucket
1. first create a S3 bucket called *demo-cloudfont-stephane-v6*
2. upload some files
3. Remember that object url will not work because the object is not public
https://demo-cloudfont-stephane-v6.s3.us-east-1.amazonaws.com/index.html

### create CloutFront
How can we make it accessible without make the object public? 
1. Create a CF distribution
   - <img width="1383" height="783" alt="image" src="https://github.com/user-attachments/assets/de68aee6-ddae-43f2-b546-7bbf4aae5892" />

2. Specify origin > choose the S3 bucket
   - <img width="958" height="1227" alt="image" src="https://github.com/user-attachments/assets/5ddc2dfa-9d45-4493-b2d8-4d242df6119d" />

3. Enable Security
   - Do not use security protection
  
4. Review and Create distribution

If you go back to the S3 bucket, you can see that there is now a Bucket policy

<img width="1245" height="1247" alt="image" src="https://github.com/user-attachments/assets/c101ea01-8d64-4fe8-91e8-085111da81ca" />

Wait for the CloudFront distribution to finish Deployment

<img width="951" height="194" alt="image" src="https://github.com/user-attachments/assets/d3245222-36a4-4fc2-a4e4-f8c8877ba0d6" />


Once the deployment is done, copy the Distribution domain name and add the file name to the end of the path and paste into browser.

<img width="950" height="230" alt="image" src="https://github.com/user-attachments/assets/af0f7ed2-b948-44dd-a197-4a30d9c252b9" />

`dqlvkp69isl0n.cloudfront.net/index.html`


<img width="537" height="536" alt="image" src="https://github.com/user-attachments/assets/1d0a5ba3-b32d-4cb2-be87-bedeb7906cec" />

# 143. S3 Transfer Acceleration

<img width="503" height="252" alt="image" src="https://github.com/user-attachments/assets/30bdc838-c7eb-4a06-96bc-87fd43d92af9" />

# 144. AWS Global Accelerator
<img width="351" height="533" alt="image" src="https://github.com/user-attachments/assets/2497cb92-0012-453f-8c41-20bb09c6c463" />

## CloudFront Vs. Global Accelerator

<img width="669" height="368" alt="image" src="https://github.com/user-attachments/assets/5e99805d-7f98-4021-95c4-e6b2b565a4a7" />

https://speedtest.globalaccelerator.aws/#

# 145. AWS Outposts

Server racks that offers the same AWS infrastruture on-prem

<img width="130" height="188" alt="image" src="https://github.com/user-attachments/assets/a7795174-79f7-4b61-8393-165db71a34a4" />






































































