# **Terraform Workflow Overview**

1. `terraform init` Initializes the working directory - Downloads required providers (e.g., AWS) - Configures the backend to manage your state file.

2. `terraform validate` Checks the configuration files for syntax errors and internal consistency. Ensures your code is well-formed before planning or applying.

3. `terraform plan` Creates + shows an execution plan by comparing the **current state to the desired state in your configuration**.

4. `terraform apply` Executes the plan and applies changes to reach the desired state.Prompts for confirmation before making changes.

5. `terraform destroy` Destroys all Terraform-managed infrastructure. Prompts for confirmation before removing resources.