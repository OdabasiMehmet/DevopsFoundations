Terraform recommends usage of provisioners as a last resort because they may make the configuration more complex. Instead of provisioners, we can use the following native options for cloud providers.

* AWS = user_data for aws_instance
* Azure = custom_data for azurrerm_virtual_machine
* GCP = meta_data for google_compute_instance

Another option is to use amis that alraedy has what we need to install. For example, instead of using a regular ami and then trying to install nginx, we can use an ami that already has nginx (custom ami).