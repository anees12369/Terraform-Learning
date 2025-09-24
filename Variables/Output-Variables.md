# **Output Variables**

**What are output variables?**
---
- Output variables in Terraform let you see important information after running `terraform apply`.

- Example: an EC2 instance ID, public IP, or any resource attribute.

**They’re useful for:**
---
- Passing data to other Terraform configs (when using modules).

- Feeding values into automation scripts/tools.

- Just for your own reference (e.g., copy-pasting the instance IP).

**Example output block**
---
```bash
output "instance_id" {
  description = "The ID of the EC2 instance"
  value       = aws_instance.example.id
}
```
- `output` → keyword.

- `instance_id` → name of the output.

- `description` → optional, but good practice.

- `value` → what you want to show (usually a resource attribute).

```bash
terraform apply


Outputs:
instance_id = "i-0bee7048a6422fa79"
```

**Best Practices**
---
1. **Use clear names** → e.g. instance_id, db_endpoint, vpc_id.

2. **Document outputs** → always add description.

3. **Expose critical info only** → things your team or automation needs.

4. **Secure sensitive outputs** → mark as sensitive = true if it’s a password, secret, or token.
