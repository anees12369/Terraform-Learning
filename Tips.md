# **Essential Tips for Learning and Using Terraform**

1. **Use the Terraform docs** → Learn from the official HashiCorp docs to understand what Terraform is, use cases, and adoption phases.

2. **Rely on the Terraform Registry** → Daily reference for cloud provider docs (like AWS) and resources needed for deployments.

3. **Test and validate** → Always check `terraform plan` and `terraform validate` to avoid breaking production resources, when configuring your IaC in a prod environment 

4. **Start small (MVP)** → Begin with the simplest working resource, then iterate by adding variables, modules, etc.

5. **Follow DRY principle** → Don’t repeat code; use modules and reusable patterns to keep Terraform clean and efficient.