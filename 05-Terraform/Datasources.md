In Terraform, we can use of resources that are created outside of terraform. For example, we may want to use the contents of a text file which was created using terminal commands outside the terraform process. In such cases, we can use data block.

```hcl

resource "local_file" "pet" {
    filename = "/root/pet.txt
    content = data.local_file.dog.content

}

data "local_file" "dog" {
    filename = "/root/dog.txt" # Dog.txt not created by terraform
}
```
Note that data sources can only reads infrastructure. They can not, as resource blocks, create or destroy infrastructure.
