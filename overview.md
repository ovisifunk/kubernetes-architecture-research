# Kubernetes Overview

Kubernetes (pronounced **K8s**) is an open‑source container orchestration platform originally developed by Google and now maintained by the Cloud Native Computing Foundation (CNCF). It automates the deployment, scaling, and management of containerized applications across a cluster of machines (virtual or bare‑metal).

**Key points**
- **Purpose** – Provides a unified API and control plane to run workloads reliably at any scale.
- **Core concepts** – **Pods** (the smallest deployable unit), **Nodes** (worker machines), **Control Plane** (API server, etcd, scheduler, controller manager), **Services** (stable networking), **Volumes** (storage), **ConfigMaps & Secrets** (configuration).
- **Architecture** – A highly available control plane stores desired state in **etcd** and reconciles it via controllers; the **kubelet** on each node ensures the actual state matches.
- **History** – Announced in 2014, released as 1.0 in 2015, now at version 1.35 (2025). Licensed under Apache 2.0.
- **Ecosystem** – Extensible via custom resources, operators, and a rich ecosystem of plugins (CNI, CSI, etc.).

For a deeper dive see the official docs and the Wikipedia article: https://en.wikipedia.org/wiki/Kubernetes.