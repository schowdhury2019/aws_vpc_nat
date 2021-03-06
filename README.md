# AWS Networking

Creating VPC, Internet Gateway, Subnets, Routing Tables:
https://github.com/schowdhury2019/eng99CloudAWS/blob/main/README2.md

## VPC

### Summary of VPC

*NAT AMI*: `amzn-ami-vpc-nat-2018.03.0.20200918.0-x86_64-ebs - ami-01ae0e01e7fffd105`
*Locate in community marketplace

- 3 Route Table: Public, Private, NAT
- 3 Instances: App Instance (Public Subnet), Database Instance (Private Subnet), NAT Instance (NAT Subnet)
- VPC CIDR Block:   `10.10.0.0/16`
- Public Subnet:    `10.10.1.0/24`
- Private Subnet:   `10.10.2.0/24`
- Nat Subnet:       `10.10.3.0/24`

![image](https://user-images.githubusercontent.com/14828358/145205489-bd25f4ff-4ff2-4401-8b5b-cc775ba8fcc6.png)




# Public Subnet Routing Table
![image](https://user-images.githubusercontent.com/14828358/145218187-fad663a1-bd5a-4ce0-a507-124316d5d344.png)


- Only public routing table is linked to internet gateway


# Private Subnet Routing Table
![image](https://user-images.githubusercontent.com/14828358/145218403-bd26be54-6538-401d-a28b-553420117750.png)
- Routing ICMP/internet traffic through nat instance `eni-0e697b1974e6d91c1`

# NAT Subnet Routing Table

![image](https://user-images.githubusercontent.com/14828358/145218635-8ac6a7e8-06bd-4125-b4d1-9cf7febf19db.png)




# App Security Group

![image](https://user-images.githubusercontent.com/14828358/145219247-835e3e89-01b8-4bc0-9a49-fe74ee45eb3d.png)


# DB Security Group

![image](https://user-images.githubusercontent.com/14828358/145219501-8a8087a0-f83f-4229-90f4-f332d96c5d5b.png)

- Any TCP or ssh Requests from the public subnets can come through
- ICMP to be trafficed from any address and is streamed through the nat instance


# NAT Security Group

![image](https://user-images.githubusercontent.com/14828358/145219709-4d7d5955-34eb-4ad1-b8ca-42b84c2a5be3.png)

![image](https://user-images.githubusercontent.com/14828358/145214923-ff16ff7c-510e-454a-9a51-553edce27428.png)

- Source / destination checking is performed by your EC2 instance by default
- Stop source / destination checking if you want to allow your instance to handle network traffic that isn???t specifically destined for it
- Otherwise you can't ping from DB instance

![image](https://user-images.githubusercontent.com/14828358/145214954-d1e9558d-d2c5-4e11-9442-b1f0870e235e.png)
