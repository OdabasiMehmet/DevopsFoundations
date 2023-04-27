The main configuration file in terraform is conventionally named as main.tf. Provider block and resource blocks are added into this configuration file.
For small projects, resource blocks can be hard coded however it is a good practice to use variables to provide values for resources instead of hard coding the main tf file.
## variables.tf
Variables can be listed in a separate configuration file called variables.tf. In this file, variable keyword is used followed by the name of the variable. You can also add an optional default value between curly braces.

### Example

```hcl
variable "filename" {
    default = "/roor/pets.txt"
}
variable "content" {
    default = "We love pets"
}
```

In order to make use of these variables, we enter var followed by .variable-name in the main.tf file

### Example

```hcl
resource "local_file"  "pet"{
    filename= var.filename
    contents = var.content
}

```
Once we have the variables.tf, all we need to do is to change the values in the variables.tf instead of the main.tf.

## Optional parameters in variables.tf

We can also add type as a parameter. By default, it is any type if not entered. Once we enter the types, we can make use of the variables in accordance with the type of the variables. For example, we can use a list type and enter multiple values in a single variable. Then we should add an index value to make sure that the variable takes what we really want.

### Example

```hcl
variable "prefix" {
    default = ["mr" , "mrs" ,"ms"]
    type = list
}
variable "content" {
    type = map
    default = {
        "statement1" ="We love pets"
        "statement2" ="We love birds"
    }
}
```

```hcl
resource "local_file"  "pet"{
    prefix= var.prefix[0]
    contents = var.content["statement1"]
}

```

## Other methods to use variables

We can employ variables in terraform using terraform apply followed by -var to denote variables. So by using -var followed by variables, we can point multiple variables to be used.

Another method is to create a new file with a tfvars or auto.tfvars extension. These files are automatically loaded by Terraform if the names are terraform.tfvars or *.auto.tfvars. However, if we provide another name, such as variables.tfvars, then we need to address them in the terraform apply command with a -var-file flag.

When createing the variables.tf file, we used blocks to define the variable; however, when createing auto.tfvars file, we just enter key value pairs.

Also, we can export environmet variables in the TF_VAR_variablename format.

```bash
export TF_VAR_filename = "/root/cats.txt"
```

## Precedence of variables

If we have multiple values assigned to the same variable in different files, such as variables.tf, autotf.vars, then terraform accepts the value which has the most precedence over the others.


1. Environment variables (Lowest)
2. terraform.tfvars
3. *.auto.tfvars
4. -var or -var-file (Highest)


## Using interpolation sequences in naming resources

Interpolation sequences help dynamically generate names for resources in Terraform. For example, you may use a resource, such as pet-name generator, and want to use the generated name as the name of another resource. In such cases, we use ${random_pet.my-pet.id} to name the resource.

You may wonder where that expression came from. Well, it comes from the random_pet generator below. Below code will generate an id which is a string that consists of the pet name.

```hcl
resource "random_pet""my-pet" {
    prefix = var.prefiz
}

We can use other examples for interpolation sequences. For example, you might want to create multiple instances of an EC2 instance, each with a unique name. You could use an interpolation sequence to generate a unique name for each instance:

```hcl
resource "aws_instance" "example" {
  count = 3

  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
  subnet_id     = aws_subnet.private.id
  key_name      = aws_key_pair.example.key_name
  tags = {
    Name = "example-${count.index + 1}"
  }
}
```
In this example, the tags block uses an interpolation sequence to generate a unique name for each instance. The ${count.index} interpolation references the current index of the count loop, and we add 1 to make the name more user-friendly.

When Terraform creates the resources, it will generate three instances named "example-1", "example-2", and "example-3".