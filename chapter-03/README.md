# cloud-native-and-kubernetes

<h3>Chapter 03 Notes</h3>

<h5>kube-apiserver</h5>
<p>
The Frontend server for control pane and this handle request from api
</p>


<h5>etcd</h5>
<p>
The databse of Kubernetes where it is stored all information: existing node, resources inside of cluster and etc.
</p>

<h5>kube-scheduler</h5>
<p>
It is responsible for start and execute all pods recentely created.
</p>

<h5>kube-controller-manager</h5>
<p>
It is responsible for execute the resource control, for example Deployments.
</p>

<h5>cloud-controller-manager</h5>
<p>
It is about of cloud providers.
</p>


<h5>Node Component</h5>
<p>
Member of a cluster that execute some kind of work load of user is calling as woker nodes. Each worker node on Kubernetes execute some component as the following topic.

kubelet is responsible for teach the runtime container to start the work load of <i>escanolaores</i> of a node and watch the status of it.

kube-proxy is responsible for routing the request between Pods and distinct node and between Pods and internet.

</p>


<h5>Runtime of Container</h5>
<p>
It is responsible for start and stop the container, and it is responsible for manager all comunication. Overall it is the Docker, but the Kubernetes permit all the other runtime containers, such as rkt and CRI-O
</p>
