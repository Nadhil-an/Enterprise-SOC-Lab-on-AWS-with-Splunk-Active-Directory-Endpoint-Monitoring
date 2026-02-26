## 🏗 VPC Configuration Diagram

<p align="center">
  <img src="vpc-configuration.png" width="800">
</p>


Day 1 – Custom VPC & Subnet Setup on AWS
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
🎯 Objective

Create an isolated cloud network environment to deploy the Enterprise SOC Lab infrastructure.

## 🏗 Architecture Overview
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
```
Internet
   ↓
Internet Gateway (SOC-IGW)
   ↓
SOC-VPC (10.0.0.0/16)
   └── SOC-Public-Subnet (10.0.1.0/24)
```
1️⃣ Step 1 – Create Custom VPC
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
1.1 Navigate

AWS Console → VPC → Create VPC

1.2 Select

Choose VPC Only

1.3 Configuration

| Setting         | Value       |
| --------------- | ----------- |
| Name            | SOC-VPC     |
| IPv4 CIDR Block | 10.0.0.0/16 |
| IPv6            | None        |
| Tenancy         | Default     |

Click Create VPC

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
📌 Explanation

10.0.0.0/16 provides 65,536 IP addresses

Ensures scalability for multiple SOC lab components

2️⃣ Step 2 – Create Public Subnet
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
2.1 Navigate

VPC → Subnets → Create Subnet

2.2 Configuration
| Setting           | Value             |
| ----------------- | ----------------- |
| VPC               | SOC-VPC           |
| Subnet Name       | SOC-Public-Subnet |
| Availability Zone | Any               |
| IPv4 CIDR Block   | 10.0.1.0/24       |

Click Create Subnet

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
📌 Explanation

10.0.1.0/24 provides 256 IP addresses

Used to host:

Active Directory Server

Endpoint Machine

Web Server

Splunk Server

3️⃣ Step 3 – Enable Internet Access
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Without this step, EC2 instances cannot access the internet.

3.1 Create Internet Gateway

VPC → Internet Gateways → Create Internet Gateway

Name: SOC-IGW

3.2 Attach Internet Gateway

Select SOC-IGW → Attach to VPC → Choose SOC-VPC

4️⃣ Step 4 – Configure Route Table
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
4.1 Add Internet Route

VPC → Route Tables → Edit Routes

| Destination | Target                     |
| ----------- | -------------------------- |
| 0.0.0.0/0   | Internet Gateway (SOC-IGW) |

4.2 Associate Subnet

Route Table → Subnet Associations → Select SOC-Public-Subnet

5️⃣ Step 5 – Enable Auto-Assign Public IP
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Subnets → SOC-Public-Subnet → Edit Subnet Settings

✔ Enable Auto-assign public IPv4 address


## ✅ Infrastructure Achieved

- ✔ Created isolated AWS VPC  
- ✔ Designed custom IP address range  
- ✔ Created public subnet  
- ✔ Enabled internet connectivity  
- ✔ Configured routing  
- ✔ Prepared environment for EC2 deployment  



## 🧠 Why This Is Important for SOC Lab

- Simulates real enterprise cloud infrastructure  
- Enables log collection from multiple systems  
- Forms foundation for:

  - Active Directory  
  - Endpoint Monitoring  
  - Splunk SIEM  

