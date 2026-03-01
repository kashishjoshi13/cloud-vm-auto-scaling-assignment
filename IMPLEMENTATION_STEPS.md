# Step-by-Step Implementation

## Step 1: Create Launch Template
- Selected Amazon Linux 2 AMI
- Instance type: t3.micro
- Created key pair for SSH
- Attached IAM Role
- Configured Security Group

---

## Step 2: Create Auto Scaling Group
- Attached launch template
- Selected multiple Availability Zones
- Set:
  - Minimum capacity: 1
  - Maximum capacity: 3
  - Desired capacity: 1

---

## Step 3: Configure Application Load Balancer
- Internet-facing
- Listener: HTTP (Port 80)
- Created Target Group
- Attached Auto Scaling Group to Target Group

---

## Step 4: Configure Scaling Policy
- Selected Target Tracking Policy
- Metric: Average CPU Utilization
- Target value: 60%

---

## Step 5: Configure Security
Security Group Inbound Rules:
- Port 22 (SSH)
- Port 80 (HTTP)

Outbound:
- Allow all (default)

---

## Step 6: Monitoring & Verification
- Verified CPU metrics in CloudWatch
- Observed scale-out when CPU crossed 60%
- Observed scale-in when CPU dropped below threshold