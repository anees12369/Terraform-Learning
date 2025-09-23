# **Configuring Terraform Backend and State Management**

**How to configure a remote state file for the backend of your Terraform configuration using an S3 bucket**
---
1. S3 bucket prepared in AWS ahead of time (must have a globally unique name).

2. In the Terraform configuration, a backend "S3" block is added to the **terraform block**

3. Initialize Terraform backend with `terraform init.`

**An example of backend block:**
---
```bash
terraform {
  required_providers {
    aws = {
      source = "hashicorp/aws"
      version = "6.14.0"
    }
  }
   backend "s3" {
    bucket         = "remote-state-file-anees"   # must already exist in AWS
    key            = "terraform.tfstate"   # path inside the bucket
    region         = "eu-west-1"                   # bucket region
  }
}  
provider "aws" {
}
```

**Important**
---
- Terraform can create EC2 with hardcoded keys **in the provider block**

- But the S3 backend **ignores those keys and only uses environment variables or AWS CLI profiles for credentials:**

- `export AWS_ACCESS_KEY_ID=`
- `export AWS_SECRET_ACCESS_KEY=`
- `export AWS_DEFAULT_REGION=`

