 POD
  - usually 1 application per pod
  - Each pod gets its own IP address
  - New IP on re-creation
SERVICE
  - static or permanant IP address thta can be attached to each pods
  - life cycle of service and pod not connected, if pod dies service will stay
  - Load Balancer - service actually catches the request and forwatd that to pods
External Service - is a sevive that opens the communication from external sources.
Ingress --> Service
Ingress - Route traffic into the clusters
ConfigMap - usually contains configuration data like url of database and other services that they use.
            ! Don't put credentials into configmap - for these kubernetes has a component secrete
Secret - just like configmap used to store secret data

inorder to create the 2nd replica of 'my-app', you wouldn't create a 2nd pod but instead you'll define blueprints for 'my-app' pod and specify how many replicas that pod you need to run 
that blue print we'll call it as Deployment.

pod is layer of abstraction on top of containers
deployments are layer of abstraction on top of pods
  - for stateless applications
StatefulSet - 
  - for statefull apps like sql, mongoDB, elastic
  - databases should be created using statefulset 
  - deploying sttefulset is not easy
  - DB are often hosted on outside of the cluster

Node - Each node has multiple pods in it
worker node do actual work
3 processes must be installed in each pod used to that are used to shedule and manage.
  - 1. container runtime - docker, cri-o, containerd
  - 2. kubelet interacts with both container and node. and kubelet starts the pods with a container inside.
  - 3. Kubeproxy - is a network proxy that maintains network rules on nodes. It enables communication between services inside the cluster and external clients.
Master - Managing nodes is done by master
4 processes that runs on master node
 - 1. api-server - gets the intial request of any update into the cluster or even the query.
              - also acts as a gate keeper for authentication
              - only one entry point to the cluster
 - 2. scheduler - on which worker node the new pod should be sheduled?
             - The scheduler assigns pods to nodes based on resource availability and other constraints.
 - 3. controller-manager - detects cluster state changes
                         - which regulate the state of the cluster, such as node and replication controllers.
 - 4. etcd - etcd is a distributed key-value store used to store cluster state and configuration.
           - cluster changes get stored in the key-value pair
           - cluster state information which is used for master processes to communicate with work processes vice versa.
           - etcd holds current status of any kubernetes component

* master processes are more important but they actually have a less load of work, so they need less resources like cpu| ram| storage
* worker node do the actual job of running those nodes therefore they need more resources 
Minikube - is a one node cluster that runs in a virtual box.
         - one node cluster where the master processes and worker processes both run on one node.
         - creates a virtual box in our local
         - node runs in virtual box
         - for testing kubernets on local
Kubectl - command line tool for kubernetes cluster
! virtualization on your machine needed

* Deployment - blue print for creating pod. deployment manages pods
* Replicaset - manages all the replicas of the pods.
* Pod - an abstraction of containers.

Attributes of 'spec' are specific to kind

Each configuration file has 3 parts
 - 1. Metadata - Contains meta data about resources, suach as it's Name
 - 2. Spec - This section specifies the desired state for the resource.
           - replicas - this states desired number of pods to replicate.
           - selector - This specifies how to select the pods targeted by this deployment
           - template - This section contains the pod template used to create new pods.
                     - metadata.labels - This specifies the labels to apply to the pods.
                     - spec.containers - This specifies the containers to run in the pods
 - 3. status - automatically generated and added by kubernetes.

connection between deployment and services made through selector labels

Name Space - 
 - virtual cluster inside a physical cluster
 - It's a way to divide and organize resources within a Kubernetes cluster.
4 default Namespaces
 - 1.kube-system - do not create and modify on kube-system
                 - system processe
                 - master and kubectl processe
 - 2.kube-public - contains publicely accessible data
                 - conatins cluster information accessible even without authentication.
                 - a configmap which contains cluster information
 - 3.kube-node-lease - heart beat of nodes
                     - each node has associated lease object in node
                     - determines availability of a node
 - 4.default - resources you create are located here
     
----- INGRESS -------
Ingress provides routing rules to manage external users’ access to the services in a Kubernetes cluster, typically via HTTPS/HTTP.
With Ingress, you can easily set up rules for routing traffic without creating a bunch of Load Balancers or exposing each service on the node.

You must have an Ingress controller to satisfy an Ingress. 


Resource Quota is like a limit or boundary set on how much of the computing resources (like CPU and memory) a group of containers or namespaces 
can use within a cluster.









