# Kubernetes Enterprise App Manifests

This repository contains Kubernetes manifests for enterprise applications, organized by namespace and application for clarity and ease of management.

## Structure

- `namespaces/`: Namespace definitions for each enterprise app.
- Each application has its own folder with deployments, database, and services.
- Each app folder contains a `README.md` for app-specific notes.

## How To Use

1. **Create Namespaces**
    ```bash
    kubectl apply -f namespaces/
    ```

2. **Deploy Each App**
    ```bash
    kubectl apply -f jira/
    kubectl apply -f confluence/
    kubectl apply -f artifactory/
    kubectl apply -f jenkins/
    ```

3. **Access Services**
    - See each app’s `README.md` for details.

## Best Practices

- All sensitive data should be handled with Kubernetes Secrets in production.
- Persistent storage is configured for all stateful services and databases.
- Manifests are grouped by app, as used in real enterprise environments.