# Create a Terraform Plan

This repo is a companion repo to the [Create a Terraform Plan](https://developer.hashicorp.com/terraform/tutorials/cli/plan) tutorial.
It contains Terraform configuration you can use to learn how Terraform generates an execution plan.

# Files and Folders to Exclude from Version Control

**Terraform State Files:**
terraform.tfstate: This file contains the current state of your infrastructure and can include sensitive information like passwords, private keys, and other secrets.
terraform.tfstate.backup: A backup of the state file, which also contains sensitive information.
.terraform directory: This directory contains the cached provider plugins and other state-related information. It is not necessary to version control this directory, and it can also contain sensitive data.

**Terraform Variable Files:**
*.tfvars: These files often contain values for your variables, including sensitive information like passwords, API keys, and other secrets.
*.tfvars.json: Similar to *.tfvars files, these JSON files can contain sensitive variable values.
Terraform Configuration Overrides:

override.tf and override.tf.json: These files are used for local overrides and should not be version controlled as they can contain environment-specific configurations.
*_override.tf and *_override.tf.json: Similar to override.tf, these files can contain sensitive and local-specific configurations.

**Managing Sensitive Information**
To manage sensitive information effectively in Terraform, consider using the following practices:

Environment Variables: Use environment variables to pass sensitive information to your Terraform configuration instead of storing it in files.

Secrets Management Tools: Use tools like HashiCorp Vault, AWS Secrets Manager, or Azure Key Vault to securely manage and retrieve sensitive information during Terraform runs.

Terraform Backend: Use a remote backend (like Terraform Cloud, AWS S3, or others) to securely store your state files. This also allows for better collaboration and state locking.

.gitignore: Add sensitive files and directories to your .gitignore file to ensure they are not accidentally committed to your VCS.

**Example .gitignore File**
Here’s an example .gitignore file for a Terraform project:

gitignore
Copy code
# Terraform state files
terraform.tfstate
terraform.tfstate.backup

# Terraform variable files
*.tfvars
*.tfvars.json

# Local override files
override.tf
override.tf.json
*_override.tf
*_override.tf.json

# .terraform directory
.terraform/
.terraform.lock.hcl

# Crash log files
crash.log

# Sensitive files (examples)
secret.tfvars
private.key

# Ignore system-specific files
.DS_Store
Thumbs.db
