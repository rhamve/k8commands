# k8s Architecture
# k8s Concepts
| Terms | Explanation | Example |
|-------|-------------|---------|
| Containers | Light Weight Virtual Machines (Sharing same OS Kernels) | Dockers |
| Image | Is a package or template used to create one or more containers. | Same as like VM template |
| Docker Hub | Public Registry for Docker images  | |
| Node (Minions) | Is a machine physical / virtual on which kubernetes is installed, Node is a worker machine that’s where containers will be launched by kubernetes | |
| Cluster | Cluster is a set of nodes grouped together | |
| Cluster Master | Master is responsible for actual orchestration of containers on the worker nodes | |
| Pods | The containers are encapsulated into kubernetes object known as PODs. A pod is an single instance of an application. Pods have 1-1 relationship with the containers running your application to scale up / down to create new / existing pods. Also we do not add additional containers to the existing pod to scale up applications. A Single Pod has multiple containers with different applcation (NOT same application) |  |
| Container Orchestration | The platform needs to orchestrate connectivity between the containers, dramatically scale up or down based on the load. This process of  automatically scale up and down process of managing and deploying containers | Kubernetes, Docker Swarm, Mesos |
| YAML | YAML file is used to represent the data. In this case it is configuration data | Key Value Pair, Examples Fruit: Apple|
| Controller | Are the brain behind the kubernetes  | |
| Replication Controller | Ensures number of pods running up all the time, just 1 or 100. Another reason is to load across the two pods. It is a older technology. It is now Replica Set | rc-definition.yml |
| Replication Controller Vs ReplicaSet | The difference is the Selector field under spec defines what POD fall under the replica set. |  |

# K8s Deployments 
| Rolling Updates | Upgrade one after the other pod in order not to impact the users accessing the applications. Undo the recent changes in case of any errors. Paused and rolled out the all the deployment together. |  |
| Deployment | Is the Kubernetes Object that is higher in the hierarchy. The Deployment provides the capability to upgrade the underlying instances seamlessly using rolling updates, undo changes, pause and resume changes |  |






Note: Difference between docker and pod is docker has one more application instances running on the same Node. For example A and B running on same node. In docker scenario, the connectivity between A and B is manually configured. However, in the Pod scenario, both the application will be installed on the same Pod, therefore Pod establishes that internal connectivity between A and B.

# k8s Configuration
# k8s Multi-Container Pods
# k8s Observability
# k8s Pod Design
# k8s Services & Networking
# k8s State Persistance

