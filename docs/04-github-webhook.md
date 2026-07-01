# 🔗 GitHub Webhook Integration

## 📌 Overview

GitHub Webhooks were configured to automatically notify Jenkins whenever new code is pushed to the GitHub repository.

Instead of manually clicking the **Build Now** button, every push to the **main** branch automatically triggers the Jenkins pipeline.

This enables a fully automated Continuous Integration (CI) workflow.

---

# Step 1: Configure GitHub Webhook

The webhook was created inside the GitHub repository settings.

Navigation:

```
Repository
    ↓
Settings
    ↓
Webhooks
    ↓
Add Webhook
```

The webhook sends an HTTP POST request to the Jenkins webhook endpoint whenever new code is pushed.

### Payload URL

```
http://<EC2-PUBLIC-IP>:8080/github-webhook/
```

### Content Type

```
application/json
```

### Events

```
Just the push event
```

### Screenshot

![GitHub Webhook Configuration](../screenshots/07-github-webhook-configuration.png)

---

# Step 2: Enable GitHub Trigger in Jenkins

Inside the Jenkins Pipeline job, the following trigger was enabled:

```
GitHub hook trigger for GITScm polling
```

This allows Jenkins to listen for incoming webhook events from GitHub.

---

# Step 3: Push Source Code

The application source code was modified locally.

The updated code was committed and pushed to GitHub.

```bash
git add .

git commit -m "Updated application heading"

git push origin main
```

No manual interaction with Jenkins was required.

---

# Step 4: Automatic Pipeline Execution

As soon as GitHub received the push, it immediately sent a webhook request to Jenkins.

The Jenkins pipeline started automatically and executed all stages successfully.

Pipeline stages:

- Clone Repository
- Build Docker Image
- Login to Docker Hub
- Push Docker Image
- Deploy Application

### Screenshot

![Blue Ocean Pipeline](../screenshots/09-blueocean-pipeline-view.png)

---

# Step 5: Automatic Application Deployment

After the pipeline completed successfully:

- The latest Docker image was pushed to Docker Hub.
- The running container was stopped.
- The old container was removed.
- A new container was started using the latest Docker image.

No manual deployment commands were executed.

---

# Step 6: Verify Updated Application

Refreshing the browser displayed the updated application automatically.

This confirms that the latest source code was successfully deployed through the CI/CD pipeline.

### Screenshot

![Updated Application](../screenshots/13-auto-deployment-after-github-push.png)

---

# ✅ Result

The complete deployment process is fully automated.

```
Developer
      │
      ▼
Git Push
      │
      ▼
GitHub Webhook
      │
      ▼
Jenkins Pipeline
      │
      ▼
Docker Image Build
      │
      ▼
Docker Hub
      │
      ▼
Deploy on AWS EC2
      │
      ▼
Updated Application
```

This implementation removes manual deployment steps and demonstrates a production-style CI/CD workflow using GitHub, Jenkins, Docker, Docker Hub, and AWS EC2.