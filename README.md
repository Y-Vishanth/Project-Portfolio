# Project-Portfolio
This project demonstrates a complete CI/CD pipeline for deploying a personal portfolio website using Amazon EC2, Docker, Jenkins, Git, and Linux. The goal is to showcase automation skills in DevOps by building, containerizing, and deploying a web application directly from source code changes.

# 🚀 Dockerized Portfolio Website with Jenkins CI/CD on AWS EC2

## 📌 Project Overview

This project demonstrates a complete DevOps workflow:

- Static Portfolio Website (HTML + CSS)
- Containerized using Docker (Nginx)
- CI/CD Pipeline using Jenkins
- Hosted on AWS EC2 (Ubuntu)

Whenever code is pushed to GitHub, Jenkins automatically:
1. Pulls the latest code
2. Builds a Docker image
3. Stops the old container
4. Deploys the updated container

---

##** 🏗️ Architecture**

Developer → GitHub → Jenkins → Docker → AWS EC2 → Browser

---

## 🛠️** Tech Stack**

- Linux (Ubuntu EC2)
- Git & GitHub
- Docker
- Jenkins (Pipeline)
- AWS EC2
- Nginx

---

## **📂 Project Structure**


portfolio/
│── index.html
│── style.css
│── Dockerfile
│── Jenkinsfile

## 🌐 Deployment Flow

1. Code pushed to GitHub
2. Jenkins pulls the repository
3. Docker image is built
4. Old container is removed
5. New container is deployed
6. Website becomes live on EC2 Public IP

---

## 🔐 Security Configuration

AWS Security Group Rules:

* SSH (22) → My IP only
* HTTP (80) → 0.0.0.0/0
* Jenkins (8080) → 0.0.0.0/0

## 🧪 Verification Steps

**Check running containers:**
docker ps

**Test locally:**
curl http://localhost

**Access from browser:**
http://<EC2-PUBLIC-IP>

## 🧠 Key Learnings

* Jenkins inside Docker requires Docker socket mounting
* GitHub authentication requires Personal Access Token
* EC2 Security Groups control inbound traffic
* CI/CD automates containerized deployments

## 📊 Architecture Diagram


```
            ┌───────────────┐
            │   Developer   │
            │  (Git Push)   │
            └───────┬───────┘
                    │
                    ▼
            ┌───────────────┐
            │    GitHub     │
            │   Repository  │
            └───────┬───────┘
                    │
                    ▼
            ┌───────────────┐
            │    Jenkins    │
            │   (Pipeline)  │
            └───────┬───────┘
                    │
                    ▼
            ┌───────────────┐
            │     Docker    │
            │  Build Image  │
            └───────┬───────┘
                    │
                    ▼
            ┌───────────────┐
            │   EC2 Server  │
            │  Run Container│
            └───────┬───────┘
                    │
                    ▼
            ┌───────────────┐
            │   Browser     │
            │  Public IP    │
            └───────────────┘
```

```

---

```

