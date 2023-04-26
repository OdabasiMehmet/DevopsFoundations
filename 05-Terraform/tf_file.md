It is a good practice to create a terraform directory and create tf files inside that directory

```bash
mkdir terraform-local
cd terraform-local
```

Now, let's create a simple local.tf file

```hcl
resource "local_file" "pet" {
  filename = "/pets.txt"
  content = "We love pets!"
}

```
## Breakdown of the above code
Block name: resource
Provider name: local
Resource name: pet
Resource type: local_file # before the underscore is provider, after the underscore is the type of resource
filename and content are arguments in key value pairs

Below is an example for an AWS Ec2 instance

```hcl
resource "aws_instance" "webserver" {
  ami = "ami-0c2f25c1f66a1ff4d"
  instance_type = "t2.micro"
}
```
## Commands to execute
```bash
terraform init # backend is initialized. Provider plugin initialized.
terraform plan # plus symbols shows the resources to be created
terraform apply # will need to confirm
```

## To see the details of the created resources

```bash
terraform show
```

## Update the code

Just modify the .tf file

```hcl
resource "local_file" "pet" {
  filename = "/pets.txt"
  content = "We love pets!"
  file_permission = "0700"
  } 
  ```
```bash
terrraform apply # type yes to confirm
```

## Delete the resource

```bash
terrraform destroy # type yes to confirm
```