# K8s

# Kubernetes Project with MongoDB and Basic Web App

## Overview

This project demonstrates a Kubernetes deployment using Minikube and `kubectl`. It includes a basic MongoDB deployment with a `mongo-secret.yaml` file for secret configuration, and a basic web app deployment with port specification. Ingress and Egress configurations are also included for routing and external connectivity.

## Prerequisites

- Install Minikube: [Minikube Installation Guide](https://minikube.sigs.k8s.io/docs/start/)
- Install kubectl: [kubectl Installation Guide](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- Docker installed: [Docker Installation Guide](https://docs.docker.com/get-docker/)

## Project Structure

```plaintext
.
├── mongo-secret.yaml
├── webapp
│   ├── Dockerfile
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── ingress.yaml
│   └── egress.yaml
└── README.md

```

* mongo-secret.yaml: MongoDB secret configuration file.
* webapp/: Directory containing web app configurations.
* Dockerfile: Dockerfile for building the web app image.
* deployment.yaml: Deployment configuration for the web app.
* service.yaml: Service configuration for the web app.
* ingress.yaml: Ingress configuration for routing external traffic.
* egress.yaml: Egress configuration for external connectivity.

# Getting Started

Start Minikube cluster:

```
minikube start
```

Apply MongoDB secret:

```
kubectl apply -f mongo-secret.yaml
```

Deploy MongoDB:

```
kubectl apply -f mongodb-deployment.yaml
```

Deploy the web app:

```
kubectl apply -f webapp/deployment.yaml
```

Expose the web app service:

```
kubectl apply -f webapp/service.yaml
```

Apply Ingress for external access:

```
kubectl apply -f webapp/ingress.yaml
```

Apply Egress for external connectivity (if needed):

```
kubectl apply -f webapp/egress.yaml
```
# Docker Image for Web App

Build the Docker image for the web app:

```
cd webapp
docker build -t webapp-image:v1 .
```

Cleaning Up
To clean up resources:

```
kubectl delete -f mongo-secret.yaml
kubectl delete -f mongodb-deployment.yaml
kubectl delete -f webapp/
minikube stop
```

Feel free to customize the configurations based on your specific project requirements.
