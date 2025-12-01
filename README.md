 # AWS CloudFormation – Production-Grade Auto-Scaling Web Farm (100% IaC)

End-to-end highly available and scalable web application deployed entirely using AWS CloudFormation.

## Architecture Highlights
- Custom VPC with public subnets across 2 Availability Zones
- Internet Gateway + Route Tables
- Application Load Balancer (ALB) with HTTP → HTTPS redirect
- Launch Template + Auto Scaling Group (Desired=3, Min=2, Max=5)
- Target Tracking Scaling Policy (ALB Request Count per Target)
- 7 CloudWatch Alarms (CPU, RequestCountPerTarget, HealthyHostCount, etc.)
- SNS Topic with email subscriptions for real-time notifications
- Security Groups with least-privilege rules
- UserData scripts that auto-install and start Apache (httpd)
- All resources created in a single stack (or modular stacks – both versions included)

## Live Demo Results (tested & working)
- Successfully triggered scale-out to 5 instances under load (PowerShell + curl stress test)
- Successfully triggered scale-in back to 2 instances when load reduced
- Received live email alerts from SNS on every scale event and health change
- ALB properly distributes traffic across all healthy targets

## Why this project stands out
- Zero manual steps after `aws cloudformation deploy`
- Proper handling of missing CloudWatch data (`TreatMissingData: breaching`)
- Real-world scaling policies (not just CPU-based)
- Complete observability with meaningful alarms
- Clean, readable, and well-commented YAML

Perfect for DevOps / Cloud Engineer interviews and portfolios.

Tech stack: AWS CloudFormation (YAML), EC2, ALB, Auto Scaling, CloudWatch, SNS, VPC, IAM
