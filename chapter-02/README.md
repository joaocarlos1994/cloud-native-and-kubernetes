# cloud-native-and-kubernetes

<h3>Chapter 02 Notes</h3>
<p>
	Some scratch means from zero.
	For create some image run the following code:
</p>

		<code>docker image build -t first-image .</code>

<p>
	The "-t" is to add a name for your image and "." is to add everything for you image, like git add from Git.
	The second command to execute is for create a virtual container on docker enverioment. For create a container run
the following statement:
</p>

		<code>docker container run -p HOST_PORT:CONTAINER_PORT IMAGE_NAME</code>
		<code>docker container run -p 9999:8888 first-image</code>

<p>
	For create or execute a pod you need to push a image on local docker registry or docker docker hub. The first step is to send
image for local docker resgitry:
</p>

		<code>docker image tag IMAGE_NAME YOUR_DOCKER_ID/IMAGE_NAME</code>

<p>
	To send this image for docker hub run the following image:
</p>

		<code>docker image push YOUR_DOCKER_ID/IMAGE_NAME</code>

<p>
	For create a container inside cluster on Kuberts run the following command:
</p>

		<code>kubectl run demo --image=first-image --port=9999 --labels app=demo</code>

<p>
	Actually this command is depreacted , use this one 
</p>

		<code>kubectl run --generator=deployment/apps.v1 is DEPRECATED and will be removed in a future version. Use kubectl run --generator=run-pod/v1 or kubectl create instead.</code>

<p>
	For delete some you can run this command:
</p>

		<code>kubectl delete pod POD_NAME</code>

<p>
	If necessary you could forwad request port using the following command:
</p>	

		<code>kubectl port-forward deploy/APP_NAME INCOMING_PORT:OUTCOMING_PORT</code>

		<code>kubectl port-forward deploy/demo 9999:8888</code>

<p>	
	To check the exists pod running run the following command:
</p>
		<code>kubectl get pods --selector app=NAME_APP</code>

		<code>kubectl get pods --selector app=demo</code>
