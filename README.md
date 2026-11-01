# Secure Multi-Tier E-Commerce & Food Delivery Platform on Kubernetes

A production-ready Kubernetes infrastructure architecture built to simulate a high-availability, secure backend environment for an e-commerce / food delivery platform.

## Architecture & Features

- **Isolated Namespace:** Segmented deployment under `ecommerce-prod`.
- **Least Privilege Access (RBAC):** Configured dedicated `ServiceAccount`, `Role`, and `RoleBinding` to restrict cluster API access.
- **Credential & Config Management:** Separated app configuration via `ConfigMap` and base64-encoded `Secrets` for sensitive DB parameters.
- **Database Tier:** Single-pod PostgreSQL database exposed via an internal `ClusterIP` service.
- **Scalable Application Tier:** Replicated NGINX web app pods bound to custom ServiceAccounts.
- **Layer 7 Ingress Routing:** Configured NGINX Ingress Controller with host-based routing (`delivery.local`).

## Manifest Directory Structure

```text
k8s-ecommerce-platform/
├── manifests/
│   ├── 01-namespace.yaml
│   ├── 02-configmap.yaml
│   ├── 03-secret.yaml
│   ├── 04-rbac.yaml
│   ├── 05-postgres-db.yaml
│   ├── 06-web-app.yaml
│   └── 07-ingress.yaml
└── README.md
