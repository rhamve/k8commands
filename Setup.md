# Setup Kubernetes

| Virutal Machines | Description | Hosted VM |
|------------------|-------------|-----------|
| Minikube | bundles all of the k8s components into a single image providing as preconfigured single node k8s cluster. The whole bundle ISO image is available online |  GCP | 
| MicroK8s |  |  AWS |
| kubeadm  | is used to manage bootstrap and manage production  | MS Azure |

# Minikube Setup
1. Minikube hypervisor ISO image installed: 
2. Virtual Box (or) Docker
3. kubectl


## Install kubectl
1. Kubernetes.io -> Documentation -> Tasks -> Install Tools
2. brew install kubectl 
3. kubectl version --client

### Reference: https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/


## Install Minikube
1. After install, start your cluster: minikube start

# Start Minikube
kubectl version --client

kubectl cluster-info

````
Kubernetes control plane is running at https://127.0.0.1:53686
CoreDNS is running at https://127.0.0.1:53686/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

```
kubectl get nodes

````
NAME       STATUS   ROLES                  AGE   VERSION
minikube   Ready    control-plane,master   15d   v1.21.2
```

 # Trouble Shooting 
 #minikube start and stop

192:k8commands rhamkuvenkat$ kubectl cluster-info

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
The connection to the server 127.0.0.1:50934 was refused - did you specify the right host or port?

# Tools / IDE
## ATOM
## PyCharm

