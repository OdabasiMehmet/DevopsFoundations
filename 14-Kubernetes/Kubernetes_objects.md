# Pods

In Kubernetes, containerized applications are organized into logical units called pods. A pod is the smallest and simplest unit in the Kubernetes object model that you create or deploy.
A pod represents a single instance of a running process in your cluster. A pod contains one or more containers, and all of the containers in a pod share the same network namespace, meaning they can all communicate with each other using localhost.

Pods provide a way to package one or more containers together and treat them as a single, atomic deployment unit. This makes it easy to manage and scale containerized applications, as well as to update them with zero downtime. Pods are also ephemeral, meaning that if a pod crashes or is deleted, it will be automatically replaced by a new pod.

* Check the pod.yaml file within this directory to see a simple pod definition file that defines a single Pod named my-pod running a single container named my-container that uses the nginx Docker image. 
