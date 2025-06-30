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
  

# Create the VPC

Use the following procedure to create a VPC with a public subnet and a private subnet in two Availability Zones, and a NAT gateway in each Availability Zone.

## To create the VPC
  1. Open the Amazon VPC console at https://console.aws.amazon.com/vpc/.

  2. On the dashboard, choose Create VPC.

  3. For Resources to create, choose VPC and more.

  ## Configure the VPC

    For Name tag auto-generation, enter a name for the VPC.
    
    For IPv4 CIDR block, you can keep the default suggestion, or alternatively you can enter the CIDR block required by your application or network.
    
    If your application communicates by using IPv6 addresses, choose IPv6 CIDR block, Amazon-provided IPv6 CIDR block.

  ## Configure the subnets

    For Number of Availability Zones, choose 2, so that you can launch instances in multiple Availability Zones to improve resiliency.
    
    For Number of public subnets, choose 2.
    
    For Number of private subnets, choose 2.

    You can keep the default CIDR block for the public subnet, or alternatively you can expand Customize subnet CIDR blocks and enter a CIDR block. For more information, see Subnet CIDR blocks.

4. For NAT gateways, choose 1 per AZ to improve resiliency.

5. If your application communicates by using IPv6 addresses, for Egress only internet gateway, choose Yes.

6. For VPC endpoints, if your instances must access an S3 bucket, keep the S3 Gateway default. Otherwise, instances in your private subnet can't access Amazon S3. There is no cost for this option, so you can keep the default if you might use an S3 bucket in the future. If you choose None, you can always add a gateway VPC endpoint later on.

7. For DNS options, clear Enable DNS hostnames.

8. Choose Create VPC.



## 🔐 Security Best Practices
- Only Bastion host exposed via public IP
- Private subnets used for application/backend services
- Fine-grained security group rules

## 🚀 Usage
1. Launch VPC and subnets
2. Deploy bastion host
3. SSH into private instances via bastion
