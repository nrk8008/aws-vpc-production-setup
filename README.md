# AWS VPC Setup (Production-Grade)

This project sets up an AWS Virtual Private Cloud with a secure production-ready architecture using public and private subnets.


## 📸 Architecture Diagram

![image](https://github.com/user-attachments/assets/c8e2165f-b5c6-4865-b3ff-b3d1adaacd89)

## 🌐 Components
- VPC with CIDR block
- Public & Private Subnets
- Internet Gateway
- NAT Gateway
- Route Tables
- Bastion Host for secure SSH access

## 🛠 Tools Used
- AWS Console
- Terraform (optional)
- EC2, Security Groups, Elastic IPs

## 🔐 Security Best Practices
- Only Bastion host exposed via public IP
- Private subnets used for application/backend services
- Fine-grained security group rules

## 🚀 Usage
1. Launch VPC and subnets
2. Deploy bastion host
3. SSH into private instances via bastion
