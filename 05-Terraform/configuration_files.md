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