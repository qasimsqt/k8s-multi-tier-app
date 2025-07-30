# k8s-multi-tier-app

A beginner-friendly project that demonstrates the deployment of a simple multi-tier web application using Kubernetes (via `kubeadm`). It features an NGINX frontend and a MongoDB backend, containerized with Docker and orchestrated with Kubernetes manifests.

---

##  Technologies Used

- Kubernetes (kubeadm)
- Docker
- NGINX (Frontend)
- MongoDB (Backend)
- Kubernetes Services, Deployments, ConfigMaps, Secrets
- NGINX Ingress Controller

---

##  How to Deploy

> This project assumes you have a running Kubernetes cluster (set up with `kubeadm`).

### 1. Clone the Repository

```bash
git clone https://github.com/qasim22/k8s-multi-tier-app.git
cd k8s-multi-tier-app


```
 ## Apply Kubernetes Manifests
Apply them one by one:

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

## Accessing the Application (kubeadm setup)

Make sure you have NGINX Ingress Controller installed and your nodes are accessible.

Install NGINX Ingress Controller

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.9.4/deploy/static/provider/baremetal/deploy.yaml

```
Edit your /etc/hosts file

```bash
sudo vim /etc/hosts
```

Add the following line (replace with your node IP):

```bash
192.168.1.100 yourapp.local
```

### Access the app
Open your browser and go to:

```bash
http://yourapp.local
```







## Learning Outcomes
Set up a Kubernetes cluster using kubeadm

Deployed and managed multi-tier containerized workloads

Used ConfigMaps and Secrets for environment management

Implemented Ingress routing with NGINX

Practiced Infrastructure-as-Code with declarative YAML







