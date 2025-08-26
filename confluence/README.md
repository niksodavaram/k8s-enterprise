# Confluence on Kubernetes

This folder contains manifests to deploy Atlassian Confluence with PostgreSQL and persistent storage.

## How to Deploy

1. Create the namespace:
```sh
kubectl apply -f ../namespaces/confluence-namespace.yaml
```
2. Create persistent volumes:
```sh
kubectl apply -f pvc.yaml
```
