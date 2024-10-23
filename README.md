Node.js DB Kubernetes Deployment

Project Structure

The project contains the following files:

── Dockerfile
── cluster-creat.sh
── configmap.yaml
── index.html
── index.js
── kubectl
── kubectl.sha256
── nodedb-service.yaml
── nodemongodb-service.yaml
── nodejs-db-deployment.yaml
── package.json
── package-lock.json
── aws


This README covers the steps to deploy a Node.js application along with a MongoDB service using Kubernetes.

Prerequisites
AWS-cli configure
Kubernetes cluster running
kubectl configured to communicate with your cluster
YAML configuration files for deployment and services

Deploy the Node.js application using the deployment configuration file:
kubectl apply -f nodejs-db-deployment.yaml
![image](https://github.com/user-attachments/assets/b4737a61-faed-45af-b3d7-962532bebd22)
This command creates a deployment named nodejs-db-deployment.

Create a ConfigMap to hold MongoDB configuration:
kubectl apply -f configmap.yaml
This command creates a ConfigMap named mongo-config.
![image](https://github.com/user-attachments/assets/5881b3ff-8ea5-4bdf-a77d-67e8a05b8114)

Create a Kubernetes service to expose the Node.js application:
kubectl apply -f nodedb-service.yaml
![image](https://github.com/user-attachments/assets/d60bfbf7-052d-4167-ae2a-457d5841d341)
This command creates a LoadBalancer service named nodedb-service.

Create a Kubernetes service to expose the MongoDB instance:
kubectl apply -f nodemongodb-service.yaml
![image](https://github.com/user-attachments/assets/d9cf263e-d71c-40d5-ad0a-a8d3214c5fdb)
This command creates a ClusterIP service named mongo.

Check the status of all Kubernetes resources:
kubectl get all
This command shows all pods, services, deployments, and replica sets in the cluster.
![image](https://github.com/user-attachments/assets/49c79e0e-1cfc-4145-9e4e-7aed48a43ce6)

Access the apllication through LoadBalancer with Port number
![image](https://github.com/user-attachments/assets/6d73409b-6e97-44fc-8b88-f8ea3d8c59ae)



