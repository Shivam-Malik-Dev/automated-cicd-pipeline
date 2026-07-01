# ☁️ AWS Infrastructure Setup

## 📌 Overview

This document explains the AWS infrastructure setup used to host the CI/CD pipeline. The complete environment is deployed on an Ubuntu-based Amazon EC2 instance where Jenkins, Docker, and the Node.js Todo application are configured.

---

# Step 1: Launch an EC2 Instance

An Ubuntu EC2 instance was launched to host Jenkins and Docker. This server is responsible for building Docker images and deploying the application automatically.

### Instance Configuration

| Property | Value |
|----------|-------|
| Cloud Provider | AWS |
| Service | EC2 |
| Operating System | Ubuntu |
| Instance Type | t3.small |
| Region | ap-south-1 (Mumbai) |

### Screenshot

![AWS EC2 Instance](../screenshots/01-aws-ec2-instance.png)

---

# Step 2: Configure Security Group

The security group was configured to allow incoming traffic for SSH, Jenkins Dashboard, and the deployed Node.js application.

### Inbound Rules

| Port | Purpose |
|------|----------|
| 22 | SSH Access |
| 8080 | Jenkins Dashboard |
| 8000 | Node.js Application |

### Screenshot

![Security Group Configuration](../screenshots/02-security-group-configuration.png)

---

# Step 3: Install Docker

Docker was installed on the EC2 instance to containerize the application and manage deployments through Docker images.

### Verify Docker Installation

```bash
docker --version
```

### Screenshot

![Docker Installation](../screenshots/03-docker-installation-verification.png)

---

# Step 4: Verify Jenkins Service

After installing Jenkins, the service was verified to ensure it was running successfully before configuring the CI/CD pipeline.

### Check Jenkins Status

```bash
sudo systemctl status jenkins
```

### Screenshot

![Jenkins Service Running](../screenshots/04-jenkins-service-running.png)

---

# Step 5: Grant Docker Permission to Jenkins

To allow Jenkins to execute Docker commands without permission issues, the Jenkins user was added to the Docker group.

### Command

```bash
sudo usermod -aG docker jenkins
```

After updating the group membership, Jenkins was restarted.

```bash
sudo systemctl restart jenkins
```

### Screenshot

![Jenkins Docker Permission](../screenshots/05-add-jenkins-to-docker-group.png)

---

# ✅ Infrastructure Ready

The AWS server is now fully configured with:

- Ubuntu EC2 Instance
- Docker Installed
- Jenkins Installed
- Docker Permission Configured
- Required Security Group Rules
- Ready for CI/CD Pipeline Deployment
