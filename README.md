<<<<<<< HEAD

# DevOps CI/CD Project

## Project Overview
This project demonstrates a complete DevOps pipeline using modern tools and practices.  
It includes code integration, automated build, containerization, and deployment.

---

## Tech Stack
- AWS EC2
- Jenkins
- GitHub
- Docker
- Kubernetes
- Nginx (for web server)

---

## Architecture
1. Developer pushes code to GitHub
2. Jenkins detects changes (webhook)
3. Jenkins builds the project
4. Docker image is created
5. Image is pushed to Docker Hub
6. Kubernetes deploys the application

---

## Project Structure

    project-root/
    │── app/
    │── Dockerfile
    │── Jenkinsfile
    │── deployment.yaml
    │── service.yaml
    │── README.md

---
## Setup Instructions

### Clone Repository
```bash
git clone https://github.com/NandhiniKandasamy29/GuviProject
cd <GuviProject>
docker build -t app .
docker run -p 3000:3000 app

**Kubernetes**
    kubectl apply -f deployment.yaml
    kubectl apply -f service.yaml

**External-Ip**
    a675ab45bbc2b495bbf5b13d1f7b6fc6-1624662063.ap-south-1.elb.amazonaws.com

**Application URL**
    http://a675ab45bbc2b495bbf5b13d1f7b6fc6-1624662063.ap-south-1.elb.amazonaws.com/

---

# GuviProject
Guvi DevOps projects
>>>>>>> b7c57e82cf18df8594da2d9eba9f44a9e0845654
