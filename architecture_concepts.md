# Kubernetes Architectural Concepts

## Control Plane
- **API Server** – Central entry point for all RESTful calls; validates and persists desired state in **etcd**.
- **etcd** – Distributed key‑value store that holds the cluster configuration and state.
- **Scheduler** – Assigns newly created **Pods** to suitable **Nodes** based on resource requirements, affinity, taints, etc.
- **Controller Manager** – Runs core controllers (ReplicaSet, Deployment, StatefulSet, DaemonSet, Job, etc.) that continuously reconcile the actual state with the desired state.

## Nodes (Worker Machines)
- **kubelet** – Agent that ensures containers in Pods are running as defined; communicates node status to the API server.
- **kube-proxy** – Implements Service networking (load‑balancing, virtual IPs) and network policies on each node.
- **Container Runtime** – Executes containers (e.g., containerd, CRI‑O) via the Container Runtime Interface (CRI).

## Workloads & Primitives
- **Pod** – Smallest deployable unit; one or more tightly‑coupled containers sharing network and storage namespaces.
- **Deployment** – Declarative controller for stateless applications; manages ReplicaSets.
- **StatefulSet** – Provides stable network IDs and storage for stateful workloads.
- **DaemonSet** – Ensures a copy of a Pod runs on every (or selected) Node.
- **Job / CronJob** – Runs batch or scheduled tasks.

## Services & Networking
- **Service** – Stable abstraction (ClusterIP, NodePort, LoadBalancer) exposing a set of Pods.
- **Ingress** – HTTP/HTTPS routing layer; integrates with Ingress Controllers.
- **Network Policies** – Controls traffic flow between Pods.
- **CNI Plugins** – Pluggable networking implementations (Calico, Cilium, Flannel, etc.).
- **DNS** – CoreDNS provides service discovery within the cluster.

## Storage
- **Volumes** – Abstract storage accessible to Pods (emptyDir, hostPath, ConfigMap, Secret, etc.).
- **PersistentVolumes (PV) & PersistentVolumeClaims (PVC)** – Decouples storage provisioning from Pod specifications.
- **StorageClasses** – Defines classes of storage (e.g., SSD, HDD) for dynamic provisioning via CSI drivers.

## Configuration & Security
- **ConfigMaps & Secrets** – Externalize configuration data and sensitive information.
- **RBAC** – Role‑Based Access Control for API permissions.
- **Admission Controllers** – Extensible hooks for policy enforcement (e.g., PodSecurityAdmission).
- **Certificates & TLS** – Secures communication between components.

## Extensibility
- **Custom Resource Definitions (CRDs)** – Allows users to define new API objects.
- **Operators** – Pattern for managing complex applications via controllers.
- **API Aggregation** – Extends the API server with additional services.

These concepts form the foundation for building, operating, and scaling containerized micro‑services on Kubernetes.