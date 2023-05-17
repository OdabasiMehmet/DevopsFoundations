Kubernetes is an open source paltform for automating the deployment, scaling, and management of containerized applications.
Containers have become very popular way to package and deploy applications, but they can be difficult to manage at scale. Kubernetes is a container orchestration tool, that helps solve this problem by providing a unified way to manage and orchestrate containers across multiple nodes and cloud environments.

* Other container orchestration tools: Docker Swarm which lacks the capabilities for complex applications and Mesos from Apache which is quite difficult to set up and get started. Kubernetes is the most popular one.
# Terminology

* Nodes: These are physical or virtual machines that run your containers
* Pods: A pod is the smallest deployable unit in the Kubernetes and represents a single instance of a running process in your cluster.
* Services: Services are abstractions that define a set of pods and provide network connectivity to them.
* Replication controllers: Replication controllers ensure that a specified number of replicas of your application are running at any given time.
* Cluster: A cluster is a set of nodes that run your applications
* Namespace: A namespace is a virtual cluster within a cluster
* Labels: Labels are key-value pairs that are attached to objects, such as pods and can be used to organize and selct subsets of objects.

# Architecture
Kubernetes architecture is based on a master-slave model where the master component manages the overall state of the cluster and the slave components execute the tasks on the worker nodes.

The master component consists of several key components, including the API server, etcd, the scheduler, and the controller manager. The API server is responsible for receiving and processing requests from clients, while etcd is a distributed key-value store that stores the state of the cluster. The scheduler is responsible for scheduling tasks to worker nodes, and the controller manager ensures that the desired state of the cluster is maintained.

The worker nodes, on the other hand, are responsible for running containers and executing tasks. Each worker node runs a kubelet agent that communicates with the master components to receive tasks to execute. The worker node also runs a container runtime, such as Docker, to run the containers.
In addition to the kubelet agent and the container runtime, each worker node also runs a Kubernetes proxy. The proxy is responsible for forwarding network traffic to the appropriate service running in the cluster.