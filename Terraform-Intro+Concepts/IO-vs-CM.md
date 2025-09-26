# **Infra Orchestration vs Config Management**

- **Infrastructure Orchestration:** This is about **provisioning and managing resources** like servers, networks, databases, and load balancers. **Example tools:** Terraform, CloudFormation.

- **Configuration Management:** **Configuring the software and settings** on those resources once they exist. **Example tools:** Ansible, Puppet, Chef.

**For example** 
---
**Infrastructure Orchestration (Terraform)**

- You write Terraform code that says: “Give me 3 EC2 servers in AWS, Put them in this VPC, Attach a load balancer in front.”

- Terraform talks to AWS’s API and creates all of that.

- At this point, you have blank servers 

**Configuration Management (Ansible)**

- Next, Ansible connects to those servers.

- It installs Nginx, deploys your web app code, sets environment variables, and configures logging.

- Now the servers are not just empty boxes — they’re running a **ready-to-serve application.**

**Summary**
---
- **Infra Orchestration** deploys infrastructure, **configuration management** manages software on it