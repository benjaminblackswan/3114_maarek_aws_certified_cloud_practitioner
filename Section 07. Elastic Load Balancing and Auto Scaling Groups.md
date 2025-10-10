# 64. High Availability, Scalability, Elasticity

### Vertical scalability vs Horizontal scalability

<img width="529" height="325" alt="image" src="https://github.com/user-attachments/assets/3fce87c7-db75-404e-99bd-32d10243aa94" />

### High Availability

two data centres in different places.

Scalability - ability to accomodate a larger load making hardware stronger or adding more units of hardware.

Elasticity - auto-scaling in the cloud

# 65. Elastic Load Balancing (ELB) Overview

<img width="614" height="419" alt="image" src="https://github.com/user-attachments/assets/14ffe234-01cc-4171-8e8a-1418ec89e3a3" />

AWS ELB is managed load balancer, there are four types of ELB
1. Application LB (ALB) - layer 7
2. Network LB - (NLB) Layer 4
3. Gateway LB - (GLB) Layer 3
4. Classic LB - (CLB) Layer 4 and 7

<img width="1158" height="684" alt="image" src="https://github.com/user-attachments/assets/231771c6-0c9d-443f-9259-f1ac99d3f497" />

# 66. Application Load Balancer (ALB) Hands On

Create two instances, we have the following information.

<img width="928" height="193" alt="image" src="https://github.com/user-attachments/assets/b0ffdd6e-e255-4b0c-b9e3-37e082aa0956" />


## Create an ALB

from LP 
<img width="209" height="126" alt="image" src="https://github.com/user-attachments/assets/4322d4ec-7019-4264-a281-a5aab46891d9" />

<img width="346" height="688" alt="image" src="https://github.com/user-attachments/assets/edea9ac4-653d-45be-819d-3a3e8e3fe835" />

schema - internet facing

LB IP address type - IPv4

availability zones and subnets - choose all AZ in this region



### Create new security group

name it *demo_sg-load-balancer*

#### inbound rule

<img width="1606" height="175" alt="image" src="https://github.com/user-attachments/assets/76129771-04ea-4f40-a364-23ec581708f6" />

#### outbound rule

<img width="1581" height="172" alt="image" src="https://github.com/user-attachments/assets/4cb1da1a-db4e-429f-8773-d5546730c2ea" />

choose the newly created sg and remove the default sg


### listener and routing

listener - http port 80

routing action - forward to target groups > create target group 

create load balancer

it'll take a few minutes to provision.. once provisioned, copy the DNS name and paste it into browser..

<img width="1381" height="219" alt="image" src="https://github.com/user-attachments/assets/3b37e868-040d-410c-bc64-c859b4137fb1" />

and if you keeping on refresh it, you will get the both internal IPv4 from the two EC2.

<img width="770" height="98" alt="image" src="https://github.com/user-attachments/assets/abe9558b-2aae-4c3b-822e-773903ac1f15" />

<img width="797" height="110" alt="image" src="https://github.com/user-attachments/assets/4cff55d0-3e7a-42c2-bd83-e75cbb577fe7" />

go to LP > Load balancing > Target Groups

<img width="167" height="121" alt="image" src="https://github.com/user-attachments/assets/75ac8139-346d-4286-a532-436b9dca7bf3" />


<img width="1355" height="786" alt="image" src="https://github.com/user-attachments/assets/76fdb7da-e0c0-4884-9986-7d3308014158" />



# 67. Auto Scaling Groups (ASG) Overview


<img width="650" height="599" alt="image" src="https://github.com/user-attachments/assets/56922093-e885-4096-9204-5a810f143b8e" />

1. terminate the two previous instances.
2. LP > Auto scaling groups (ASG)
3. Launch template

4. Create Launch template

The **Launch Template** is a template for launching EC2 instances in the auto scaling, so the format is similar to creating an EC2 instance.

remember to use this for User data field under Advanced

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

Create the launch template




























































































































