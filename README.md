# Terraform AWS 3-Tier Infrastructure

This project provisions a basic 3-tier AWS infrastructure using Terraform, demonstrating Infrastructure as Code (IaC) principles.

## Architecture
- **VPC** with a public subnet and internet gateway
- **EC2 instance** running in the public subnet, secured via a custom security group (SSH + HTTP only)
- **S3 bucket** for application storage
- **IAM role** attached to the EC2 instance, granting least-privilege access to the S3 bucket (no hardcoded credentials)

## Files
- `provider.tf` – AWS provider configuration
- `variables.tf` – Configurable input variables (region, CIDR blocks, instance type)
- `main.tf` – Core infrastructure: VPC, subnet, routing, security group, EC2, S3
- `iam.tf` – IAM role and policy for secure EC2-to-S3 access
- `outputs.tf` – Key outputs (VPC ID, instance public IP, S3 bucket name)

## How it works
1. `terraform init` – initializes the working directory and providers
2. `terraform plan` – previews the infrastructure changes
3. `terraform apply` – provisions the resources on AWS
4. `terraform destroy` – tears down all resources when no longer needed

## Skills demonstrated
Infrastructure as Code, AWS networking (VPC/subnets/routing), security groups, IAM least-privilege access, and modular Terraform structure.
