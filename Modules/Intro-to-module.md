# **Introduction to Terraform Modules**

- A Terraform Module is essentially a **collection of `.tf` (config) files in a directory** in order to serve a specific process.

- By **default**, any Terraform configuration in a folder is treated **as if it's its own Module**, often called the **Root Module**.

- To create a terraform module, you can create a folder called `modules` within your working directory, then create and name another folder based on what module will be used for 

- e.g. `./modules/ec2`

- Then you move your configuration files into that directory (`/ec2` in this example), and call the module from a `main.tf` file (in the root module), using the modules path

**Example**
---
```bash
# main.tf
module "ec2_module" {
  source = "./Modules/EC2"
}
```
**Why do we use modules?**
---
1. **Reusable** – Instead of writing the same EC2 setup (or S3, or VPC, etc.) in every project, you write it once as a module and then reuse it everywhere. 📦 Like saving a recipe so you don’t have to rewrite it every time you cook.

2. **Organization** – As infrastructure grows, keeping all the code in one file/folder **becomes messy**. Modules group related resources together in neat “packages.”

3. **Consistency** – By using the same module in dev, staging, and production, you know everything is built in the **same way with the same rules.**

4. **Collaboration** – Teams can share modules so not everyone has to write Terraform from scratch. Less experienced folks can still deploy things correctly using a standardized approach.