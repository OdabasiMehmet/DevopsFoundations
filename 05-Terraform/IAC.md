## Traditional methods

In traditional infrastructure planning, you need to take into account everything when you come up with a new application or a service. This is generally done by solution architects or technical leads. By taking into account the resources needed to run the application, infrastructure must be created by placing orders through vendors. However, each time an upgrade is needed in terms of hardware, it will take some time to order and receive the new infrastructure components. Therefore, there will be time restrainsts when it comes to scale up the infrastructure. Furthermore, if the service is no longer required or the spikes are over, then the infrastructure will be useless or at least under utilized.

## Cloud services

Organizations have shifted towards virtualization and cloud services in the last decades. Cloud providers, such as AWS, Azure, and Google Cloud have been very popular in terms of providing services to organizations. By moving to cloud, time to spin up infrastructure and market applications are significantly reduced. Because, cloud providers manage the infrastructure needed to run applications and services and they are alredy there and ready for organizations' disposal.

Infrastructure management is also easier when using cloud services. Because organizations do not need to worry about how to safeguard and how to service the hardware. They do not need to worry about infrastructure failures, due to any types of problems, such as cooling issues. 

Scaling up and down the infrastrucrure is also very convenient in cloud services. It is just a matter of minutes to scale up and down infrastrurcture whenever needed.

## IOC services

Cloud providers make it very easy to spin up infrastructure through their online consoles or user interfaces. Also, all of them offer terminal tools so that users can spin up infrastructure through their terminals. However, this method is not feasible for large organizations with numerous compute resources.
At first, many organizations developed codes through programming languages, such as Python and Powershell in terms of automating this process. Throughtout time, many tools are emerged that all aim for the same purpose. We call them infrastructure as code.

The way it works is that, these tools code the entire infratsructure provisioning process. By this way, we can define and execute the code to create, update, and terminate infrastructure components. Also, the code is reusable.

Tools, suchs Terraform and Ansible are very popular in terms of provisioning and configuring infrastructure. Other prominent IAC tools are Vagrant, Packer, Puppet, Saltstack, CloudFormation and Docker.

## Types of IAC 

1. Configuration Management: Ansible, Chef, Puppet, and Saltstack

Thse tools are idempotents which means that no matter how many times you run the code, only the necessary changes are made. They keep the others as is.

2. Server Templating: Docker, packer, and Vagrant

These tools prepare images that containe pre installed software and dependencies. However, when there is a need to update the images, they have to be redeployed with the updated image. Because they are immutable.

3. Provisioning tools: Terraform and CloudFormation

These tools use a declarative code to provision infrastrcture. While CloudFormation is specific to AWS, Terraform is cloud agnostic.