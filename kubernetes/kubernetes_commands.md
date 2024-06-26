```
kubectl run <podName> --image=<ImageName>   --> to create a pod 
kubectl create deployment <podName> --image=<imageName> --> To create a deployment
kubectl edit deployment [deployment Name] --> To update the deployment
kubectl delete deployment <deployment Name>
```
```
kubectl get nodes| pods| services| deployment| replicaset   --> To see status different kubenetes components
kubectl get pods -o wide
```

-----> Name Space <--------
```
kubectl create namespace <NameSpaceName> --> to create a new name space
kubectl apply -f <configurationFile> --namespace=<NameSpace> --> to cerate resources inside a name space
kubectl get all -n <NameSpace> --> To see all the resources under particular Name space
```
-----> Debugging Pods <-------
```
kubectl logs <podName>  --> Logs to console
kubectl describe pod <podName> --> Get info about pod
kubectl exec -it <podName> -- bin/bash --> We can debug, To get interactive Terminal
```
```
kubectl apply -f <configuration File> --> To create a deployment using configuration file
```
- kubernetes uses yaml files as inputs for the creation of objects such as pods, replicas, deployment services, etc.

```
#creating pod using yaml script ? 

apiVersion: v1
kind: Pod
metadata: 
    name: myapp-pod
    labels:
        app: my-app
        type: front-end
spec:
    containers:
        - name: nginx
          image: nginx
```
# creating Replica Controllers using Yaml script ? 
```
apiVersion: v1
kind: ReplicationController
metadata: --------------------------------------------> ReplicaController Meta Data
    name: myapp-rc
    labels:
        app: myapp
        type: front-end
spec:   -----------------------------------------------> ReplicaController Spec
    template:
        metadata: --------------------------------------> Pod Meta Data
            name: myapp-pod
            labels:
                app: my-app
                type: front-end
        spec: --------------------------------------------> Pod Spec
           containers:
                - name: nginx
                  image: nginx
    replicas: 3
kubectl get replicationcontroller   -->  to view created replica controllers 
```

# creating Replica Set using yaml script
```
apiVersion: apps/v1
kind: ReplicaSet
metadata: --------------------------------------------> Replica SetMeta Data
    name: myapp-replicaset
    labels:
        app: myapp
        type: front-end
spec:   -----------------------------------------------> Replica Set
    template:
        metadata: --------------------------------------> Pod Meta Data
            name: myapp-pod
            labels:
                app: my-app
                type: front-end
        spec: --------------------------------------------> Pod Spec
           containers:
                - name: nginx
                  image: nginx
    replicas: 3
    selector:  ----------------------------> identify what pods fall under it
        matchLabels: ----------------------> matches the labels specified under it to the labels on the pods.
            type: front-end

```
```
kubectl replace -f replicaset-definition.yml -----> to update definition file
kubectl scale --replicas=6 -f replicaset-definition.yml ---> to scale the replications
kubectl scale --replicas=6 replicaset(type) myapp-replicaset(name) 
kubectl delete replicaset myapp-replicaset(name) -----> also delete underlying PODs
```

