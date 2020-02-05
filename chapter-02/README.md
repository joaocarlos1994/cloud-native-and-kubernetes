# cloud-native-and-kubernetes

<h3>Chapter 02 Notes</h3>
<p>
	Some scratch means from zero.
	For create some image run the following code:

		<code>docker image build -t first-image .</code>

	The "-t" is to add a name for your image and "." is to add everything for you image, like git add from Git.
	The second command to execute is for create a virtual container on docker enverioment. For create a container run
the following statement:

		<code>docker container run -p HOST_PORT:CONTAINER_PORT IMAGE_NAME</code>
		<code>docker container run -p 9999:8888 first-image</code>

	For create or execute a pod you need to push a image on local docker registry or docker docker hub. The first step is to send
image for local docker resgitry:

		<code>docker image tag IMAGE_NAME YOUR_DOCKER_ID/IMAGE_NAME</code>

	To send this image for docker hub run the following image:

		<code>docker image push YOUR_DOCKER_ID/IMAGE_NAME</code>

	For create a container inside cluster on Kuberts run the following command:

		<code>kubectl run demo --image=first-image --port=9999 --labels app=demo</code>

	Actually this command is depreacted , use this one 
		
		<code>kubectl run --generator=deployment/apps.v1 is DEPRECATED and will be removed in a future version. Use kubectl run --generator=run-pod/v1 or kubectl create instead.</code>

	For delete some you can run this command:

		<code>kubectl delete pod POD_NAME</code>

	If necessary you could forwad request port using the following command:
	
		<code>kubectl port-forward deploy/APP_NAME INCOMING_PORT:OUTCOMING_PORT</code>

		<code>kubectl port-forward deploy/demo 9999:8888</code>
	
	To check the exists pod running run the following command:

		<code>kubectl get pods --selector app=NAME_APP</code>

		<code>kubectl get pods --selector app=demo</code>
		
</p>
