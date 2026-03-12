# Kubernetes MongoDB Deployment

This project demonstrates how to deploy a **containerized application stack in a Kubernetes cluster** using **MongoDB** as the database and **Mongo Express** as the web-based database administration interface.

The project focuses on understanding **Kubernetes core concepts such as Deployments, Services, ConfigMaps, and Secrets**, while enabling communication between application components within the cluster.

---

## 🚀 Project Overview

In modern cloud-native environments, applications are commonly deployed using container orchestration platforms. This project shows how to deploy and manage a **multi-container application architecture** using Kubernetes.

The architecture includes:

- MongoDB database running inside the cluster
- Mongo Express for database management
- Kubernetes resources for configuration and service communication

---

## 🏗 Architecture

```
User
 │
 ▼
Mongo Express (Web Interface)
 │
 ▼
Kubernetes Service
 │
 ▼
MongoDB Database
```

Mongo Express connects to MongoDB internally within the Kubernetes network.

---

## ⚙️ Technologies Used

- Kubernetes
- Docker
- MongoDB
- Mongo Express
- YAML configuration files

---

## 📂 Project Structure

```
kubernetes-mongodb-deployment/
│
├── mongo-configmap.yaml
├── mongo-secret.yaml
├── mongodb-deployment.yaml
├── mongodb-service.yaml
├── mongo-express-deployment.yaml
├── mongo-express-service.yaml
│
└── README.md
```

---

## 🔑 Kubernetes Components Used

### ConfigMap
Stores MongoDB configuration variables.

Example:
```
mongo-configmap.yaml
```

---

### Secret
Stores sensitive data such as database username and password.

Example:
```
mongo-secret.yaml
```

---

### Deployment
Defines the MongoDB and Mongo Express container deployments.

Examples:
```
mongodb-deployment.yaml
mongo-express-deployment.yaml
```

---

### Service
Allows communication between MongoDB and Mongo Express within the Kubernetes cluster.

Examples:
```
mongodb-service.yaml
mongo-express-service.yaml
```

---

## 🛠 Setup Instructions

### 1 Clone the Repository

```bash
git clone https://github.com/yourusername/kubernetes-mongodb-deployment.git
cd kubernetes-mongodb-deployment
```

---

### 2 Apply Kubernetes Configuration Files

Create the resources in the following order:

```bash
kubectl apply -f mongo-secret.yaml
kubectl apply -f mongo-configmap.yaml
kubectl apply -f mongodb-deployment.yaml
kubectl apply -f mongodb-service.yaml
kubectl apply -f mongo-express-deployment.yaml
kubectl apply -f mongo-express-service.yaml
```

---

### 3 Verify Deployments

```bash
kubectl get pods
kubectl get services
```

---

### 4 Access Mongo Express

If using NodePort:

```
http://<node-ip>:<nodeport>
```

If using port forwarding:

```bash
kubectl port-forward service/mongo-express-service 8081:8081
```

Then open:

```
http://localhost:8081
```

---

## 📊 Learning Outcomes

Through this project, I gained practical experience with:

- Deploying containerized applications in Kubernetes
- Managing application configuration with ConfigMaps
- Handling sensitive data using Kubernetes Secrets
- Creating Deployments and Services
- Understanding internal cluster networking
- Managing multi-container cloud-native architectures

---

## 🔮 Future Improvements

Possible improvements for this project include:

- Add persistent storage using Kubernetes Persistent Volumes
- Implement Helm charts for easier deployment
- Deploy the cluster in a cloud environment
- Add monitoring with Prometheus and Grafana
- Implement CI/CD pipeline for automated deployment

---

## 👨‍💻 Author

Ravindu Dasanayaka

Software Engineering Graduate  
Cloud | DevOps | Backend Development | Linux Systems

---

## 📜 License

This project is open source and available under the MIT License.
