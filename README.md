# CafeApp

CafeApp is a Spring Boot web application containerized using Docker, deployed on a Kubernetes cluster, and automated using Jenkins CI/CD pipelines.

## Technologies Used

* Java 21
* Spring Boot
* Maven
* MySQL 8.0
* Docker
* Docker Hub
* Kubernetes
* Jenkins
* Nginx

## Features

* Spring Boot web application
* MySQL database integration
* Dockerized application
* Docker image pushed to Docker Hub
* Kubernetes Deployment and Service
* MySQL StatefulSet with Persistent Volume (PV) and Persistent Volume Claim (PVC)
* Jenkins CI/CD Pipeline for build and deployment
* Nginx Reverse Proxy
* Parameterized deployment pipeline

## Project Structure

```text
CafeApp/
├── src/
├── target/
├── kubernetes/
│   ├── namespace.yaml
│   ├── mysql-pv.yaml
│   ├── mysql-pvc.yaml
│   ├── mysql-service.yaml
│   ├── mysql-statefulset.yaml
│   ├── app-deployment.yaml
│   └── app-service.yaml
├── Dockerfile
├── docker-compose.yml
├── Jenkinsfile-build
├── Jenkinsfile-deploy
├── pom.xml
└── README.md
```

## Jenkins Pipeline 1

Pipeline 1 performs the following tasks:

* Checkout source code
* Build Spring Boot application using Maven
* Build Docker image
* Login to Docker Hub
* Tag Docker image
* Push Docker image to Docker Hub
* Clean Docker images and workspace

## Jenkins Pipeline 2

Pipeline 2 is parameterized and supports the following operations:

* Deploy Database
* Deploy Application
* Remove Application
* Remove Database

## Kubernetes Components

* Namespace (`production`)
* Spring Boot Deployment
* Spring Boot NodePort Service
* MySQL StatefulSet
* MySQL ClusterIP Service
* Persistent Volume (PV)
* Persistent Volume Claim (PVC)

## Build the Project

```bash
mvn clean package
```

## Build Docker Image

```bash
docker build -t cafeapp .
```

## Push Docker Image

```bash
docker tag cafeapp <dockerhub-username>/cafeapp:v1
docker push <dockerhub-username>/cafeapp:v1
```

## Deploy to Kubernetes

```bash
kubectl apply -f kubernetes/
```

## Verify Resources

```bash
kubectl get all -n production
kubectl get pv
kubectl get pvc -n production
```

## Access the Application

Access the application using:

* Kubernetes NodePort
* Nginx Reverse Proxy (Public IP)

Example:

```text
http://<Public-IP>
```

or

```text
http://<Node-IP>:30080
```

## Local Development

The project also includes a `docker-compose.yml` file for local development and testing using Docker Compose.

## Author

**Shreelaxmi Bhat**
