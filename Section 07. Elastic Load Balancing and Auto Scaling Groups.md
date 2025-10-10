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

# 68. Auto Scaling Groups (ASG) Hands On

1. terminate the two previous instances.
2. LP > Auto scaling groups (ASG)
3. Launch template
5. **Create Launch template** called *demo-launch-template*

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

In network: choose default VPC and all the Az used by the EC2

Health checks: Turn on ELB health checks

group size: 2

**Scaling**: min 1 max 4

instance maintenance policy: no policy

additional capacity settings: default

Create ASG

The ASG automatically provisioned two instances

<img width="1351" height="612" alt="image" src="https://github.com/user-attachments/assets/2ed5774e-829e-44de-b065-8c8125069eae" />

The load balancer automatically assigns the two instances created by the asg as the targets

<img width="1515" height="1022" alt="image" src="https://github.com/user-attachments/assets/d52d42c6-a830-40fb-8a2f-3110f5e39eb9" />

pasting the load balancer DNS name into browser `http://demo-alb-929360010.us-east-1.elb.amazonaws.com/`

<img width="758" height="92" alt="image" src="https://github.com/user-attachments/assets/2e10c515-42f6-4b56-a4f7-cdb4fa5baf13" />


## Termination test

<img width="383" height="104" alt="image" src="https://github.com/user-attachments/assets/64323f2f-d7e5-41d7-918c-a38530e245a2" />

Currently I have two instances, lets terminate the one that ends in `dab`


<img width="738" height="209" alt="image" src="https://github.com/user-attachments/assets/61f903a5-5fe0-49e3-850f-77308221b2ed" />

under the ASG's activity history, the 'dab' instance was disconnected and new instances was automatically launched.

<img width="1440" height="599" alt="image" src="https://github.com/user-attachments/assets/eefedd9a-bc90-4233-9a20-58c6ce639d65" />

<img width="1425" height="230" alt="image" src="https://github.com/user-attachments/assets/fed0547d-41f2-4dbe-aef0-2bcd20a4cd35" />


# 69. Auto Scaling Groups (ASG) Strategies

1. manual scaling
2. dynamic scaling
   - simple/step (dynamic) scaling: this is basically if then statement
   - target tracking scaling: condition based on a target, eg 40% cpu usage
   - scheduled scaling: condition based on time
   - predictive scaling: using ML
  
<img width="837" height="429" alt="image" src="https://github.com/user-attachments/assets/8046dff7-8e89-4943-a7d5-a055ab123447" />

<img width="833" height="409" alt="image" src="https://github.com/user-attachments/assets/830f271f-19b2-4c96-9f2e-caa1028ca96f" />

<img width="839" height="458" alt="image" src="https://github.com/user-attachments/assets/4010810c-9946-4f2d-9f32-7defc3f8fb05" />

<img width="825" height="493" alt="image" src="https://github.com/user-attachments/assets/b2d0e11c-0829-4b99-afee-6f23a2ca5891" />

<img width="831" height="454" alt="image" src="https://github.com/user-attachments/assets/dec75e3f-11ce-43db-9815-d2151bccebab" />

<img width="822" height="450" alt="image" src="https://github.com/user-attachments/assets/367955d1-fdb5-4fbe-99c1-760d383def56" />

<img width="837" height="463" alt="image" src="https://github.com/user-attachments/assets/b3e7ab1c-df5e-4cb4-b4cd-6cf45db192bd" />

<img width="831" height="458" alt="image" src="https://github.com/user-attachments/assets/2e441cc0-3f32-41c8-9a23-c327bd70b810" />

<img width="832" height="436" alt="image" src="https://github.com/user-attachments/assets/dd936b55-338a-46be-a703-bc707ae72a93" />




















































































