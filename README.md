# CafeApp

CafeApp is a simple Spring Boot web application containerized using Docker and automated with Jenkins for CI/CD.

## Technologies Used

- Java 21
- Spring Boot
- Maven
- MySQL
- Docker
- Docker Compose
- Jenkins

## Features

- Spring Boot web application
- MySQL database integration
- Dockerized application
- Docker Compose for multi-container setup
- Jenkins pipeline for automated build and deployment

## Project Structure

```
CafeApp/
├── src/
├── Dockerfile
├── docker-compose.yml
├── Jenkinsfile
├── pom.xml
└── README.md
```

## Build the Project

```bash
mvn clean package
```

## Run Using Docker Compose

```bash
docker compose up --build -d
```

## Access the Application

```
http://localhost:8085
```

## Stop the Application

```bash
docker compose down
```

## Author

Shreelaxmi Bhat