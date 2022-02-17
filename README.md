# kindk8scluster
Create a virtualized multi node kubernetes cluster on your host machine using kind


## Prerequisites 
1. Install Kind 
2. Install docker 
3. Install kubectl 


## Clone this repository and Create a multi Node kubernetes cluster with exposed NodePort for public access 
```
git clone https://github.com/ehtishammubarik/kindk8scluster
cd kindk8scluster
kind create cluster --config multi-node.yaml --name yotabytetest

```
## Wait for few minutes and make sure all nodes are up and read 

```
kubectl get nodes 
```

## Deploy nginx pod and service with port 30012 exposed for Nginx with Custom webpage. 

```
cd deployment
kubectl apply -f nginxpod.yaml
kubectl apply -f svc.yaml

```

## Image used for deployment is 

> ehtishammubarik/nginxalpine:1

######Available in dockerhub repo at https://hub.docker.com/r/ehtishammubarik/nginxalpine/tags


## Make sure that your pod and service are both up and service is exposed at port 30012

```
kubectl get all 
```

## Go to http://localhost:30012 for your custom web page. 

