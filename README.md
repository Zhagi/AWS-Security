# AWS Security Infrastructure Deployment

This repository contains Terraform configuration files for setting up AWS infrastructure. 
As a DevOps engineer, I created this project to allow the migration of on-premises applications to AWS, focusing on establishing a highly secure setup, designed to protect and manage cloud-based applications effectively. 

## Deployment Instructions

To deploy this infrastructure:

1. Navigate to each module directory (e.g., `cd modules/vpc`).
2. Initialize the Terraform environment with `terraform init`.
3. Validate the Terraform configuration with `terraform plan`.
4. Apply the Terraform configuration with `terraform apply`.

Repeat these steps for each module, following the order of dependencies when applying the configurations.

## Security Best Practices Implemented

- **IAM Least Privilege**: Each service is assigned only the permissions necessary for its function.
- **MFA for Root Account**: Multi-Factor Authentication is enabled for the root account for additional security.
- **S3 Bucket Policies**: Strict policies are in place to control access and prevent public exposure.
- **Encryption**: At-rest encryption is enabled for S3 buckets and EBS volumes.
- **CloudTrail Logging**: API call logging is enabled for tracking and auditing purposes.
- **VPC Flow Logs**: Network traffic is monitored for both the VPC and its subnets.
- **CloudWatch Alarms**: Alarms for unusual activity or unauthorised API calls are in place.

## Assumptions and Design Choices

- The infrastructure is expected to scale, so the design is modular to facilitate easy updates and changes.
- A multi-environment setup (dev, staging, production) is anticipated, although not yet implemented.
- Services are distributed across public and private subnets based on their exposure needs.


## Infrastructure Components

- **VPC**: Configured with separate public and private subnets for different levels of access and security.
- **EC2**: Instances provisioned in the private subnet with security groups limiting access.
- **IAM**: Roles and policies designed to provide services with the minimum necessary permissions.
- **S3**: Secure storage buckets for logs, encrypted and version-controlled.
- **CloudTrail**: Monitors and records account activity across the AWS infrastructure.
- **CloudWatch**: Monitoring and alerting for operational and security insights.
- **Secrets Manager**: Centralised management for sensitive information like database credentials.
- **Flow Logs**: Captures information about the IP traffic going to and from network interfaces in the VPC.


## Architecture Diagram

![AWS Architecture Diagram](https://github.com/Zhagi/AWS-Security/blob/main/Images/AWS%20Architecture%20Diagram.png?raw=true)


## Acknowledgements
You can explore this project along with others at [moabukar/tech-vault](https://github.com/moabukar/tech-vault).
