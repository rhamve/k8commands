# Commands
## The kubectl command is to used to deploy and manage applications on a kubernetes cluster.

| Command | Description | Comments |
|---------|-------------|----------|
| kubectl run hello-minikube | is used to deploy an appliation on the cluster | |
| kubectl run niginx | it deploys a docker container by createing a Pod. It first creates a pod automatically and deploys an instance of the nginx docker image. | |
| kubectl run niginx --image nginx | it deploys a docker container by createing a Pod. It first creates a pod automatically and deploys an instance of the nginx docker image. It get the application image from the docker hub for that you need to specify the image name with image parameter. The application image is download from the docker hub repository a public repository (or from a private repository). | |
| kubectl cluster-info | cluster-info | |
| kubectl get nodes | list all the nodes as part of the cluster | |
| kubectl pod describe nginx | Describe information about PoD, lot more information when compared to the get command | |
| kubectl get pods -o wide | This provide additional information where the such as node ip address where the pod is running | |
| kubectl create -f pod-definition.yml | Creates the POD | |
| kubectl apply -f pod-definition.yml | Creates the POD | |
| kubectl create -f rc-definition.yml | Creates the replica set | |
| kubectl get replicationcontroller  | View the current number of replica set / pod | |
| kubectl create -f replicaset-definition.yml | Creates the replica set | |
| kubectl get replicaset  | View the current number of replica set / pod | |
| kubectl replace -f replicaset-definition.yml | scale up the replica set | |
| kubectl scale --replicas=6 -f replicaset-definition.yml | Another method to scale up the replica set | |
| kubectl scale --replicas=6 replicaset myapp-replicaset | Another method to scale up the replica set | |
| kubectl delete replicaset myapp-replicaset | Delete tbe replica set | |
| kubectl create -f deployment-definition.yml | Create deployments | |
| kubectl get deployments | Get deployments | |
| kubectl get replicaset | View deployments/replicaset | |
| kubectl get all | To view all deployments/replicaset | |
| kubectl describe deployment myapp-deployment | To describe about all the deployments. Events at the end describes the replicaset about the deployment and its details, etc,.. | |

