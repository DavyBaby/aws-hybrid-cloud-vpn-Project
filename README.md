# Hybrid Cloud with AWS VPC and On-Premises VPN Integration

## Overview
This project demonstrates a **Hybrid Cloud Architecture** connecting an **AWS VPC** with an **on-premises network** through **Site-to-Site VPN** and **AWS Direct Connect**. The architecture is designed for secure, private connectivity between AWS resources and an on-premises environment, simulating a real-world hybrid cloud solution.

## Architecture Diagram
![AWS Hybrid Cloud Diagram]([https://github.com/DavyBaby/aws-hybrid-cloud-vpn-Project/blob/58249132554093790c58674b1df789dee23b41b6/Hybrid%20Cloud%20with%20VPN.drawio.png))

## Components
- **AWS VPC (Virtual Private Cloud)**: A dedicated network within AWS configured with both public and private subnets.
- **Private Subnet**: Contains resources like an EC2 instance that is accessible from the on-premises network.
- **Virtual Private Gateway**: Allows secure connectivity from the AWS VPC to on-premises resources via Site-to-Site VPN.
- **Direct Connect Gateway**: Provides a dedicated, private connection to the on-premises network.
- **On-Premises Network**: Represents the corporate network environment, connected to AWS through a router/firewall.

## Project Objectives
- Set up a **VPC** with private and public subnets in AWS.
- Configure a **Site-to-Site VPN** for secure connectivity to the on-premises network.
- Optionally, add an **AWS Direct Connect** link for high-speed, low-latency connectivity.
- Test connectivity by accessing an EC2 instance in the private subnet from the on-premises network.

## Prerequisites
- An **AWS Account** with permissions to create VPC, VPN, and Direct Connect resources.
- **VPN-capable router or firewall** on the on-premises side.
- Basic knowledge of networking concepts, including subnets, CIDR blocks, and routing.

## CloudFormation Stack Deployment
To simplify deployment, a CloudFormation template is provided to create the essential components of this architecture.

### CloudFormation Template File
- [aws-hybrid-cloud-vpc.yml]([aws-hybrid-cloud-vpc.yml](https://github.com/DavyBaby/aws-hybrid-cloud-vpn-Project/blob/feb80e406f945d9cd98af749828f1ca20cf5fa8e/aws-hybrid-cloud-vpc.yml)): This template creates a VPC with public and private subnets, a Virtual Private Gateway, and an EC2 instance in the private subnet for connectivity testing.

### Deployment Instructions
1. **Download the CloudFormation Template**: The template file is available in this repository as `aws-hybrid-cloud-vpc.yml`.
2. **Deploy the Stack**: You can deploy this template using the AWS Management Console or AWS CLI.

#### Deploy with AWS Management Console
- Go to the **CloudFormation Console** in AWS.
- Choose **Create Stack** and select **Upload a template file**.
- Upload `aws-hybrid-cloud-vpc.yml` from this repository.
- Follow the prompts to set parameters and deploy the stack.

#### Deploy with AWS CLI
If you prefer to use the CLI, you can deploy the stack with the following command:
```bash
aws cloudformation create-stack --stack-name HybridCloudStack --template-body file://aws-hybrid-cloud-vpc.yml
