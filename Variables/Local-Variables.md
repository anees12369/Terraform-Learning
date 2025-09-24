# **Using Local Variables in Terraform**

- **Local variables** = Used for when you want to **simplify code internally**, allows for **consistency and reducing repetition** (tags, name formats, constants).

- Their main job is to make your code **cleaner, shorter, and easier to maintain**

**Example**
---
- You can assign local variables in a `variables.tf` file

**Without local variables:**

```bash
resource "aws_instance" "one" {
  ami           = "ami-12345678"
  instance_type = "t2.micro"
  tags = {
    Project = "MyApp"
    Owner   = "TeamA"
  }
}
```
**With local variables**
```bash
locals {
  common_tags = {
    Project = "MyApp"
    Owner   = "TeamA"
  }
}

resource "aws_instance" "one" {
  ami           = "ami-12345678"
  instance_type = "t2.micro"
  tags          = local.common_tags
}
```
**Simpler example:**
---
```bash
locals {
  instance_ami = "ami_1234567
}
```
**Differences**
---

- 👉 Input variables = flexible values you **pass in** (e.g. through a `.tfvar` file ).

- 👉 Local variables = helper values you compute once and reuse everywhere, a **consistent value** 