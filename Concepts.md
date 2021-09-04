# k8 Concepts
| Terms | Explanation | Example |
|-------|-------------|---------|
| Containers | Light Weight Virtual Machines (Sharing same OS Kernels) | Dockers |
| Image | Is a package or template used to create one or more containers. | Same as like VM template |
| Docker Hub | Public Registry for Docker images  | |
| Node (Minions) | Is a machine physical / virtual on which kubernetes is installed, Node is a worker machine that’s where containers will be launched by kubernetes | |
| Cluster | Cluster is a set of nodes grouped together | |
| Cluster Master | Master is responsible for actual orchestration of containers on the worker nodes | |
| Pods | | |
| Container Orchestration | The platform needs to orchestrate connectivity between the containers, dramatically scale up or down based on the load. This process of  automatically scale up and down process of managing and deploying containers | Kubernetes, Docker Swarm, Mesos |

# # Setup Kubernetes
| Virutal Machines | Description | Hosted VM |
|------------------|-------------|-----------|
| Minikube | bundles all of the k8s components into a single image providing as preconfigured single node k8s cluster. The whole bundle ISO image is available online |  GCP | 
| MicroK8s |  |  AWS |
| kubeadm  | is used to manage bootstrap and manage production  | MS Azure |

# Minikube Setup
1. Minikube hypervisor ISO image installed
2. Virtual Box
3. kubectl
