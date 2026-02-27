# 🚀 Production-Ready MEAN Stack Deployment
## DevOps CI/CD & Cloud Deployment Case Study

---

## 📌 Project Overview

This project demonstrates a fully containerized MEAN stack application deployed on AWS EC2 with automated CI/CD using GitHub Actions.

### The objective was to:

- Containerize frontend and backend services

- Enable service-to-service communication via Docker networking

- Implement reverse proxy routing

- Automate build, push, and deployment

- Achieve reliable zero-touch production updates

---

## 🎯 Deployment Objectives

- Fully Dockerized architecture

- CI/CD triggered on push to main

- Automatic image build and push to Docker Hub

- Secure SSH-based deployment to EC2

- Reverse proxy using Nginx

- Persistent MongoDB storage

- Production stability without manual intervention
  
---

## 🏗 Final Architecture

### Flow
<img width="640" src="https://github.com/user-attachments/assets/161958c7-6f1c-487f-a5af-a150a913dab0" />

---

## ⚙️ System Components

### 1️⃣ Frontend (Angular + Nginx)

- Multi-stage Docker build

- Static files served via Nginx

- SPA routing enabled via try_files

- Reverse proxy for /api requests

- Reverse Proxy Configuration

```
location /api/ {
    proxy_pass http://backend:8080/;
}
```

### Purpose:

- Internal container communication

- No CORS issues

- Clean production routing

---

## 2️⃣ Backend (Node.js + Express)

- REST API with CRUD operations

- MongoDB connection via service name

- Environment variable-based configuration

- Container memory isolation

---

## 3️⃣ Database (MongoDB)

-- Runs as isolated container

-- Persistent volume mounted

-- Automatically connected via Docker network

-- Data survives container restart

---

## 🔁 CI/CD Pipeline

- Implemented using GitHub Actions.

- Workflow Stages

- Build backend Docker image

- Build frontend Docker image

- Push images to Docker Hub

- SSH into EC2

- Pull updated images

- Restart containers

- Trigger

- Push to main branch.

---

## 📸 Implementation Evidence

🔹 CI/CD Configuration

<img width="800" src="https://github.com/user-attachments/assets/930582f6-e316-411c-ac94-b0d3331ac21d" />

🔹 Successful Pipeline Execution

<img width="800" src="https://github.com/user-attachments/assets/b021e095-3f93-4d98-98b6-08da53c55065" />

🔹 Docker Image Publishing

<img width="900" src="https://github.com/user-attachments/assets/075f67b4-8e15-4f6a-96b5-661ee8291b82" />

🔹 EC2 Deployment Verification

<img width="900" src="https://github.com/user-attachments/assets/6eb12452-830e-4cd8-8c0e-3576dbd53941" />

🔹 Production Application

<img width="900" src="https://github.com/user-attachments/assets/3c8606aa-6e5c-46b7-9efa-e497d3f7d417" />

---

## 🛠 Deployment Procedure

### Local Run
``` docker compose up --build ```

### EC2 Setup
```
sudo apt update
sudo apt install docker.io -y
sudo systemctl enable docker
sudo systemctl start docker
sudo usermod -aG docker ubuntu
```
#### Deploy:
```
docker-compose up -d
```
---

## 🧠 Debugging & Challenges Resolved

### During implementation, the following issues were identified and fixed:

- Docker daemon startup failure on Ubuntu 24.04

- Port conflicts with Jenkins

- MongoDB connection failures inside container

- Nginx misconfiguration causing restart loop

- Reverse proxy misrouting /api

### Final system is stable and redeployable.

---

## 📊 System Stability

### Feature	Status

- Automated Build	     ✅
- Image Versioning	     ✅
- Secure SSH Deployment	 ✅
- Reverse Proxy Routing	 ✅
- Persistent Storage	 ✅
- Zero Manual Deployment ✅
  
---

## 🌍 Live Application

```
http://98.92.202.93/

```

---

## 📈 Future Improvements

- Add HTTPS using Let's Encrypt

- Implement blue-green deployment strategy

- Add centralized logging (ELK stack)

- Add Prometheus monitoring

- Introduce staging environment

- Add Docker image version tagging
  
---

## Outcome

### Deployment:

- Fully automated

- Repeatable

- Production-ready

### Infrastructure:

- Containerized services

- Reverse proxy routing

- Cloud hosted

### DevOps Capability Demonstrated:

- CI/CD automation

- Cloud debugging

- Docker networking

- roduction troubleshooting
