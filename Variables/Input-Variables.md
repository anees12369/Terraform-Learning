# **Using and Configuring Input Variables**

- Input variables are **values that you pass into your configuration** removing the need to hardcode things like the AMI ID or instance type etc. `(refer to Input-Variables.md)`

![alt text](../Screenshots/image-7.png)

- You can define input variables to receive values from a **user, the command line, or variable files**

- More info can be found on the Terraform registry

**Variable blocks**
---
- A **variable block** has the keyword `variable` at the start and is followed by a label, **which is the name of your variable**

- When referencing variables, you will be calling them by **var.whatever you have named them** e.g. `var.instance_type`

- So you need to ensure that you don't duplicate or repeat things.

- Its **best practice** to define variables in a `variables.tf` file.

```bash
variable "instance_type" {
  type        = string
  default = t2.micro
}

variable "ami_id"
  type = string
  default = ami-1234567
```
**`terraform.tfvars` file**
---
- Lets say we don't want to use the **default value** of a variable 

- Or we haven't assigned a default value

- The **best practice** is to use a `terraform.tfvars` to specify any explicit values/parse in variable values

- Prevents you from passing in values manually on the CLI every time

- You do this by using the variable name and assigning a value to it:

```bash
instance_type = "t3.small"
```
