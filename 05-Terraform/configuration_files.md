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