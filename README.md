# Kubernetes

## What is kubernates
Kubernetes is an open-source container managment platform that automates the deployment, scaling, and management of containerized applications. It was originally developed by Google and is now maintained by the Cloud Native Computing Foundation (CNCF).

## Why kubernates is used:
When you run applications in containers (like Docker), managing them manually can be complex. Kubernetes makes it easier by:
- Automatically managing container lifecycles
- Scaling applications up or down based on demand
- Load balancing traffic between multiple containers
- Self-healing by restarting failed containers
- Rolling updates without downtime

## Cluster
A Kubernetes cluster is a group of machines (nodes) that work together to run and manage containerized applications efficiently. It consists of a Control Plane (Master Node) and multiple Worker Nodes that execute the applications.

## Kubernates architecture
![kubernates-architure](kubernates-arch.jpg)
### Explanation:
A Kubernetes architecture consists of a Control Plane (Master Node) and Worker Nodes that manage and run containerized
applications
### 1. Control pannel: 
The Control Plane is responsible for managing the Kubernetes cluster. It makes decisions about scheduling, scaling, and maintaining the system state.
#### Key components of control pannel
1. API Server
- The main entry point for all Kubernetes commands (kubectl, API calls).
- It validates and processes requests.
2. Controller Manager
  - Ensures the cluster is in the desired state
3. Scheduler
- Assigns Pods to Worker Nodes based on resource availability
4. etcd
- stores key-value type data
- A distributed database that stores cluster state and configuration.
- Every change in the cluster is recorded in etcd.
### 2. Worker Nodes
Worker Nodes run the actual applications in the form of Pods (smallest deployable units in Kubernetes
#### Key components of Worker Nodes:
1. Kubelet
- Runs on every Worker Node
- Communicates with the Control Plane and ensures that Pods are running.
3. Kube Proxy
- Handles networking and ensures that Pods can communicate with each other.
4. Container Runtime
- The software responsible for running containers

### Installation Of Docker
```
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl -y
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

#Install the Docker packages, install the latest version, run:
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```
