# kubernetes express node redis postgres example

This Kubernetes project containerizes a `React` application as the frontend, which is used to calculate a time-consuming task - in this case, finding the nth Fibonacci number. The application is designed to be scalable and able to handle large amounts of traffic.

The project also includes a `PostgreSQL` database for data storage, a `Redis` server for caching, and a `Node` `Express` server to handle incoming requests. Each of these services is separated into its own folder with its own Dockerfile, which helps to keep the codebase organized and easy to manage.

To manage the deployment of the various services, `Kubernetes` is used, along with several Kubernetes-specific components. These include an IP service to assign IP addresses to each service, an `ingress service` to handle incoming traffic and routing, and a `persistent volume claim` to ensure that data is stored securely and can be easily accessed.

Overall, the project demonstrates how Kubernetes can be used to manage complex, multi-component applications in a scalable and efficient manner.

## Setup
> _**NOTE**_:
  By default my personal dockerhub repo(`deapu`) is used for retrieving images, you can recreate your own images with dockerfile inside every folder.

Install ```minikube``` or any other local kubernetes cluster maker

```bash
 $ minikube start
 $ kubectl cluster-info
 ```
 to check cluster is up and running

## Create a secret for postgres password
 ```bash
 $ kubectl create secret generic pgpassword --from-literal PGPASSWORD=postgres_password
 ```
 
 ## Start the containers
```bash
$ kubectl apply -f k8s/
```
 
 ## Check results
 ```bash
 $ minikube ip
 ```
 use the above ip (local) to see the result
 

