# Pods

In Kubernetes, containerized applications are organized into logical units called pods. A pod is the smallest and simplest unit in the Kubernetes object model that you create or deploy.
A pod represents a single instance of a running process in your cluster. A pod contains one or more containers, and all of the containers in a pod share the same network namespace, meaning they can all communicate with each other using localhost.

Pods provide a way to package one or more containers together and treat them as a single, atomic deployment unit. This makes it easy to manage and scale containerized applications, as well as to update them with zero downtime. Pods are also ephemeral, meaning that if a pod crashes or is deleted, it will be automatically replaced by a new pod.

* Check the pod.yaml file within this directory to see a simple pod definition file that defines a single Pod named my-pod running a single container named my-container that uses the nginx Docker image. 

# Replicasets

A ReplicaSet is a Kubernetes object that is used to ensure that a specific number of replicas of a pod are running at all times. The ReplicaSet is responsible for managing the lifecycle of its replicas, creating new replicas when necessary, and removing old replicas when they are no longer needed.

When you create a ReplicaSet, you specify the number of replicas that you want to run. The ReplicaSet then monitors the state of its replicas and makes sure that the actual number of replicas matches the desired number. If a replica fails or is terminated, the ReplicaSet will automatically create a new replica to replace it.

* Check replicaset.yaml file within this directory to see a simple replicaset definition file. The ReplicaSet is named "my-replicaset" and is set to create 3 replicas of the "my-app" application. The selector is set to match any Pods with the label "app: my-app". The template specifies the Pod spec that will be used to create the replica Pods, including the container name and image. 

# Deployments

Deployments in Kubernetes are objects that manage the deployment of new versions of an application. They provide a higher-level abstraction than ReplicaSets by allowing you to declaratively manage a set of ReplicaSets, as well as the updates and rollbacks of your application.

A Deployment object specifies how many replicas of an application should be running at any given time, and provides a way to update or roll back the application to a previous version without downtime. It also allows for rolling updates, which means that new versions of an application can be gradually deployed, replacing old versions one at a time, ensuring that the application is always available to users.

* Check deployment.yaml file within this directory to see a simple deployment definition file.
```bash
apiVersion: The API version of the Deployment resource. In this case, it's apps/v1.
kind: The type of resource. In this case, it's Deployment.
metadata: Information about the resource, such as its name.
spec: The specification of the Deployment, which includes the desired number of replicas, the selector for the Pods managed by the Deployment, and the Pod template that specifies the container(s) to be run in each replica.
replicas: The desired number of replicas for the Deployment. In this example, we have specified 3 replicas.
selector: The label selector that matches the Pods managed by the Deployment. In this example, we have used the app: my-app label selector.
template: The Pod template that specifies the container(s) to be run in each replica.
metadata: Labels to be applied to the Pods created from this template.
spec: The specification for the containers in the Pod.
containers: The list of containers to be run in the Pod. In this example, we have specified only one container.
name: The name of the container.
image: The container image to be run.
ports: The list of ports to be exposed by the container. In this example, we have exposed port 80.
```