# 🚀 Attendance Marking System - Docker & Kubernetes Deployment

## 📌 Project Overview

This project is a simple **Attendance Marking Web Application** built using HTML, CSS, and JavaScript, containerized with Docker and deployed on Kubernetes using Minikube.

It demonstrates core DevOps concepts like containerization, orchestration, service exposure, image versioning, and debugging in Kubernetes.

---

## 🛠️ Tech Stack

- HTML, CSS, JavaScript
- Docker (Nginx-based container)
- Kubernetes (Deployment & Service)
- Minikube (Local Kubernetes Cluster)
- Git & GitHub

---

## 🏗️ Project Architecture


Frontend (HTML App)
↓
Docker Image (attendance-app:v1 / v2 / v3)
↓
Kubernetes Deployment (3 replicas)
↓
NodePort Service
↓
Minikube Tunnel
↓
Browser


---

## 📁 Project Structure


attendance-k8s-project/
│
├── index.html
├── Dockerfile
├── attendance-deployment.yaml
├── attendance-service.yaml
└── README.md


---

## 🐳 Docker Setup

### 1️⃣ Build Docker Image


docker build -t attendance-app:v1 .


### 2️⃣ Load Image into Minikube


minikube image load attendance-app:v1


---

## ☸️ Kubernetes Deployment

### 1️⃣ Start Minikube


minikube start --driver=docker


### 2️⃣ Apply Deployment & Service


kubectl apply -f attendance-deployment.yaml
kubectl apply -f attendance-service.yaml


### 3️⃣ Verify Pods & Services


kubectl get pods
kubectl get svc
kubectl get endpoints


---

## 🌐 Access Application


minikube service attendance-service


OR


kubectl port-forward svc/attendance-service 8080:80


Then open:


http://localhost:8080


---

## 🔄 Image Versioning

When updating UI:


docker build -t attendance-app:v2 .
minikube image load attendance-app:v2


Update image in `attendance-deployment.yaml`:


image: attendance-app:v2


Restart deployment:


kubectl rollout restart deployment attendance-deployment


---

## 🧠 Key Learnings

- Difference between Pod and Deployment
- Service communication using Labels & Selectors
- Debugging `ErrImageNeverPull`
- Understanding Kubernetes Endpoints
- NodePort vs Minikube Tunnel networking
- Docker image version management

---

## 🐛 Common Issues Faced & Fixed

- Service not connecting due to label mismatch
- ImagePull errors due to `imagePullPolicy`
- Docker driver networking issues on Windows
- Browser cache not reflecting updated UI

---

## 📸 Demo Screenshot

(Add screenshots here)

---

## 👨‍💻 Author

Akash V  
Aspiring DevOps Engineer  

---

## 📢 Future Improvements

- Add backend (Node.js / Express)
- Store attendance in database
- Deploy on AWS EKS
- Add CI/CD pipeline
- Use Ingress instead of NodePort

---

#DevOps #Docker #Kubernetes #Minikube #CloudComputing
🔥 After Adding This

Run:

git add README.md
git commit -m "Added professional README"
git push
