# IDS706 Dockerized Application #

This repository contains a Python application that calculates the factorial of a number, containerized using Docker. The application demonstrates building and running Docker images locally and in a CI/CD pipeline, and pushing images to Docker Hub.

![Dockerized App Screenshot](https://github.com/therealzella/IDS06_Dockerized_Application/blob/main/Screenshot%202024-11-23%20at%2023.42.35.png)

## Features ##

* A simple Python application (main.py) that calculates the factorial of a number.
* Dockerized application using a Dockerfile.
* CI/CD pipeline using GitHub Actions.
* Docker image hosted on Docker Hub.

## How to Use ##

### Clone the Repository ###
```bash
git clone https://github.com/therealzella/IDS06_Dockerized_Application.git
cd IDS06_Dockerized_Application
```

### Build and Run the Docker Image Locally ###
**Build the Docker Image**
```bash
docker build -t dockerized-app .
```
**Run the Docker Container**
```bash
docker run -p 5000:5000 dockerized-app
```
**You should see output similar to:**
```bash
The factorial of 5 is 120
```

### Push the Docker Image to Docker Hub ###
Once the Docker image is built locally, push it to your Docker Hub repository using the following commands:
```bash
docker tag dockerized-app therealzella/dockerized-app:latest
docker push therealzella/dockerized-app:latest
```
### Pull and Run the Pre-Built Docker Image from Docker Hub ###
The Docker image for this application is available on Docker Hub. Pull and run it directly:

**Pull the Docker Image**
```bash
docker pull therealzella/dockerized-app:latest
```
**Run the Docker Container**
```bash
docker run -p 5000:5000 therealzella/dockerized-app:latest
```
## Docker Hub Repository ##

**The Docker image for this project is hosted on Docker Hub and can be found at the following link:**
```bash
https://hub.docker.com/r/therealzella/dockerized-app/tags
```

## CI/CD Pipeline ##

This repository includes a CI/CD pipeline using GitHub Actions. The pipeline automates the following steps:

1. Build the Docker image using the Dockerfile.
2. Push the built image to the Docker Hub repository.

## Repository Structure ##
```bash
IDS06_Dockerized_Application/
├── .github/workflows/
│   └── ci.yml         # GitHub Actions workflow
├── devcontainer/      # Development container configuration
├── main.py            # Main application script
├── main_test.py       # Unit tests for the application
├── requirements.txt   # Python dependencies
├── Dockerfile         # Dockerfile for containerizing the application
├── README.md          # Documentation
└── Makefile           # Optional make commands
```
