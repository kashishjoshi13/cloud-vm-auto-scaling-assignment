# Cloud VM Auto Scaling and Security Implementation

## Project Objective
This project demonstrates the deployment of a scalable cloud infrastructure using Amazon Web Services (AWS). The system automatically scales EC2 instances based on CPU utilization and applies security best practices including IAM roles and firewall rules.

---

## AWS Services Used
- Amazon EC2
- Application Load Balancer (ALB)
- Auto Scaling Group (ASG)
- Amazon CloudWatch
- IAM Roles
- Security Groups
- Virtual Private Cloud (VPC)

---

## Region
us-east-1 (N. Virginia)

---

## Instance Configuration
- AMI: Amazon Linux 2
- Instance Type: t3.micro
- Key Pair: Created for SSH access

---

## Architecture Overview

User traffic enters through an Application Load Balancer.  
The ALB distributes traffic across EC2 instances deployed in multiple Availability Zones.  
An Auto Scaling Group manages the EC2 instances and adjusts capacity based on CPU utilization.  
CloudWatch monitors performance metrics and triggers scaling actions.  
Security Groups and IAM Roles enforce security policies.

Refer to `architecture-diagram.png` for system architecture.

---

## Auto Scaling Configuration
- Minimum Instances: 1
- Maximum Instances: 3
- Desired Capacity: 1
- Scaling Policy Type: Target Tracking
- Target CPU Utilization: 60%

---

## Security Implementation
- Security Group allowing:
  - Port 22 (SSH)
  - Port 80 (HTTP)
- IAM Role attached to EC2 instances
- Least privilege access policy applied

---

## Implementation Method
The infrastructure was configured manually using the AWS Management Console.  
This repository contains structured documentation and architecture design rather than Infrastructure-as-Code scripts.

---

## Outcome
The system successfully:
- Distributed traffic using ALB
- Automatically scaled EC2 instances
- Monitored CPU utilization via CloudWatch
- Applied IAM and firewall security controls
- Ensured high availability using Multi-AZ deployment
