# k8s-multi-tier-app
My very own K8s project 


THIS FILE Explains what the project is, tools used, how to run it

# Multi-Tier Application Deployment on Kubernetes

This project demonstrates the deployment of a simple multi-tier web application on a self-managed Kubernetes cluster (using `kubeadm`). It includes a frontend (NGINX) and a backend (MongoDB), both containerized using Docker and deployed using Kubernetes manifests.

---

Technologies Used

- Kubernetes (deployed via `kubeadm`)
- Docker
- NGINX (Frontend)
- MongoDB (Backend)
- Kubernetes Services, Deployments, ConfigMaps, Secrets
- NGINX Ingress Controller

---


---

##  How to Deploy

> This project assumes you already have a running Kubernetes cluster (via `kubeadm`, Minikube, etc.)

### 1. Clone the Repository
```bash
git clone https://github.com/qasim22/k8s-multi-tier-app.git
cd k8s-multi-tier-app/

```
AND THEN RUN:

```bash
kubectl apply -f secret.yaml
kubectl apply -f configmap.yaml
kubectl apply -f backend-deployment.yaml
kubectl apply -f backend-service.yaml
kubectl apply -f frontend-deployment.yaml
kubectl apply -f frontend-service.yaml
kubectl apply -f ingress.yaml
```

OR SIMPLY RUN TO APPLY ALL FILE at once:
```bash
kubectl apply -f .
```

## Accessing the Application

If you're using Minikube, run:
```bash
minikube tunnel
```

Then access:
```bash
http://yourapp.local
```
⚠️ Make sure to update your /etc/hosts file






