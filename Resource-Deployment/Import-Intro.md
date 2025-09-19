# **Terraform Importing Introduction**

- `terraform import` lets you bring **existing cloud resources** (like EC2, S3, VPC) that **weren’t created with Terraform** under Terraform’s management.

- Useful in production environments where resources were created manually, and you don’t want to delete and recreate them.

**The process:**

1. Identify the existing resource in the cloud. (instance ID)

2. Write the **corresponding resource block** you need in your Terraform configuration **(using the registry)**

3. Then use `terraform import <instance type.name> <instance id> ` to link the resource 
- e.g. `terraform import aws_instance.Imported i-06fd5846132b148f1` 

4. Then `terraform plan/apply: there should be **no changes to your infrastructure as you are IMPORTING**

- Note: Import does not automatically generate the configuration code, you have to write it yourself.

**Example Import Block**
---
![alt text](Screenshots/image-5.png)

**or**

`terraform import` *(as mentioned above)*