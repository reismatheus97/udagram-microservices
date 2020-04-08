# cloud-developer
content for Udacity's cloud developer nanodegree

##### Docker  
##### Kubernetes  
##### Travis

This project have public [images](https://hub.docker.com/u/reismatheus97) at Docker Hub.

## Running services locally (Docker)
`cd course-03/exercises/udacity-c3-deployment/docker/`  
`docker-compose up`  

## Deploying to a Kubernetes cluster
Every resource to k8s resides in `course-03/exercises/udacity-c3-deployment/k8s/`  
It includes Deployments, ConfigMaps, Secrets and Services.

To start deploying, apply the each one of `.yml` files, for example:   
`kubectl apply -f aws-secret.yaml`   

After applying those:  
`kubectl get pods`  
Now we you able to see the cluster pods and its status.  

## Expose cluster services
To access services, we should expose both frontend and reverse-proxy services.  
This can be achived with the following command:  
`kubectl port-forward service/reverseproxy 8080:8080`  
`kubectl port-forward service/frontend 8100:8100`  

Now we are good to go and use Udagram App, check it out at the browser:    
[http://localhost:8100]  


## Continuous Integration
This project uses Travis as CI tool.  
Every commit at branch master will trigger a build process descibred at `.travis.yml` file.  
The build process will use Docker to build containers according to the `docker-compose-build.yml` file.  


