# 🚀 CI/CD Pipeline Workflow

## 📌 Overview

This project implements a fully automated CI/CD pipeline using **GitHub**, **Jenkins**, **Docker**, **Docker Hub**, and **AWS EC2**.

Whenever a developer pushes code to the GitHub repository, Jenkins automatically starts the pipeline, builds a new Docker image, pushes it to Docker Hub, and deploys the latest version of the application on an AWS EC2 instance.

The entire deployment process is completed without any manual intervention.

---

# Pipeline Architecture

```
Developer
     │
     ▼
Git Push
     │
     ▼
GitHub Repository
     │
     ▼
GitHub Webhook
     │
     ▼
Jenkins Pipeline
     │
     ├───────────────┐
     │               │
     ▼               ▼
Clone Repository   Build Docker Image
                     │
                     ▼
              Login to Docker Hub
                     │
                     ▼
             Push Docker Image
                     │
                     ▼
             Pull Latest Image
                     │
                     ▼
         Stop Running Container
                     │
                     ▼
          Remove Old Container
                     │
                     ▼
         Run Updated Container
                     │
                     ▼
          Application Available
```

---

# Jenkins Pipeline Stages

The pipeline consists of the following stages.

---

## Stage 1 — Clone Repository

The latest source code is cloned from the GitHub repository.

Purpose:

- Always build the latest code.
- Keep Jenkins workspace updated.

---

## Stage 2 — Build Docker Image

A new Docker image is created using the application's Dockerfile.

Command:

```bash
docker build -t shivammalikdocker/todo-app:latest .
```

Purpose:

- Package the application into a portable container image.
- Ensure every deployment uses a fresh image.

---

## Stage 3 — Login to Docker Hub

Jenkins securely authenticates with Docker Hub using stored credentials.

The Docker Hub username and Personal Access Token are stored in Jenkins Credentials Manager and accessed using the `withCredentials()` block.

Purpose:

- Avoid hardcoding credentials.
- Follow secure DevOps practices.

---

## Stage 4 — Push Docker Image

The newly created Docker image is uploaded to Docker Hub.

Command:

```bash
docker push shivammalikdocker/todo-app:latest
```

Purpose:

- Store the latest application image.
- Make it available for deployment.

---

## Stage 5 — Deploy Application

The deployment stage performs the following operations:

- Pull the latest Docker image.
- Stop the currently running container.
- Remove the old container.
- Start a new container using the latest image.

Commands:

```bash
docker pull shivammalikdocker/todo-app:latest

docker stop todo-app || true

docker rm todo-app || true

docker run -d \
  --name todo-app \
  -p 8000:8000 \
  shivammalikdocker/todo-app:latest
```

Purpose:

- Replace the running application with the latest version.
- Ensure zero manual deployment.

---

# Blue Ocean Pipeline

Blue Ocean provides a modern graphical representation of the Jenkins Pipeline.

Each stage can be monitored independently, making it easy to identify failures and verify successful deployments.

### Screenshot

![Blue Ocean Pipeline](../screenshots/09-blueocean-pipeline-view.png)

---

# Pipeline Result

Whenever a developer pushes new code:

- Jenkins automatically starts the pipeline.
- A new Docker image is built.
- The image is uploaded to Docker Hub.
- The latest container is deployed on AWS EC2.
- The updated application becomes available automatically.

No manual deployment commands are required.

---

# Benefits of this Pipeline

- Fully automated deployment
- Eliminates manual deployment errors
- Faster release process
- Consistent deployments
- Secure Docker Hub authentication
- Production-style CI/CD workflow
- Easy to scale for larger applications

---

# Final Workflow

```
Code Change
      │
      ▼
Git Commit
      │
      ▼
Git Push
      │
      ▼
GitHub Webhook
      │
      ▼
Jenkins
      │
      ▼
Docker Build
      │
      ▼
Docker Hub
      │
      ▼
AWS EC2
      │
      ▼
Updated Application
```

---

# Conclusion

This project demonstrates a complete CI/CD implementation using Jenkins, Docker, GitHub Webhooks, Docker Hub, and AWS EC2. The pipeline automates the complete software delivery process, allowing application updates to be deployed automatically whenever new code is pushed to GitHub.
