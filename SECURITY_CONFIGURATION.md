# Security Configuration

## Security Group Rules

### Inbound Rules
- Port 22 (SSH) – Administrative access
- Port 80 (HTTP) – Public web traffic

### Outbound Rules
- Allow all outbound traffic (default)

---

## IAM Role Configuration
- Role attached to EC2 instances
- Temporary credentials used
- No hardcoded access keys
- Least privilege principle applied

---

## Security Best Practices Implemented
- No unnecessary open ports
- Multi-AZ deployment
- Role-based access control
- Firewall protection via Security Groups