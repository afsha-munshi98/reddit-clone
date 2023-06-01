# Reddit Clone App on Kubernetes with Ingress
This project demonstrates how to deploy a Reddit clone app on Kubernetes with Ingress and expose it to the world using Minikube as the cluster.

## Prerequisites
Before you begin, you should have the following tools installed on your local machine: 

- Docker
- Minikube cluster ( Running )
- kubectl
- Git


## Installation
Follow these steps to install and run the Reddit clone app on your local machine:

1) Clone this repository to your local machine: `git clone https://github.com/afsha-munshi98/reddit-clone.git'
2) Navigate to the project directory: `cd reddit-clone`
3) Build the Docker image for the Reddit clone app: `docker build.-t afshamunshi/reddit-clone`
4) create a namespace in kubernetes: 'kubectl create namespace -n reddit-clone-ns'
5) Deploy the app to Kubernetes: `kubectl apply -f deployment.yaml -n reddit-clone-ns`
6) Deploy the Service for deployment to Kubernetes: `kubectl apply -f service.yaml -n reddit-clone-ns`
7) Enable Ingress by using Command: `minikube addons enable ingress`
8) Expose the app as a Kubernetes deployment: `kubectl expose deployment reddit-clone-deployment -n reddit-clone-ns --type=NodePort`
9) Expose the service: 'kubectl port-forward svc/reddit-clone-service 3000:3000 --address 0.0.0.0 &'
9) Create an Ingress resource: `kubectl apply -f ingress.yml`


## Test Ingress DNS for the app:
- Test Ingress by typing this command: `curl http://domain.com/test`



