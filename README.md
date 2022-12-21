# About
In this repository, you will find all the necessary files and instructions to deploy a MongoDB database on a Kubernetes cluster using Minikube.

# Prerequisites
- Docker
- Minikube
- kubectl

# Deployment
Start Minikube: `minikube start`

Apply the configuration files in the kubernetes directory: `kubectl apply -f kubernetes/`

This will create a Kubernetes deployment and service for the MongoDB database.

Check the status of the pods: `kubectl get pods`

To connect to the MongoDB database from your application, you can use the service name as the hostname and the port specified in the mongodb-service.yaml file (default is 27017).

# Configuration

You can customize the configuration of the MongoDB deployment by modifying the following files:

**mongodb-deployment.yaml**: This file specifies the number of replicas and the container image to use for the MongoDB deployment.

**mongodb-service.yaml**: This file specifies the service name and port for the MongoDB deployment.

# Backup and Restore
To create a backup of the MongoDB database: `kubectl exec -it mongodb-xxxxx-yyyyy -- mongodump --out /backup`

To restore a backup, you can use the mongorestore utility: `kubectl exec -it mongodb-xxxxx-yyyyy -- mongorestore /backup`
