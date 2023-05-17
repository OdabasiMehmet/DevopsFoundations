## Virtualization
The best way to understand Docker and containerization is to understand the evolution starting from virtualization. Before virtualization, companies used computers to host their applications. However, considering the many factors that require isolation of application and databases, companies had to use a considerable amount of such computers. The problem was that these computers were most of the time not being used to their full capacities. Because, some of them were just used to store data that in terms of compute resources did not require much resources.
Virtul machines(VM) was a major step in solving that problem. A virtual machine is an emulation of a computer system. Put simply, it makes it possible to run what appears to be many separate computers on hardware that is actually one computer.
In a virtual machine, valuable resources are emulated for the guest OS and hypervisor, which makes it possible to run many instances of one or more operating systems in parallel on a single machine (or host). Every guest OS runs as an individual entity from the host system.
## Containerization
While the VMs was a major step, they were not sufficient enough to solve the problem. The real solution to the problem came with the Container technology. 
Containerization is the packaging of software code with just the operating system (OS) libraries and dependencies required to run the code to create a single lightweight executable—called a container—that runs consistently on any infrastructure. More portable and resource-efficient than virtual machines (VMs), containers have become the de facto compute units of modern cloud-native applications.

* Note: Most applications require dependencies and work with specific version of OS and other softwares. When multiple applications require different sets of dependencies, it is not easy to have them work under the same VM. In such cases, having each application under a separate container solves this problem.

## Hypervisor vs. Docker Engine
Hypervisor and Docker Engine are both tools used to create and manage virtual environments, but they do so in different ways.

A hypervisor, also known as a virtual machine manager, is a software tool that creates and manages virtual machines (VMs). Each VM created by a hypervisor runs a separate operating system and has its own virtual hardware, including CPU, memory, and storage. This allows multiple virtual environments to run on a single physical machine, with each environment fully isolated from the others.

On the other hand, Docker Engine is a containerization platform that allows you to create and manage containers. Containers are similar to VMs in that they provide an isolated environment for running applications, but they do so by sharing the host operating system kernel rather than running a separate operating system in each container. This makes containers more lightweight and efficient than VMs.

In summary, hypervisors create and manage separate virtual machines with their own operating systems and virtual hardware, while Docker Engine creates and manages containers that share the host operating system kernel. 

* Boot up time is faster in containers as they share the kernel
* Docker has less isolation since kernel is shared compared to VMs.
* You can have multiple OS using hypervisor, such as Ubuntu and Windows
* You cannot have multiple OS on a single docker host

## Container vs image
An image is a package or a template that is used to create containers.
Containers are running instances of images that are isolated abd have their own environments and set of of processes.