Orchestrators manage the lifecycle of containers. They  deploy and load-balance applications across multiple servers, control autoscaling to handle traffics to applications, and employ rollout and rollback operations.

While there are container orchestration tools, such as Kubernetes, Amazon offers a simple alternative to container orchestration with AWS Elastic Container Service.

ECS offers two types of launch types: EC2 and Fargate. Infrastructure is composed of virtual machines that make up clusters and ECS manages the containers inside the cluster.

* When using EC2 launch types, we are responsible for managing the underlying EC2 instances. That means, we have to create EC2 instances and install docker, ECS agent and and other software on them. However, we have full control over the cluster.
* Fargate: AWS manages the underlying infrastructure. Fargate follows a serverless architecture. There are no physical servers that we have to create. Fargate will handle them once we choose Fargate and start creating the cluster. Fargate will create resources when we need them so we only pay for what we use.