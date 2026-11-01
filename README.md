# ☸️ Kubernetes Deployment Basics

A hands-on project exploring fundamental Kubernetes concepts through deploying and managing a containerised Node.js application using IBM Cloud Kubernetes lab environments.

This project demonstrates how to deploy applications, manage multiple replicas, expose applications through Kubernetes Services, and understand basic load balancing.

## 🚀 Project Overview

The project uses a simple Node.js application running inside a Docker container. The application returns a response containing the hostname of the Pod handling the request.

The application is deployed to Kubernetes using Pods and Deployments, with a Service providing stable network access to the application replicas.

## 🛠️ Technologies & Tools

- **Kubernetes** – Container orchestration and workload management
- **Docker** – Containerisation of the Node.js application
- **Node.js** – Backend application
- **Express.js** – Web application framework
- **IBM Cloud Container Registry** – Docker image storage
- **kubectl** – Kubernetes command-line tool
- **YAML** – Kubernetes resource configuration
- **Git & GitHub** – Version control and project management

## 🏗️ Kubernetes Architecture

The application follows this basic deployment architecture:

```text
             Docker Image
                  |
                  v
       IBM Cloud Container Registry
                  |
                  v
          Kubernetes Deployment
                  |
                  v
             ReplicaSet
                  |
          +-------+-------+
          |       |       |
          v       v       v
        Pod 1   Pod 2   Pod 3
          |       |       |
          +-------+-------+
                  |
                  v
          Kubernetes Service
               ClusterIP
                  |
                  v
          Application Access
```

The Deployment maintains the desired number of application replicas, while the Service provides a stable endpoint and distributes traffic among eligible Pods.

## 📚 Concepts Implemented

### 1. Docker Image Creation

- Created a Dockerfile for the Node.js application.
- Built a Docker image using `docker build`.
- Tagged and pushed the image to IBM Cloud Container Registry.
- Configured Kubernetes image pull credentials.

### 2. Kubernetes Pods

- Created a Pod using the imperative `kubectl run` command.
- Created a Pod using a declarative YAML manifest.
- Inspected Pod status and application logs.

### 3. Kubernetes Deployments

- Created a Deployment using YAML configuration.
- Configured three application replicas.
- Used labels and selectors to associate Pods with their Deployment.
- Explored how Deployments and ReplicaSets maintain the desired number of Pods.

### 4. Kubernetes Services

- Exposed the Deployment using `kubectl expose`.
- Created a ClusterIP Service.
- Explored how Services provide stable network access to changing Pod instances.
- Inspected Service configuration and endpoints.

### 5. Load Balancing

- Tested application access through the Kubernetes Service.
- Sent multiple HTTP requests using `curl`.
- Observed different Pod hostnames responding to requests.
- Explored how Kubernetes Service networking distributes connections across available Pod endpoints.

## 💻 Useful Kubernetes Commands

**Create a Pod**

```bash
kubectl run hello-world --image=<IMAGE_NAME>
```

**Create resources from YAML**

```bash
kubectl create -f hello-world-create.yaml
```

**Apply a Deployment configuration**

```bash
kubectl apply -f hello-world-apply.yaml
```

**Check Deployments**

```bash
kubectl get deployments
```

**Check Pods**

```bash
kubectl get pods
```

**Expose a Deployment**

```bash
kubectl expose deployment/hello-world
```

**Check Services**

```bash
kubectl get services
```

**Inspect Service endpoints**

```bash
kubectl get endpoints hello-world
```

**View application logs**

```bash
kubectl logs <POD_NAME>
```

**Delete Kubernetes resources**

```bash
kubectl delete deployment/hello-world service/hello-world
```


## 📁 Project Structure

```text
.
├── Deployment/
│   └── kubernetes_declarative_approach.yaml
│
├── Pods/
│   ├── Kubernetes_pods.yaml
│   └── imperative_commands_Kubernets.txt
│
├── Services/
│   └── Kubernetes_services.yaml
│
├── Dockerfile.txt
├── Package.json
├── README.md
└── app.js
```

*The YAML files demonstrate different approaches to creating and managing Kubernetes resources.*

## 🎯 Key Learnings

Through this hands-on project, I gained practical experience with:

- Containerising applications using Docker.
- Deploying container images to Kubernetes.
- Understanding Pods, Deployments, and ReplicaSets.
- Managing multiple application replicas.
- Understanding labels, selectors, and resource configurations.
- Exposing applications through ClusterIP Services.
- Understanding Service networking and basic load balancing.
- Using imperative and declarative Kubernetes commands.

## 🔮 Future Improvements

- Explore NodePort and LoadBalancer Services.
- Implement Ingress for external HTTP access.
- Configure Horizontal Pod Autoscaling (HPA).
- Explore rolling updates and rollback strategies.
- Integrate Kubernetes deployment into a CI/CD pipeline.
- Explore advanced traffic management using Istio.

---

**Learning Journey:** IBM DevOps and Software Engineering Professional Certificate

**Focus:** Kubernetes | Docker | Container Orchestration | DevOps

