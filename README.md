## To start minikube

minikube start

## To stop minikube

minikube stop

## To check minikube status

minikube status

## To create a new namespace "development"

<span style="color:yellow;">CMD:</span> kubectl create namespace development<br/>
<span style="color:green;">Result:</span> namespace/development created

## To get namespaces

<span style="color:yellow;">CMD:</span> kubectl get namespaces<br/>
<span style="color:green;">Result:</span><br/>
NAME STATUS AGE<br/>
default Active 132m<br/>
development Active 12m<br/>
kube-node-lease Active 132m<br/>
kube-public Active 132m<br/>
kube-system Active 132m

## To create a service (run a service.yaml script):

<span style="color:yellow;">CMD:</span> kubectl apply -f service.yaml<br/>
<span style="color:green;">Result:</span> service/demo-service created<br/>

## To get the services in "development" namespace

<span style="color:yellow;">CMD:</span> kubectl get services -n development<br/>
<span style="color:green;">Result:</span><br/>
NAME TYPE CLUSTER-IP EXTERNAL-IP PORT(S) AGE<br/>
demo-service LoadBalancer 10.109.28.88 127.0.0.1 80:32585/TCP 11m

## To get the pods in "development" namespace

<span style="color:yellow;">CMD:</span> kubectl get pods -n development<br/>
<span style="color:green;">Result:</span><br/>
NAME READY STATUS RESTARTS AGE<br/>
pod-info-deployment-554c495857-dgl5r 1/1 Running 0 115s

## To get deployments
CMD: kubectl get deployments<br/>
Result:<br/>
NAME             READY   UP-TO-DATE   AVAILABLE   AGE<br/>
deployment-name   1/1     1            1           4s

## To get pods
CMD: kubectl get pods<br/>
Result:<br/>
NAME                              READY   STATUS    RESTARTS   AGE<br/>
deployment-name-6fd48d96b6-f87dh   1/1     Running   0          3s

# To delete a deployment
CMD: kubectl delete deployment deployment-name<br/>
Result: deployment.apps "deployment-name" deleted

## To delete a service in a namespace

<span style="color:yellow;">CMD:</span> kubectl delete service demo-service -n development<br/>
<span style="color:green;">Result:</span> service "demo-service" deleted

## To delete a Kubernetes resource specified in the "deployment.yaml" file from a Kubernetes cluster

<span style="color:yellow;">CMD:</span> kubectl delete -f deployment.yaml<br/>
<span style="color:green;">Result:</span> deployment.apps "pod-info-deployment" deleted

## To delete a namespace

<span style="color:yellow;">CMD:</span> kubectl delete namespace development<br/>
<span style="color:green;">Result:</span> namespace "development" deleted

## To delete the minikube cluster

<span style="color:yellow;">CMD:</span> minikube delete<br/>
<span style="color:green;">Result:</span><br/>
🔥 Deleting "minikube" in docker ...<br/>
🔥 Deleting container "minikube" ...<br/>
🔥 Removing /Users/ismail-dev/.minikube/machines/minikube ...<br/>
💀 Removed all traces of the "minikube" cluster.

## To scan a script file (ex: deployment.yaml)

<span style="color:yellow;">CMD:</span> snyk iac test deployment.yaml
