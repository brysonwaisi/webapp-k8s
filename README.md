## Deploy WebApp over Kubernetes
In this project, we will containerize and deploy a Simple Ruby-on-Rails (RoR) application over Kubernetes.

This application provides search functionality and enables the users to search for the courses. These courses are stored and fetched from the PostgreSQL database.

### Cluster
To run Kubernetes, you must have a cluster. You can spin one using 
* minikube
* kind
* Docker Desktop
* kubeadm
* AKS
* EKS
* GKE etc

### Kind Cluster 
- Create a kind cluster using the following command   <br>
`kind create cluster`
- Use the following command to display the name of the cluster.   <br>
`kind get clusters`
- To interact with a specific cluster   <br>
`kubectl cluster-info --context kind-kind`   <br>
`kubectl cluster-info --context kind-kind-2`
- Delete Cluster   <br>
`kind delete cluster`
- Using a config file   <br>
`kind create cluster --config kind-example-config.yaml`

### Containerize and push Image
Create Docker image and push it

- Login to dockerhub   <br>
`docker login -u username -p password`

- build image and push    <br>
`docker build -t username/image-name:tag .`   <br>
`docker push username/image-name:tag`   

### Inject Environment Variables to the containers using ConfigMap
- Create a ConfigMap

### Deploy App to K8s
- Deploy
e.g `kubectl apply -f database.yaml`  <br>

- Verify deployment  <br> 
`kubectl get deployments`

- Do that for the Service, Frontend and Backend

- Forward the service 
`kubectl port-forward svc/app-svc --address 0.0.0.0 31111:3000`

### Make the app live
Configure it to the internet via a proxy, domain, Load Balancer, app gateway etc

 * <b>NOTE</b>: This is not a production grade configuration