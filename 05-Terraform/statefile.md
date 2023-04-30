Terraform stores the state of the infrastructure and configuration. This state is used by terraform to map real world infrastructure to your configuration and keep track of the metadata.
Terraform state file is located in the configuration directory by default. However, we can store the state file on a remote location, such as an S3 bucket in AWS. Due too having sensitive information, it is not recommended to save state file in version control repos, such as github.
The state file is stored as a jason file and named terraform.tfstate by default.
The state is first created when we run the terraform apply command. Before that, there is no terraform state file. In order to see the details of the tfsate, we can use `terraform show`command.

Having the state file in a remote location may bring a problem in terms of managing infrastructure. What happens if two members of a team want to modify the state file at the same time?

Well, terraform offers a state locking which prevents users from running terraform processes until the end of the ongoing process. In such cases, Terraform will provide an error stating that the resource is temporarily unavaiable. Because terraform acquires a state lock to protect the state from being written by multiple users at the same time.

Version control systems, such as Github does not support state locking system. Also, when developers use version control systems to clone  the state file, they may experience problems if they do not pull the latest version of the state before committing a change.

## Remote backend

Terraform offers a remote backend option through providers, such as AWS S3, Hashicorp Consul, Google Cloud Storage and Terraform Cloud.

When we make use of the remote backend, terraform will automatically pull the latest version of the state file from the shared remote backend whenever it is needed. Also, after each apply, the state file is uploaded to remote backend.