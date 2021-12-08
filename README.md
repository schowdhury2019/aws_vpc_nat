# AWS Networking

Creating VPC, Internet Gateway, Subnets, Routing Tables:
https://github.com/schowdhury2019/eng99CloudAWS/blob/main/README2.md



*NAT AMI*: `amzn-ami-vpc-nat-2018.03.0.20200918.0-x86_64-ebs - ami-01ae0e01e7fffd105`


# Public Subnet Routing table
![image](https://user-images.githubusercontent.com/14828358/145201361-fba10e99-0bee-4d0b-bc8f-0da7b30845b6.png)

- Only public routing table is linked to internet gateway


# Private Subnet Routing table
![image](https://user-images.githubusercontent.com/14828358/145201423-6aaa33d9-275c-4ba1-a316-df4fbd1d2a5b.png)

- Routing ICMP/internet traffic through nat instance `eni-0e697b1974e6d91c1`


# App Security Group

![image](https://user-images.githubusercontent.com/14828358/145201804-82a9153e-ea0e-4ee8-ad32-1a386d96bdae.png)



# DB Security Group

![image](https://user-images.githubusercontent.com/14828358/145201896-96b2d327-fa53-42fd-be9f-3076b46ce59f.png)


- Any TCP or ssh Requests from the public subnets can come through
- ICMP to be trafficed from any address and is streamed through the nat instance



## VPC

![image](https://user-images.githubusercontent.com/14828358/145205489-bd25f4ff-4ff2-4401-8b5b-cc775ba8fcc6.png)

- VPC CIDR Block:   10.10.0.0/16
- Public Subnet:    10.10.1.0/24
- Private Subnet:   10.10.2.0/24
- Nat Subnet:       10.10.3.0/24



### 2-Tier Achitecture Deployment

**AWS Networking**

- IP addresses
- CDIR blocks
- IPV4 and IPV6

**VPC and its resources**
![](VPC Diagram)

- Route Table Rules
- SG Rules
- Subnet CIDR Blocks
- Connectivity between app and db and nad db

**2 Tier Architecture Deployment in our own VPC**
![](Diagram)

- Should have all rules at all levels
