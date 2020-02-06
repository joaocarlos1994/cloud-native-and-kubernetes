# cloud-native-and-kubernetes

<h3>Chapter 04 Notes</h3>

<h5>Deployments</h5>
<p>
For each program that is necessary to manager, the Kubernetes creates a right object Deployment, that is responsible for save some informations
about the program: the name of image container, number of clone that will execute and whatever information necessary for start the container.
</p>

<p>
Working with Deployment resource, we have the kind of object Kubernetes called controller. The controllers watch all resources which it is responsible, because it is responsible for validations such as correct functioning. If one object Deployment not executing the number of clones correct, the controller will create a new clone of pod.
</p>


<p>
The object Deployment does not manager directly the clones: it create automatically an object called as ReplicaSets
</p>

<h5>Search for Deployments</h5>
<p>
We can search for all deployments using the following command:
</p>

<code>kubectl get deployments</code>

<p>For get more details about the deployment we can usa this command</p>

<code>kubectl describe deployments/demo</code>

<h5>Pods</h5>
<p>
Pod is a Kubernetes object that represents a group of one or more containers.
</p>

<p>
The speficiation of <i>Image</i> in this case is DOCKER_ID/IMAGE_NAME join with port number, is the information for Deployment start the pod and maintain it in alive. Example of deployment object below:
</p>

<code>
Name:                   demo
Namespace:              default
CreationTimestamp:      Wed, 05 Feb 2020 12:43:45 -0300
Labels:                 app=demo
Annotations:            deployment.kubernetes.io/revision: 1
Selector:               app=demo
Replicas:               1 desired | 1 updated | 1 total | 1 available | 0 unavailable
StrategyType:           RollingUpdate
MinReadySeconds:        0
RollingUpdateStrategy:  25% max unavailable, 25% max surge
Pod Template:
  Labels:  app=demo
  Containers:
   demo:
    Image:        joaocbatista/cloud-native-image
    Port:         9999/TCP
    Host Port:    0/TCP
    Environment:  <none>
    Mounts:       <none>
  Volumes:        <none>
Conditions:
  Type           Status  Reason
  ----           ------  ------
  Available      True    MinimumReplicasAvailable
  Progressing    True    NewReplicaSetAvailable
OldReplicaSets:  <none>
NewReplicaSet:   demo-8c7f9656b (1/1 replicas created)
Events:          <none>
</code>

<p>
It's an important subject is <i>kubectl run</i> not create a pod, this command create Deployment object and Deployment object started the pod.
The deployment is a declarion of the wanted state.
</p>



