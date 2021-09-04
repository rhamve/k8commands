# Install Kubernetes installs the following Components:
| Container | Explanation | Master (or) Worker Node | 
|-----------|-------------|-------------------------|
| API Server | Gateway for the client such as command line, servers, mobile, any clients | M |
| etcd | Is a distributed reliable Key-value store used to manage all values of the cluster | M |
| Scheduler | Distributing work for the containers across the multiple nodes. It looks for newly rollout containers and assign them to the nodes | M |
| Controller | are the brain behind orchestration, they are responsible for noticing and responding when nodes or containers or endpoint goes down. In such case, it scales up …	| M |
| Container runtime	| Is a underlying software that runs the container, in this case it is Docker, rkt,  etc,.. | W |
| Kubelet | Is the agent that runs on each node on the cluster, agent is responsible for making sure that containers are running on the nodes as expected |	W |
| Command Line Utility: Kubectl | Is used to deploy and manage applications on the kubernetes cluster, to get cluster info, | |
