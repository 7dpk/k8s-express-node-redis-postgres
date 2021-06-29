# k8s-express-node-redis-postgres

## Setup
Install ```minikube``` or any other local kubernetes cluster maker

```
 minikube start
 kubectl cluster-info
 ```
 to check cluster is up and running
 
 ## Create a secret for postgres password
 ``` kubectl create secret generic pgpassword --from-literal PGPASSWORD=postgres_password```
 
 ## Start the containers
 ``` kubectl apply -f k8s/```
 
 ## Check results
 ```minikube ip```
 use the above ip (local) to see the result
 
 ## NOTE:
  By default my personal dockerhub repo(deapu) is used for retrieving images, you can recreate your own images with dockerfile inside every folder.
