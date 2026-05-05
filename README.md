#  Brain Tasks App – DevOps CI/CD Project

##  Project Overview

This project demonstrates a complete **DevOps CI/CD pipeline** for deploying a containerized web application using AWS services.

The application is built, containerized using Docker, pushed to Amazon ECR, and deployed on Kubernetes using Amazon EKS. CI/CD automation is implemented using AWS CodePipeline and CodeBuild.

---

##  Architecture

GitHub → CodePipeline → CodeBuild → Amazon ECR → Amazon EKS → LoadBalancer → Browser

---

##  Tech Stack

* AWS ECR (Container Registry)
* AWS CodeBuild (Build & Docker Image Creation)
* AWS CodePipeline (CI/CD Automation)
* AWS EKS (Kubernetes Cluster)
* Docker (Containerization)
* Kubernetes (Deployment & Service)
* CloudWatch (Logs & Monitoring)
* GitHub (Source Code Management)

---

##  Project Structure

```
Brain-Tasks-App/
│── deployment.yaml
│── service.yaml
│── buildspec.yml
│── Dockerfile
│── README.md
```

---

##  Setup Instructions

### Clone Repository

```
git clone https://github.com/NandhiniKandasamy29/Brain-Tasks-App.git
cd Brain-Tasks-App
```

---

### Build & Push Docker Image (via CodeBuild)

* Created ECR repository: `mindtrack-repo`
* CodeBuild uses `buildspec.yml` to:

  * Build Docker image
  * Tag image
  * Push to ECR

---

### EKS Cluster Setup

* Cluster created using `eksctl`
* Node group with 2 worker nodes
* Verified using:

```
kubectl get nodes
```

---

### Application Deployment

Update image in `deployment.yaml`:

```
image: 634747715945.dkr.ecr.ap-south-1.amazonaws.com/mindtrack-repo:latest
```

Deploy:

```
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

---

### Access Application

```
kubectl get svc
```

* Copy **EXTERNAL-IP: http://a58a25adce7704904995c9c3026972bf-284435617.ap-south-1.elb.amazonaws.com/**
* Open in browser

---

## CI/CD Pipeline

### Pipeline Flow:

1. Code pushed to GitHub
2. CodePipeline triggers automatically
3. CodeBuild builds Docker image
4. Image pushed to ECR

---

## CloudWatch Logs

* Logs available in:

```
/aws/codebuild/mindtrack-build
```

* Used for monitoring build execution

---

## Screenshots (Attached in submission)

* CodeBuild success
* CodePipeline execution
* EKS pods & services
* Application running in browser
* CloudWatch logs

---

## ✅ Key Achievements

✔ Automated CI/CD pipeline
✔ Docker image build and push to ECR
✔ Kubernetes deployment on EKS
✔ Application exposed via LoadBalancer
✔ Monitoring using CloudWatch

---

## 👤 Author

Nandhini Kandasamy

---
