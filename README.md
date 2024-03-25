# Kubernetes hackathon

## Prerequisites
- Kubectl installation
	- https://kubernetes.io/docs/tasks/tools/
- Minikube installation
	- https://minikube.sigs.k8s.io/docs/start/
- Start the cluster using 
	 ```minikube start```
- Ensure minikube cluster context is set in **kubectl** command


## Task 1
List all kubernetes nodes using `kubectl get nodes` command and paste the output below
	    
```
NAME       STATUS   ROLES           AGE   VERSION
minikube   Ready    control-plane   56m   v1.28.3

```

## Task 2
describe one kubernetes node using `kubectl describe node/<node-name>` command and paste the section from the terminal output below

**Number of cpu**:     
```
 cpu:                12
```
**Hostname**: 
```
Hostname:    minikube
```
**Cpu and Memory usage**:
```
Capacity:
  cpu:                12
  ephemeral-storage:  1055762868Ki
  hugepages-1Gi:      0
  hugepages-2Mi:      0
  memory:             7527572Ki
  pods:               110
```

## Task 3
List all kubernetes namespaces using `kubectl get namespace` command and paste the output below
	    
```
NAME              STATUS   AGE
default           Active   60m
kube-node-lease   Active   60m
kube-public       Active   60m
kube-system       Active   60m

```

## Task 4
List all the pods in '*kube-system*' namespace using `kubectl get pods -n <namespce command>`
	    
```
NAME                               READY   STATUS    RESTARTS      AGE
coredns-5dd5756b68-kjjpb           1/1     Running   0             61m
etcd-minikube                      1/1     Running   0             61m
kube-apiserver-minikube            1/1     Running   0             61m
kube-controller-manager-minikube   1/1     Running   0             61m
kube-proxy-xqc7v                   1/1     Running   0             61m
kube-scheduler-minikube            1/1     Running   0             61m
storage-provisioner                1/1     Running   1 (60m ago)   61m

```


## Task 5

Create a namespace with name `my-namespace` using `kubectl create namespace <namespace name>` command

List all namespaces like  in **Task 3**  and paste output below
```

namespace/my-namespace created

NAME              STATUS   AGE
default           Active   64m
kube-node-lease   Active   64m
kube-public       Active   64m
kube-system       Active   64m
my-namespace      Active   2m51s

```
## Task 6

Create a Pod with name `nginx` image `nginx:latest` in `my-namespace` using yaml configurations.

1. Create yaml configuration to create a pod should run on the namespace you created in the last **Task 5**

	Refference: https://kubernetes.io/docs/concepts/workloads/pods/#using-pods
3. Use `kubectl apply -f <filename>` command to apply the configuration


Copy the yaml content below
```

NAME              STATUS   AGE
default           Active   64m
kube-node-lease   Active   64m
kube-public       Active   64m
kube-system       Active   64m
my-namespace      Active   2m51s

```

List all the pods in the namespace `my-namespace` using `kubectl get pods -n <namespace>` command
```
<Paste output here>

```

Get extra details about the pods in the namespace `my-namespace` using `kubectl get pods -n <namespace> -o wide` command
```
<Paste output here>

```

## Task 7

Get details about `nginx` pod in `my-namespace`  using `kubectl describe pods/<pod-name> -n <namespace>` command


```
<Paste the output of describe command below>

```

## Task 8

Port forward the `nginx` (running in namespace `my-namespace`) pods's port `80` to your local systems port `9090` using `kubectl port-forward` command 

Refference: 
https://kubernetes.io/docs/reference/kubectl/generated/kubectl_port-forward/

```
<Paste the output of port-forward command below>

```

Open another terminal  and do a curl to the port using given command
`curl http://localhost:9090`

```
<Paste the output of curl command below>

```


## Task 9

List all the logs of pod `nginx` running in `my-namespace`  using `kubectl logs` command

Refference: 
https://kubernetes.io/docs/reference/kubectl/generated/kubectl_logs
```
<Paste the output of kubectl logs command>

```

## Task 10
Delete the pod `nginx` using the yaml configurations we created in the **Task 6**

`kubectl delete -f < yaml file name with path from task 6>`

Refference:
https://kubernetes.io/docs/reference/kubectl/generated/kubectl_delete

```
<Paste the output of kubectl delete command>

```

Delete the namespace `my-namespace` using `kubectl delete namespace <namespace>` command

```
<Paste the output of kubectl delete command>

```
