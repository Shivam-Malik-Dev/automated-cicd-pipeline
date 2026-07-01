# ⚙️ Jenkins Installation & Configuration

## 📌 Overview

Jenkins was used as the Continuous Integration (CI) server to automate the build and deployment process. It continuously monitors the GitHub repository, builds a new Docker image whenever code is pushed, and deploys the updated application automatically.

---

# Step 1: Verify Jenkins Installation

After installing Jenkins on the EC2 instance, the Jenkins service was verified to ensure it was running correctly.

### Check Jenkins Status

```bash
sudo systemctl status jenkins
```

### Screenshot

![Jenkins Service Running](../screenshots/04-jenkins-service-running.png)

---

# Step 2: Access the Jenkins Dashboard

The Jenkins dashboard was accessed using the EC2 public IP on port **8080**.

```
http://<EC2-PUBLIC-IP>:8080
```

From the dashboard, a new Pipeline project was created.

### Screenshot

![Jenkins Dashboard](../screenshots/06-jenkins-dashboard.png)

---

# Step 3: Configure Docker Permissions

Since Jenkins executes Docker commands during the pipeline, the Jenkins user was added to the Docker group.

### Command

```bash
sudo usermod -aG docker jenkins
sudo systemctl restart jenkins
```

### Verify Group Membership

```bash
groups jenkins
```

### Screenshot

![Docker Permission](../screenshots/05-add-jenkins-to-docker-group.png)

---

# Step 4: Configure Docker Hub Credentials

To securely push Docker images, Docker Hub credentials were stored inside Jenkins Credentials Manager instead of hardcoding the username and password inside the pipeline.

Credential Details:

| Property | Value |
|----------|-------|
| Type | Username with Password |
| ID | dockerHub |
| Username | Docker Hub Username |
| Password | Docker Hub Personal Access Token |

This credential is accessed securely inside the Jenkins Pipeline using the **withCredentials()** block.

---

# Step 5: Create Jenkins Pipeline

A new Pipeline job named **Automated CI-CD Pipeline** was created.

Pipeline Features:

- Clone GitHub Repository
- Build Docker Image
- Login to Docker Hub
- Push Docker Image
- Deploy Updated Container

The pipeline was written using Declarative Pipeline syntax.

---

# Step 6: Blue Ocean Visualization

Blue Ocean provides a modern visualization of the Jenkins Pipeline. It clearly displays each stage of the CI/CD workflow and makes build monitoring much easier.

Pipeline Stages:

- Clone Repository
- Build Docker Image
- Login to Docker Hub
- Push Docker Image
- Deploy Application

### Screenshot

![Blue Ocean Pipeline](../screenshots/09-blueocean-pipeline-view.png)

---

# Step 7: Verify Successful Build

After the pipeline execution, Jenkins completed all stages successfully without any manual intervention.

The pipeline automatically:

- Cloned the latest source code
- Built the Docker image
- Pushed the image to Docker Hub
- Deployed the latest container on AWS EC2

### Screenshot

![Pipeline Success](../screenshots/08-jenkins-pipeline-job.png)

---

# ✅ Result

Jenkins is now fully configured to automate the complete build and deployment workflow. Every new GitHub push triggers the pipeline automatically, ensuring the latest version of the application is built, published, and deployed without manual effort.
