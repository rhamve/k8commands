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
## Basisc of Networking in K8s
### IP Address to the Pod
1. Start with single node kubernetes cluster, the node has an IP Address. For ex: 172.148.1.2. This is the IP Address used to access the K8s node, ssh into it, etc,.. 
2. for a Minikube setup, the IP address of the Minikube virtual machine inside your hypervisor, your laptop may have a different IP like 172.148.1.10, then the minikube has another IP address like 172.148.1.2
3. In Kubernetes world IP address is always assigned to Pod 10.244.0.2, Unline In Docker World it is assigned to the whole Docker Container. Each Pod in the k8s gets its own internal IP address.

Node -> Pod -> Container instance
Each Pod will have on IP Address with the range of 10.244 series

### How it is getting the IP Address / its range
When the K8s is initially configured we create an internal private network with the address 10.244.0.0 and all the pods are attached to it. When you deploy multiple pods, all the pods assigned a separate IP address from this private network address. The pods can communicate to each other through this IP. (Accessing other pods through this IP address may not be good idea as its subject to change when pods are recreated.)

### Cluster Networking
Problem: IP conflicts
1. As a matter of fact, K8s expects us to set up networking to meet certian fundamental requirements. Some of these are that all the containers or pods in a K8s cluster must be able to communicate to one another without having to configure NAT. 
2. All nodes must be able to communicate with containers and all containers must be able to communicate with the nodes in the cluster. K8s expects us to setup a NETWORKING SOLUTION that meets the above criteria.
Examples are:
1. Cisco FCI Networks
2. Psyllium
3. Big Cloud fabric
4. Flannel - Own System
5. VMware NSX - VMware environment
6. Kalikow - Own System
it now manages the networks and IPs in the nodes and assigns a different IP address for each network in the node. This creates the network address of all pods and nodes where they are all assigned the unique IP address, SOLVES THE PROBLEM OF IP CONFLICTS. Any by using the simple IP techniques, the cluster networking enables communication between the different pods or nodes between the networking requirements of K8s. Thus all the Pods can communicate to each other using the assigned IP address.
## K8s Services 
Enable communication between various components within and outside of the application. Services enable loosle coupling between microservices in our application.
K8s Service is an object just like pods, replicaset, or deployment that we worked with before. 
### Node Port Service
One of its use case is <b> Node Port </b> to listen to a port on the node and forward the request on the port to a pod on the port running the web application.
Node IP: 172.168.1.2
Laptop IP: 172.168.1.10
Pod IP: 10.244.0.2
Private Network Address Range: 10.244.0.0
#### how to access a WebPage / Application in the Pod
Option 1 - SSH TO THE NODE:
ssh to kubernetes node 192.168.1.2 from the laptop, then from inside the ssh node, access the webpage curl http://10.244.0.2, output "Hello World!"
Option 2 - WITHOUT SSH TO THE NODE:
Requirement is to directly access WebPage / Application in the laptop, curl 172.168.1.2, output "Hello World!". 
Map Request from Laptop -> Node, This is where K8s Service comes into play. Laptop -> SERVICE -> Node.
This type of service is known as Node Port Service, because <b> the service listens to a port (ex: 10008) on the node and forward request to the pods </b>. Thus Service makes an internal pod accessible on a port on the node.
### Cluster IP Service
In this case, the service creates a Virtual IP inside the cluster to enable communication between different services, such as a set of front end servers and a set of back end servers.
### Load Balancer Service
This type where it positions a load balancer for our application in supported cloud providers. Example: Distribute the load across the different webservers in your front end tier.
# k8s State Persistance

