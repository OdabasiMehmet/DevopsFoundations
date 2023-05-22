#  Imperative vs Declarative Methods

In Kubernetes, we can create objects in two different ways. The declarative method only indicates the end product and does not provide step by step commands on how to create the end product. Imperative method, on the other hand includes the commands.

For the declarative method, we use YAML (Yet Another Markup Language) files to present the configuration of what we desire to be the end product.

For imperative method, we simply use a terminal, such as bash, to convey the commands.

# Example: Pods

In order to create a pod in an imperative way, we use `kubectl run` command with some options. 

```bash
kubectl run mypod --image=nginx --restart=Never
```

This will create a pod with the nginx image which will not be restarted if the pod is somehow terminated.

On the other hand, in order to create a pod using a declarative method, we need to create a yaml file and prepare a template. We cab find out what information is needed to be in the yaml file with the `kubectl explain pods`command. The necessary fields are apiVersion, kind, metadata, spec, and status.

The first step is to create a yaml file
```bash
vi  mypod.yaml
```

Then we can enter the following information

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-pod
spec:
  containers:
  - name: my-container
    image: nginx
```

This will create a pod with the image nginx that will have a pod name of my-pod and container name of my-container. (We could also add restart policy as we did in the imperative command above.)

# How to retrive information regarding objects

You can get information about objects by `kubectl get `command

```bash
kubectl get pods
kubectl get deployments
```