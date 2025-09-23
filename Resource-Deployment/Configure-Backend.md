# **Configuring Terraform Backend and State Management**

**How to configure a remote state file for the backend of your Terraform configuration using an S3 bucket**
---
1. S3 bucket prepared in AWS ahead of time (must have a globally unique name).

2. In the Terraform configuration, a backend "S3" block is added to the **terraform block**

3. Initialize Terraform backend with `terraform init.`

