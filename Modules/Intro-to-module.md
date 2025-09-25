# **Introduction to Terraform Modules**

- A Terraform Module is essentially a **collection of `.tf` (config) files in a directory** in order to serve a specific process.

- By **default**, any Terraform configuration in a folder is treated **as if it's its own Module**, often called the **Root Module**.

- To create a terraform module, you can create a folder called `modules` within your working directory, then create another folder specifying what the module will be used for 

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

