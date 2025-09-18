# **Safely Removing Infrastructure**

- **Purpose:** Safely and efficiently removes **all** infrastructure managed by Terraform.

**How it works:**
---
- Reads the **configuration and state file** to identify managed resources.

- Generates a destruction plan (like plan, but for deletions).

- Prompts for confirmation before proceeding (safety check).

- Destroys resources via the provider and updates the state file.

- **Key point:** Opposite of terraform apply — used to tear down infrastructure when it’s no longer needed.