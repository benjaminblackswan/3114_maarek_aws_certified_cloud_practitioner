# 171. Virtual Private Cloud (VPC)

AWS VPC allows you to launche AWS resources in a logically isolated virtual network that you've defined. 

<img width="575" height="353" alt="image" src="https://github.com/user-attachments/assets/4c89bd2b-46b8-4539-8f0d-76f75ced9cff" />

# 172. IP Addresses in AWS

* IPv4
  - Public
    - Can be used on the internet
    - EC2 gets a new public IPv4 every time it start or restart
  - Private
    - can be used on private networks
    - is fixed for EC2
* Elastic IP: attaches fixed public IPv4 Address to EC2 instance.

* IPv6
  - a lot more address than IPv4
  - all IPv6 address are public
  - they are free

# 173. VPC, Subnet, Internet Gateway & NAT Gateways

* Deploy a VPC, inside the VPC there is a public subnet and a private subnet.
* To define access to the internet and between subnets, we use **Route Table**

<img width="209" height="464" alt="image" src="https://github.com/user-attachments/assets/11d6f0e5-38ee-4a73-853f-747e784ea472" />

### a more complete VPC Diagram

<img width="446" height="426" alt="image" src="https://github.com/user-attachments/assets/55a746fc-ce00-408d-8805-e17d642b71fc" />

## Internet gateway and NAT gateway

<img width="292" height="457" alt="image" src="https://github.com/user-attachments/assets/df7de455-33a6-4132-a77b-2d6f856fc25a" />

## VPC hands on

LP > Your VPCs

<img width="1373" height="74" alt="image" src="https://github.com/user-attachments/assets/ef45cedc-b059-4154-9d4a-ae085abefd39" />

As you can see, we already have a VPC available for us. **AWS automatically provides a default VPC for every new account in each region.**

In this case, our **default VPC** ID is `vpc-095bddb93cc96d0a3`, IP4 CIDR is 172.31.0.0/16, which has 65,536 ip address available.

select the VPC and go to CIDRs tab

<img width="1187" height="227" alt="image" src="https://github.com/user-attachments/assets/4713c497-8c72-46ec-b9e4-da5f3933d6e0" />

you can edit the CIDR if you want to add more ip addresses.

<img width="1725" height="487" alt="image" src="https://github.com/user-attachments/assets/00e7336c-487a-4ece-8a04-140b7a928533" />

go to LP > Subnets, and you will see we already have three subnets

<img width="1491" height="211" alt="image" src="https://github.com/user-attachments/assets/1770a47b-6215-4dd8-b3c4-c158b5e7a196" />

each subnet has 172.31.0.0/20 CIDR, meaning that each subnet has 4,096 available ip addresses

move to the right, you see AWs says we have 4091 available address, and each subnet has a different AZ 

<img width="732" height="134" alt="image" src="https://github.com/user-attachments/assets/6536b22e-60c4-4a05-8111-6994323ee7d5" />

creating a new EC2

When we create a new EC2, you can see that the only (default) VPC is already selected, and there are three subnets corresponding previously.

<img width="782" height="475" alt="image" src="https://github.com/user-attachments/assets/f622f807-772a-48e7-813c-dc435843f472" />

Note the private IPv4 of the EC2 is 172.31.31.143 and that the AZ is ap-northeast-1d

<img width="1189" height="676" alt="image" src="https://github.com/user-attachments/assets/e9a60941-f902-4a42-8332-9b9dbe22856b" />


Now go back to subnets in VPC, you see that number of address is 4091 -1 = 4090 for ap-northeast-1d

<img width="532" height="153" alt="image" src="https://github.com/user-attachments/assets/2c1db8ad-c3f9-4e7c-86e5-5c6e2acc0f08" />



# 175. Security Groups & Network Access Control List (NACL)

<img width="529" height="480" alt="image" src="https://github.com/user-attachments/assets/4029fd4b-ab17-49e9-874c-1bf90c2295b5" />

* NACL is at the subnet level, which SG is at the EC2 level
* Both NACLs and SGs can be found in VPC console > LP > Security.

# 176.1 VPC Flow Logs
* VPC flow logs capture information about IP traffic going into your interfaces.

# 176.2 VPC Peering
* VPC peering connects two VPC

<img width="400" height="358" alt="image" src="https://github.com/user-attachments/assets/990ff684-7e45-48ab-ba6e-9ebee3e1c6bf" />



# 177. VPC Endpoints - Interface & Gateway (S3 & DynamoDB)

Endpoints allows you to connect to AWS services using private network

<img width="367" height="510" alt="image" src="https://github.com/user-attachments/assets/3525d371-fa47-4850-9a9e-a2e3eb4316db" />


# 178. PrivateLink

Used to expose service to 1000s of other VPCs

<img width="447" height="247" alt="image" src="https://github.com/user-attachments/assets/e88b6e37-6398-4c92-909e-7f774b0547e7" />


# 179. Direct Connect & Site-to-Site VPN

There are two options to connect on-prem dc to AWS VPC
* site to site VPN
  - goes over public internet
  - <img width="300" height="270" alt="image" src="https://github.com/user-attachments/assets/2c97e04b-106e-43b6-b134-bc1b6a35d52c" />

* Direct Connect (DX)
  - physical connection between on-prem and AWS
  - does not go through public internet, ie more secure
  - <img width="293" height="293" alt="image" src="https://github.com/user-attachments/assets/a3ab525d-50b3-488a-afb9-267dd89bb525" />


## Site to site VPN

<img width="606" height="211" alt="image" src="https://github.com/user-attachments/assets/063a984a-2378-4041-ab62-9ea40c4dba41" />


# 180. AWS Client VPN

* Connect from your computer to your AWS VPC using OpenVPN
* allow connection via private IPv4

<img width="446" height="176" alt="image" src="https://github.com/user-attachments/assets/7eefb8df-fa00-4f88-8535-7c35791e8cab" />


# 181. Transit Gateway Overview

<img width="230" height="325" alt="image" src="https://github.com/user-attachments/assets/9ccf42f3-84a3-44ed-ab1c-7c054a584320" />

# VPC & Networking Quiz

<img width="856" height="492" alt="image" src="https://github.com/user-attachments/assets/52c4b2dd-9762-4c8e-b986-bcf5b893c665" />

<img width="835" height="373" alt="image" src="https://github.com/user-attachments/assets/1cf54f23-0323-4412-beb0-6be09413afe5" />

<img width="855" height="460" alt="image" src="https://github.com/user-attachments/assets/b0f8cbe5-d0e3-4177-aa56-444e952ad8ac" />

<img width="824" height="453" alt="image" src="https://github.com/user-attachments/assets/8aeb469e-b1c4-4cfb-a4b5-0e2cebe08c69" />

<img width="830" height="439" alt="image" src="https://github.com/user-attachments/assets/8dd89902-e1fe-4ff0-a9b6-ea554dad585a" />

<img width="827" height="503" alt="image" src="https://github.com/user-attachments/assets/94bc9bb2-5b7e-4c8e-9c26-9a161e0206cf" />

<img width="837" height="488" alt="image" src="https://github.com/user-attachments/assets/9c63c4b6-4a08-4771-8eb3-49b94c02e26f" />

<img width="832" height="470" alt="image" src="https://github.com/user-attachments/assets/c99721eb-608c-4730-a7c4-98b6c4701172" />
