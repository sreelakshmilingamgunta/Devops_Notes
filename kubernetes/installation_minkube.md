install kubectl on linux
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
```
```
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
```
```
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```
```
[ chmod +x kubectl
mkdir -p ~/.local/bin
mv ./kubectl ~/.local/bin/kubectl ] ---> if you don't have root access
```
```
kubectl version --client
kubectl version --client --output=yaml
```
## install minikube
i want to use docker container service as driver for minikube
```
sudo apt update
sudo apt install docker.io
sudo systemctl start docker
sudo usermod -aG docker $USER && newgrp docker 
sudo systemctl enable docker
sudo systemctl status docker
```
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```
```
minikube start --driver=docker
```



# to see how many clusters are running  inside minikube
```
kubectl get nodes -o custom-columns=NAME:.metadata.name,CPU:.status.capacity.cpu
```
#particularly inside minikube
```
minikube ssh "grep -c processor /proc/cpuinfo"
```
```
kubectl cluster-info --> Check that kubectl is properly configured by getting the cluster state
```
```
kubectl get po -A
Create a sample deployment and expose it on port 8080:

kubectl create deployment hello-minikube --image=kicbase/echo-server:1.0
kubectl expose deployment hello-minikube --type=NodePort --port=8080

It may take a moment, but your deployment will soon show up when you run:

kubectl get services hello-minikube
The easiest way to access this service is to let minikube launch a web browser for you:

minikube service hello-minikube

Alternatively, use kubectl to forward the port:

kubectl port-forward service/hello-minikube 7080:8080


kubectl delete service hello-minikube
kubectl delete deployment hello-minikube
kubectl delete deployment hello-minikube --grace-period=0 --force
kubectl get services
kubectl get deployments
kubectl get pods
```
