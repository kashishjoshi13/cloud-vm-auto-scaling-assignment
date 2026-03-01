# Architecture Design

## Components

1. User / Internet
2. Application Load Balancer (HTTP – Port 80)
3. Auto Scaling Group (Min=1, Max=3, Target CPU=60%)
4. EC2 Instances (t3.micro) in multiple Availability Zones
5. Amazon CloudWatch for monitoring
6. Security Group (Ports 22 and 80)
7. IAM Role with least privilege access

---

## Traffic Flow

User → Application Load Balancer → EC2 Instances

The ALB distributes incoming HTTP traffic across available EC2 instances in different Availability Zones.

---

## Scaling Flow

EC2 Instances → CloudWatch monitors CPU Utilization  

If CPU > 60% → Auto Scaling Group adds new instance (Scale Out)  

If CPU < 60% → Auto Scaling Group removes extra instance (Scale In)

---

## Security Flow

EC2 instances are protected by:
- Security Group firewall rules
- IAM Role for controlled AWS service access

---

## High Availability

Instances are deployed across multiple Availability Zones to ensure fault tolerance.  
If one Availability Zone fails, traffic is automatically routed to healthy instances in other zones.