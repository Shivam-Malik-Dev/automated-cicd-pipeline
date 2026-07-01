# 🚀 Automated CI/CD Pipeline for Node.js Todo Application

<p align="center">

![GitHub last commit](https://img.shields.io/github/last-commit/Shivam-Malik-Dev/node-todo-app?style=flat-square)
![GitHub repo size](https://img.shields.io/github/repo-size/Shivam-Malik-Dev/node-todo-app?style=flat-square)
![GitHub stars](https://img.shields.io/github/stars/Shivam-Malik-Dev/node-todo-app?style=flat-square)
![GitHub forks](https://img.shields.io/github/forks/Shivam-Malik-Dev/node-todo-app?style=flat-square)

</p>

<p align="center">

![AWS](https://img.shields.io/badge/AWS-EC2-orange?style=for-the-badge&logo=amazonaws)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white)
![Docker Hub](https://img.shields.io/badge/Docker-Hub-2496ED?style=for-the-badge&logo=docker)
![NodeJS](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-Server-E95420?style=for-the-badge&logo=ubuntu)

</p>

---

# 📌 Project Overview

This project demonstrates a complete **End-to-End Automated CI/CD Pipeline** for a **Node.js Todo Application** using modern DevOps tools and cloud infrastructure.

Whenever a developer pushes code to GitHub, Jenkins automatically triggers the pipeline through GitHub Webhooks, builds a Docker image, pushes it to Docker Hub, and deploys the latest application version on an AWS EC2 instance without any manual intervention.

This project follows a production-style Continuous Integration and Continuous Deployment (CI/CD) workflow.

---

# 🎯 Project Objectives

- Automate application deployment
- Eliminate manual deployment process
- Build Docker images automatically
- Push images to Docker Hub
- Deploy latest application on AWS EC2
- Demonstrate an end-to-end DevOps workflow
- Learn production-style CI/CD implementation

---

# 🏗️ Architecture Diagram

<p align="center">

<img src="architecture/architecture.png" width="1000">

</p>

---

# ⚙️ Tech Stack

| Category | Technology |
|-----------|------------|
| Version Control | Git & GitHub |
| CI/CD | Jenkins |
| Containerization | Docker |
| Container Registry | Docker Hub |
| Cloud Platform | AWS EC2 |
| Operating System | Ubuntu Linux |
| Application | Node.js |
| Automation | GitHub Webhooks |

---

# ⭐ Key Features

- Automated CI/CD Pipeline
- GitHub Webhook Integration
- Jenkins Declarative Pipeline
- Dockerized Application
- Docker Hub Image Registry
- AWS EC2 Deployment
- Automatic Container Replacement
- Zero Manual Deployment
- Production-style Workflow
- End-to-End Automation

---

# 📊 Project Metrics

| Metric | Value |
|---------|-------|
| CI/CD Tool | Jenkins |
| Cloud Platform | AWS EC2 |
| Container Platform | Docker |
| Container Registry | Docker Hub |
| Application | Node.js Todo App |
| Pipeline Stages | 5 |
| Trigger Method | GitHub Webhook |
| Build Time | ~40 Seconds |
| Deployment Time | ~15 Seconds |
| Deployment Type | Fully Automated |
| Infrastructure | Ubuntu EC2 |
| Availability | 24×7 |

---

# 📂 Project Structure

```text
automated-cicd-pipeline/

│
├── app/
│   ├── app.js
│   ├── Dockerfile
│   ├── package.json
│   └── ...
│
├── architecture/
│   └── architecture.png
│
├── docs/
│   ├── 01-project-overview.md
│   ├── 02-aws-setup.md
│   ├── 03-jenkins-installation.md
│   ├── 04-github-webhook.md
│   ├── 05-cicd-pipeline.md
│   ├── 06-deployment.md
│   └── 07-troubleshooting.md
│
├── screenshots/
│
├── Jenkinsfile
│
├── .gitignore
│
├── LICENSE
│
└── README.md
```

---

# 🔄 CI/CD Pipeline Workflow

```text
Developer

        │
        ▼

Push Code to GitHub

        │
        ▼

GitHub Webhook Trigger

        │
        ▼

Jenkins Pipeline Starts

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

Stop Existing Container

        │
        ▼

Run New Docker Container

        │
        ▼

Application Live
```

---

# ⚡ Jenkins Pipeline Stages

| Stage | Description |
|---------|-------------|
| Clone Repository | Fetch latest source code from GitHub |
| Build Docker Image | Build Docker image using Dockerfile |
| Login Docker Hub | Authenticate Docker Hub |
| Push Docker Image | Upload latest Docker image |
| Deploy on AWS EC2 | Pull latest image and restart container |

---

# 🚀 Deployment Workflow

1. Developer pushes code to GitHub.

2. GitHub Webhook automatically triggers Jenkins.

3. Jenkins clones the latest repository.

4. Docker image is built.

5. Jenkins logs into Docker Hub.

6. Docker image is pushed to Docker Hub.

7. AWS EC2 pulls the latest image.

8. Existing container is stopped.

9. Old container is removed.

10. New container starts automatically.

11. Updated application becomes live.

---

# 📸 Project Screenshots

## AWS EC2 Instance

![](screenshots/ec2-instance.png)

---

## Security Group Configuration

![](screenshots/security-group.png)

---

## Jenkins Dashboard

![](screenshots/jenkins-dashboard.png)

---

## Jenkins Pipeline Execution

![](screenshots/jenkins-blueocean.png)

---

## Docker Hub Repository

![](screenshots/dockerhub.png)

---

## Running Docker Container

![](screenshots/docker-running.png)

---

## Live Application

![](screenshots/application.png)

---

# 📖 Documentation

Complete project documentation is available inside the **docs** directory.

| Document | Description |
|-----------|-------------|
| 01-project-overview | Project Introduction |
| 02-aws-setup | AWS EC2 Configuration |
| 03-jenkins-installation | Jenkins Installation Guide |
| 04-github-webhook | GitHub Webhook Setup |
| 05-cicd-pipeline | Jenkins Pipeline Configuration |
| 06-deployment | Deployment Process |
| 07-troubleshooting | Common Issues & Solutions |

---

# 🎯 Skills Demonstrated

- Continuous Integration (CI)
- Continuous Deployment (CD)
- Jenkins Pipeline
- Docker
- Docker Hub
- AWS EC2
- Git & GitHub
- GitHub Webhooks
- Linux Administration
- Shell Commands
- DevOps Automation

---

# 🚀 Future Enhancements

- Kubernetes Deployment
- Helm Charts
- Terraform Infrastructure
- SonarQube Integration
- Trivy Image Scanning
- Prometheus Monitoring
- Grafana Dashboard
- ArgoCD GitOps Deployment
- Multi-Environment Deployment
- Slack Notification Integration

---

# 👨‍💻 Author

## Shivam Malik

**Cloud & DevOps Engineer**

### Connect with me

- GitHub: https://github.com/Shivam-Malik-Dev
- LinkedIn: https://www.linkedin.com/in/shivam-malik-59b13a29b/

---

# ⭐ Support

If you found this project useful, consider giving it a ⭐ on GitHub.

It motivates me to build and share more DevOps projects.

---