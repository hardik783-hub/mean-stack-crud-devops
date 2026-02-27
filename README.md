🚀 MEAN Stack CRUD Application with Docker, CI/CD & AWS Deployment
📌 Project Overview

This project demonstrates a fully containerized MEAN Stack application deployed on AWS EC2 with automated CI/CD using GitHub Actions.

It showcases:

Dockerized Angular frontend (served via Nginx)

Dockerized Node.js + Express backend

MongoDB containerized database

Reverse proxy configuration using Nginx

Automated CI/CD pipeline

Production deployment to AWS EC2

🏗 Architecture Diagram

<img width="1024" height="1536" alt="architecture diagram" src="https://github.com/user-attachments/assets/161958c7-6f1c-487f-a5af-a150a913dab0" />

🛠 Tech Stack
Layer	Technology
Frontend	Angular
Backend	Node.js + Express
Database	MongoDB
Web Server	Nginx
Containerization	Docker
Orchestration	Docker Compose
CI/CD	GitHub Actions
Cloud	AWS EC2
📂 Project Structure
backend/         → Express API
frontend/        → Angular App + Nginx
docker-compose.yml
.github/workflows/deploy.yml
🔧 Local Setup Instructions
1️⃣ Clone Repository
git clone https://github.com/YOUR_USERNAME/mean-stack-crud.git
cd mean-stack-crud
2️⃣ Run Using Docker
docker compose up --build

Application will be available at:

http://localhost:3000

Backend:

http://localhost:5000

MongoDB:

mongodb://localhost:27017
☁️ AWS EC2 Deployment Guide
1️⃣ Launch EC2 Instance

Ubuntu 24.04

Allow inbound ports:

22 (SSH)

80 (HTTP)

2️⃣ Install Docker (Stable Method)
sudo apt update
sudo apt install docker.io -y
sudo systemctl enable docker
sudo systemctl start docker
sudo usermod -aG docker ubuntu
newgrp docker

Verify:

docker ps
3️⃣ Deploy Application
git clone https://github.com/YOUR_USERNAME/mean-stack-crud.git
cd mean-stack-crud
docker-compose up -d

Application accessible at:

http://<EC2-PUBLIC-IP>
🔁 CI/CD Pipeline Overview

The GitHub Actions workflow performs:

Build backend Docker image

Build frontend Docker image

Push images to Docker Hub

SSH into EC2

Pull latest images

Restart containers

Trigger:

Push to main branch

Workflow file:

.github/workflows/deploy.yml


🔹 1️⃣ CI/CD Configuration

GitHub Actions workflow YAML open
<img width="923" height="848" alt="image" src="https://github.com/user-attachments/assets/930582f6-e316-411c-ac94-b0d3331ac21d" />


Secrets configuration page
<img width="573" height="329" alt="image" src="https://github.com/user-attachments/assets/3c6cec8c-77d6-4459-b9b5-c7adf0b3edfa" />


🔹 2️⃣ Successful CI/CD Execution

<img width="900" height="729" alt="image" src="https://github.com/user-attachments/assets/b021e095-3f93-4d98-98b6-08da53c55065" />


🔹 3️⃣ Docker Image Build & Push


Docker Hub repository
<img width="1859" height="858" alt="image" src="https://github.com/user-attachments/assets/075f67b4-8e15-4f6a-96b5-661ee8291b82" />



🔹 4️⃣ EC2 Deployment

<img width="1462" height="117" alt="image" src="https://github.com/user-attachments/assets/6eb12452-830e-4cd8-8c0e-3576dbd53941" />


🔹 5️⃣ Application Working UI

<img width="952" height="841" alt="image" src="https://github.com/user-attachments/assets/3c8606aa-6e5c-46b7-9efa-e497d3f7d417" />


🔹 6️⃣ Nginx Reverse Proxy Configuration

<img width="1541" height="495" alt="image" src="https://github.com/user-attachments/assets/f64f0df7-356c-46cd-8cde-77fa98369d3f" />


🔐 Nginx Reverse Proxy Configuration

Example:

location /api/ {
    proxy_pass http://backend:8080/;
}

This allows frontend to communicate with backend within Docker network.

📦 Docker Images

Available on Docker Hub:

docker pull hardikgarg000/mean-crud-backend
docker pull hardikgarg000/mean-crud-frontend

🎯 DevOps Highlights

Infrastructure as Code using Docker Compose

Automated CI/CD pipeline

Container networking

Reverse proxy configuration

Secure SSH deployment

Cloud infrastructure setup

🌍 Live Application
http://98.92.202.93/
🏆 Key Learning Outcomes

Docker image creation and optimization

CI/CD automation with GitHub Actions

Cloud deployment on AWS EC2

Nginx reverse proxy configuration

Debugging real-world infrastructure issues

🚀 Production Features Implemented

✔ Containerized services
✔ Persistent MongoDB storage
✔ CI/CD automation
✔ Cloud deployment
✔ Reverse proxy routing

