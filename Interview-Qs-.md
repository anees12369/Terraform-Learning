# **Preparing for Terraform Interviews**

**Foundational Questions**
---
**1. What is Terraform? How does it work?**

- Open-source IaC tool developed by HashiCorp - allows you to **define, provision, and manage infrastructure** in a **cloud-agnostic way** across different providers like **AWS, Azure, and GCP**. 

- It works by taking the configuration files you write and compares the **desired state against the current state** of infrastructure. 

- Then, **Terraform plans and applies** changes to match the two. 

- One of Terraform’s strengths is that it’s **idempotent**, meaning Terraform only makes changes when something is different. If nothing has changed, it leaves things as they are.

**2. What are the benefits of (IaC)?**

- IaC brings **consistency, repeatability, and automation** to infrastructure management. 

- Instead of manual provisioning, infrastructure can be **version-controlled** just like application code. 

- This reduces **human error, enables faster deployments, and ensures reproducibility** across environments. It also improves collaboration, since multiple engineers can work on the same codebase safely.

**3. What is a Terraform provider?**

- A plugin that enables Terraform **to interact with APIs of different platforms and services.** 

- For example, the AWS provider lets Terraform manage AWS resources by **translating configuration into API calls.** 

- Acts as the bridge between Terraform and the underlying platform.

**Core Terraform Commands**
---

**4. Difference between terraform plan and terraform apply?**

- `terraform plan` shows the execution plan — it compares the desired state vs the current state stored in the state file, then outputs the actions Terraform would take. 

- However, `terraform apply` takes that plan and actually performs those changes to provision or modify infrastructure. 

- `plan` tells you what will happen and `apply` makes it happen.

**5. Difference between terraform init and terraform import?**

- `terraform init` initializes a working directory with Terraform configuration files, **downloads the necessary providers, sets up backends if defined, and prepares any modules** for use. (The first step you need before running plan or apply)

- However, `terraform import` is used to bring **existing infrastructure that wasn’t originally created by Terraform under Terraform’s management.** e.g. if a company has manually created resources in AWS, instead of tearing them down and redeploying, you can import them into Terraform - useful in production to avoid downtime and save costs.

**7. What is the purpose of terraform refresh?**

- Updates the state file to reflect the real-world infrastructure. **If something was changed outside of Terraform**, running refresh ensures Terraform knows the **actual current state** ensures future `plans` and `applies` are accurate.

**Terraform State & Backends**
---
**8. Explain the role of state in Terraform.**

- It's how Terraform tracks the resources it manages. It’s essentially **a blueprint that maps your configuration to actual infrastructure.**

- Without state, Terraform wouldn’t know what already exists and what needs to be changed. State is critical for detecting drift, planning updates, and ensuring idempotency.

**9. What is the purpose of a backend in Terraform?**

- Defines **where Terraform’s state file is stored** and how operations like apply are executed. 

- By default, Terraform uses a local backend. But for team collaboration, you’d typically use a remote backend like S3, GCS, or Terraform Cloud. Remote backends **allow versioning, state locking, and prevent conflicts when multiple engineers work together**

**10. Have you worked with remote state management?**

- Yes, remote state management is important in production environments where teams collaborate. 

- For example, using AWS S3 as a backend to store the state file, combined with DynamoDB for state locking, ensures that multiple people can’t apply conflicting changes at the same time. This prevents race conditions and keeps the infrastructure consistent.

**Security & Best Practices**
---
**11. How do you manage sensitive data in Terraform?**

- Sensitive data such as API keys and passwords **should never be hardcoded** in Terraform files. 

- A best practice is to use **environment variables/dedicated secret managers** like AWS Secrets Manager or HashiCorp Vault. -

- Additionally, if using a remote backend, you should ensure the **state file is encrypted** since it can contain sensitive values.

**12. How do you ensure your Terraform code is maintainable and scalable?**

- I make sure my Terraform code has **modularity** by breaking down infrastructure into **very specific, reusable modules**. 

- I use **variable files to keep configurations flexible,** and I apply consistent naming conventions. All code is version-controlled in Git, and I maintain documentation for both the modules and the overall architecture. 

- In larger environments, we also use CI/CD pipelines to validate and apply Terraform automatically.

**Competency / Behavioral**
---
**13. Describe a challenging problem you encountered with Terraform and how you solved it.**
(can answer properly once done project)

- *Talk about projects you worked on - Share your screen. Go through code that you've deployed, saying what problems and blockers you experienced and how you went about resolving - Being able to explain code and digest it simply.*

- In one project, I inherited infrastructure that had been manually created in AWS. The challenge was to bring it under Terraform without downtime. 

- I used `terraform import` to map existing resources into our configuration files. 

- I then validated the state and configuration to avoid drift. This allowed us to adopt IAC practices without disrupting production.

**14. Explain Terraform in a production environment.**

- In production, Terraform needs to be **secure, collaborative, and reliable.** 

- Which means: **Using a remote backend with locking, integrating secret management, and automating workflows through CI/CD.** 

- It also means structuring code into reusable modules, versioning providers, and enforcing reviews before applies. All of these practices help teams safely manage infrastructure at scale.