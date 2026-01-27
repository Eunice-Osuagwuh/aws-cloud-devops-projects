# Project 02 – VPC Networking Fundamentals

## Project Objectives
- Designed AWS VPC architecture using [Draw.io](http://draw.io/)  
- Created a VPC and subnets in AWS manually  
- Configured route tables, internet gateway, security groups, and NACLs  
- Built a secure network foundation for future deployments  

---

## Tools Required
- AWS Account  
- AWS VPC  
- Subnets  
- Route Tables  
- Internet Gateway (IGW)  
- Security Groups (SG)  
- Network ACLs (NACLs)  
- Notion (for documentation)  
- [Draw.io](http://draw.io) (for architecture diagrams)  
- CIDR blocks

-![VPC Architecture](images-vpc/vps-architecture.png.png)
---

## Step-by-Step Implementation

### Phase I: VPC Creation
![VPC Creation](images-vpc/01-vpc-created.png)


1. Logged in to AWS Console, navigated to **VPC**, and clicked **Create VPC**.  
2. Named the VPC.  
3. Set the **IPv4 CIDR block** to `10.0.0.0/16` and created the VPC.  

**Review:** Custom, isolated network environment created for future deployments.

---

### Phase II: Subnet Creation
![Subnet Design](images-vpc/subnet-design.png)

1. Created a **public subnet**: IPv4 `10.0.1.0/24`.  
2. Created a **private subnet**: IPv4 `10.0.2.0/24`.  

**Review:** Public and private subnets separate internet-facing and internal resources.

---

### Phase III: Route Table Configuration
![Route Table](images-vpc/route-table.png)

1. Created a **Route Table** and attached it to the VPC.  
2. Associate both public and private subnets with the route table.  

**Review:** Controls traffic flow within the VPC and to external networks.

---

### Phase IV: Internet Gateway
![Internet Gateway](images-vpc/internet-gateway.png)

1. Created an Internet Gateway and attached it to the VPC.  
2. Edited the route table for the public subnet to add a route to `0.0.0.0/0` via IGW.  

**Review:** Allows secure internet access for public subnet resources.

---

### Phase V: Security Groups
![Security Groups](images-vpc/security-groups.png)

1. Created a Security Group.  
2. Add inbound rules for HTTP (80) and SSH (22).  
3. Allow all outbound traffic.  

**Review:** Provides instance-level traffic control.

---

### Phase VI: Network ACLs
![Network ACLs](images-vpc/nacl.png)

1. Created a Network ACL.  
2. Add inbound rules:  
   - Rule 100: HTTP (80), Allow, Source `0.0.0.0/0`  
   - Rule 110: SSH (22), Allow, Source `0.0.0.0/0`  
3. Add outbound rules similarly.  

**Review:** Adds subnet-level security.

---

## Key Concepts Demonstrated
- VPC architecture design  
- Separation of public and private subnets  
- Controlled internet access  
- Layered security using Security Groups and NACLs  
- AWS networking best practices  

---

## Outcome
Secure, scalable AWS networking foundation ready for future projects like EC2, Load Balancers, and Auto Scaling.  

---

## Planned Repository Structure




