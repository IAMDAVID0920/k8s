# k8s
my k8s practice

## Open Source Container orchestration tool

### What problem does k8s solve?

Trend from Monolith -> Microservices

### What features do orchestration tools offer?
    High Availibility
    Scalability/high performance

## K8s Architecture
Kubelet     
Control Plane:   Control Plane Nodes (Handful of master processes and **much more important!!!**)

    -> API Server (Entrypoint to k8s cluster)
        -> UI/API/CLI
    -> Controller Manager (Keeps track of whats going on in cluster)
    -> Scheduler (Ensures Pods placement) -> where to put the pod??
    -> Etcd (Key-Value storage) -> K8s backing store
Virtual Network
Node Node Node

    -> Worker Nodes (High workload, much bigger and more resources)

## Main K8S Components
### What is the role of each component?
Pod

    -> **Smallest unit in k8s**
    -> **Abstraction over container* (such as **Docker**) (Only interact with k8s layer)
    -> *Usually 1 application per pod*
    -> *Each Pod gets its own IP address*
    -> *During recreation, new IP address being assigned* (Ephermal)

Service

    -> Will have **Permanent IP address**
    -> **Lifecycle of Pod and Service are not connected (pod die不关service的事，service什么都不知道)**

    -> External Service (For application: web browser)
    -> Internal Service (For DB to keep secret)
    https://my-app.com 
    

Ingress
    
    Ingress - Service - Service

ConfigMap

    For small change db
    DB url usually in the built application (rebuild -> push to repo -> pull it in your pod)

    DB_URL = mongo db service

    External Config of your application
    just need to change configmap, no need to rebuild, push to repo, etc.

    **ConfigMap is for non-confidential data only!!!**

Secret

    Userd to store secret data
    encrypted using 3rd party tools

Volume

    Local storage
    Remote storage
    Storage on Local machine
    or Remote, outside of k8s cluster
    so when pod been restarted, data still there

K8s doesn't manage data persistance
    
User now could access application thru browser

Deployment

    Replicate everything on multiple servers
    The replica connect to same service
    Permanent ip, Service is also a load-balancer (forward to the one not busy)

    Blueprint for 'my-app' pods
    You create deployments

StatefulSet

    For stateful apps (MYSQL, MONGODB, ELASTIC, ...)

DaemonSet

# Config file 3 components

### Metadata
### Specification
### Status (Desired && Actual) been added automatically by k8s

## Minikube ? 
production cluster setup -> Test on local machine?
Minikube cluster: Run both Master processes and Worker processer, also docker been pre-installed

## Kubectl
to do anything, need to call APIServer to talk between clusters
Kubectl most powerful of 3 clients (ui, api, cli)

minikube install -> docker pre-install and also kubectl install as dependency, no further installation needed

```
minikube start --driver docker
minikube status

kubectl get node
```