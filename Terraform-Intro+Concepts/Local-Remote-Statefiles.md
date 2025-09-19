# **Understanding Local and Remote State Files**

**Local State Files**
---
- By default, Terraform stores the state file locally in the project directory.

- **Easy setup:** no extra configuration needed.

- **Best for single-user projects:** avoids conflicts since only one person manages the infrastructure.

- **Simple and contained:** no external inputs or changes to worry about.

**Remote State Files**
---
- **Centralized storage:** Keeps the state file in a secure, shared location.

- **Collaboration friendly:** Multiple team members can work on the same infrastructure without conflicts.

- **Automatic State locking:** Prevents making change at the same time and reduces corruption risks (e.g., with S3 or Terraform Cloud).

- **Backups & security:** Remote backends handle automatic backups and encryption, making the state both **secure and recoverable**.

- A **remote backend** is a storage system (outside your local machine) where Terraform keeps its state file. e.g. S3 buckets, Terraform Cloud.