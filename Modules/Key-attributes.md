# **Key Attributes of Terraform Modules**

**What makes a good terraform module?**
---

1. **Outputs** → Modules should provide useful output values (like EC2 instance ID or public IP). This makes the module easier to use in other parts of your configuration.

2. **Documentation** → Always include a README or clear comments explaining what the module does, what inputs it expects, and what outputs it provides. Well-documented modules save time for others (and future you).

3. **Avoid hardcoding** → Don’t lock values (like instance types, regions, AMIs) inside the module. Instead, pass them in as variables so the module can be reused across different environments.

4. **Modularity** → Keep each module focused on one job. For example, a module for an EC2 instance shouldn’t also manage a database or load balancer. Smaller, focused modules are cleaner, easier to maintain, and easier to compose.

5. **Testing & Versioning** → Regularly test your modules in different environments. Use versioning so teams can safely upgrade without breaking existing infrastructure.