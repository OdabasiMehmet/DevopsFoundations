Terraform is an IAC tool which was developed by Hashicorp. It uses Hashicorp Configuration Language and can deploy infrastructure across multiple platforms.

### Terraform Providers

1. Physcial machines, virtual machines, AWS,GCP
Azure

2. Network infrastructure, such as BigIP, CloudFlare, DNS, Palo Alto, Infoblox

3. Monitoring tools, such as DataDog, Grafana, Auth0, Wavefron and Sumo Logic.

4. Database tools, such as InfluxDB, MongoDB, MySQL, PostgreSQL, VCS

* Official providers: AWS, GCP
* Partner providers: bigjp, heroku
* Community providers: active driectory, ucloud

Terraform uses a declarative approach for creating infrastructure and works in three phases to do that.

1. Init Phase: Terraform initializes the projects and identifies the providers to be used in the target environment.

2. Plan phase: Terraform drafts a plan to get to the target state.

3. Terraform makes necessary changes to make sure the real world infrastructure is the same with the desired state.

The objects that are managed by Terraform are called resources. So the tf files are consisted of resources and providers blocks. Terraform can also import infrastructure which was created outside of terraform.