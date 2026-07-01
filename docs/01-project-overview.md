# 🚀 Automated CI/CD Pipeline using Jenkins, Docker, GitHub Webhooks & AWS EC2

## 📌 Project Overview

This project demonstrates a complete end-to-end CI/CD (Continuous Integration and Continuous Deployment) pipeline using Jenkins, Docker, GitHub Webhooks, Docker Hub, and AWS EC2.

Whenever a developer pushes new code to the GitHub repository, Jenkins automatically triggers the pipeline using a GitHub Webhook. The application is then built into a Docker image, pushed to Docker Hub, and deployed automatically on an AWS EC2 instance without any manual intervention.

This project eliminates the manual deployment process and ensures faster, reliable, and automated application delivery.

---

## 🎯 Project Objectives

- Automate application deployment using Jenkins.
- Build Docker images automatically after every GitHub push.
- Store Docker images on Docker Hub.
- Deploy the latest Docker image on AWS EC2.
- Reduce manual deployment effort.
- Demonstrate a real-world DevOps CI/CD workflow.

---

## 🛠️ Tech Stack

| Category | Technology |
|----------|------------|
| Cloud | AWS EC2 |
| CI/CD | Jenkins |
| Version Control | Git & GitHub |
| Containerization | Docker |
| Container Registry | Docker Hub |
| Automation | GitHub Webhook |
| Application | Node.js Todo Application |
| Operating System | Ubuntu Linux |

---

## ⚙️ CI/CD Workflow

```
Developer Pushes Code
        │
        ▼
GitHub Repository
        │
        ▼
GitHub Webhook
        │
        ▼
Jenkins Pipeline Triggered
        │
        ▼
Clone Repository
        │
        ▼
Build Docker Image
        │
        ▼
Login to Docker Hub
        │
        ▼
Push Docker Image
        │
        ▼
SSH into AWS EC2
        │
        ▼
Pull Latest Docker Image
        │
        ▼
Stop Old Container
        │
        ▼
Remove Old Container
        │
        ▼
Run New Docker Container
        │
        ▼
Application Updated Successfully
```

---

## 📂 Project Structure

```
automated-cicd-pipeline/
│
├── app/
├── jenkins/
├── screenshots/
├── docs/
├── Dockerfile
├── Jenkinsfile
├── README.md
└── .gitignore
```

---

## ✅ Features

- Fully automated CI/CD pipeline
- GitHub Webhook integration
- Docker image automation
- Automatic deployment on AWS EC2
- Zero manual deployment
- Blue Ocean pipeline visualization
- Docker Hub image management

---

## 📌 Outcome

After every GitHub push, the latest application is automatically built, pushed to Docker Hub, and deployed on the AWS EC2 server without requiring any manual steps.
