# Jira on Kubernetes

This folder contains manifests to deploy Jira Software on Kubernetes with PostgreSQL and persistent storage.

## Deploy Steps

### 1. Create the namespace:
```sh
kubectl apply -f ../namespaces/jira-namespace.yaml
```
### 2. Create persistent volumes:
```sh
kubectl apply -f pvc.yaml
```
### 3. Deploy PostgreSQL:
```sh
kubectl apply -f postgres.yaml
```
###
4. Deploy Jira:
```sh
kubectl apply -f deployment.yaml
```
### 5. Create the Jira service:
```sh
kubectl apply -f service.yaml
```
### 6. Expose via ngrok:
- Find your Minikube IP:
  ```
  minikube ip
  ```
- Start ngrok on port 30080:
  ```
  ngrok http <minikube-ip>:30080
  ```
- Access Jira via the ngrok URL.

## Default Credentials

- **PostgreSQL User:** `jirauser`
- **PostgreSQL Password:** `jirapassword`
- **Database:** `jiradb`

> **Note:** For production, store secrets in Kubernetes Secrets, not in plain YAML.

### 🟢 How to Deploy the Stack
```sh
kubectl apply -f namespaces/jira-namespace.yaml
kubectl apply -f jira/pvc.yaml
kubectl apply -f jira/postgres.yaml
kubectl apply -f jira/deployment.yaml
kubectl apply -f jira/service.yaml
```
### 🟡 Expose with ngrok
```sh
minikube ip
ngrok http <minikube-ip>:30080
```