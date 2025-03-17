# Terraform AWS S3 Static Website & Remote State Management

This repository contains Terraform configurations to provision:

1. **Terraform Remote State** (S3 and DynamoDB for state management)
2. **S3-Based Static Website** (with CloudFront, ACM, and Route 53 for hosting and distribution)

## 🚀 Features

### **Remote State Management**
- **S3 Bucket**: Stores Terraform state files securely.
- **DynamoDB Table**: Enables state file locking to prevent conflicts in team environments.

### **Static Website Hosting**
- **S3 Buckets**:
  - One bucket for the root domain.
  - One bucket for the `www` subdomain (redirects to the root domain).
- **ACM (AWS Certificate Manager)**:
  - Issues and manages a wildcard SSL certificate for the domain.
- **CloudFront (CDN for Content Delivery)**:
  - Distribution for the root domain.
  - Distribution for the `www` subdomain.
- **Route 53 (DNS Management)**:
  - Public hosted zone for domain management.
  - Alias records for CloudFront distributions.

## 📌 Prerequisites
Before using this Terraform module, ensure you have:

- **AWS CLI** (Tested with version 2.17.13)
- **Terraform** (Tested with version 1.9.2)
- **AWS Credentials** (Access Key & Secret Key with required permissions)
- **An AWS Account** with permissions to create S3, CloudFront, Route 53, ACM, and DynamoDB resources
- **A Registered Domain** (e.g., via Route 53, GoDaddy, Namecheap, etc.)
- **Basic AWS & Terraform Knowledge**

## 🔧 Setup Instructions
1. **Clone the Repository**:
   ```sh
   git clone <repository-url>
   cd <repository-folder>
   ```

2. **Initialize Terraform**:
   ```sh
   terraform init
   ```

3. **Plan the Deployment**:
   ```sh
   terraform plan
   ```

4. **Apply Changes**:
   ```sh
   terraform apply -auto-approve
   ```

5. **Verify Deployment**:
   - Check the S3 buckets in AWS Console.
   - Validate the CloudFront distributions.
   - Ensure the domain is correctly resolving via Route 53.

## 📜 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


Happy Terraforming! 🚀