# Pods & Containers

## Table of Contents
1. [Introduction](#introduction)
2. [Pods Overview](#pods-overview)
3. [Containers in Pods](#containers-in-pods)
4. [Networking](#networking)
5. [Storage & Volumes](#storage--volumes)
6. [Configuration and Secrets](#configuration-and-secrets)
7. [Lifecycle & Management](#lifecycle--management)
8. [Security Aspects](#security-aspects)
9. [Troubleshooting & Best Practices](#troubleshooting--best-practices)
10. [References](#references)

---

## Introduction

- **Purpose**: Overview of Pods and Containers in Kubernetes.
- **Key Concepts**: Lightweight runtime environments, encapsulation of applications, and how containers are managed inside Pods.

---

## Pods Overview

- **Definition**: 
 - A Pod is the smallest deployable unit in Kubernetes (Important Exam Question)
 - Abstract away from container layer which helps in direct interaction with the K8s layer
 (Instead of interacting with containers directly (which involves handling lower-level details like container runtimes, networking, and storage), you work with Pods, and Kubernetes takes care of managing those details for you.)
 - Usually 1 application per pod 
 - We can have like Database Pod, Frontend Pod, Backend Pod

- **Communication between  Pods


- **Characteristics**:
  - Shared network namespace (IP, port space)
  - Shared storage volumes(Persistent Volumes)
- **When to use Pods**:
  - Running a single container
  - Running multiple tightly-coupled containers (sidecars)

---

## Containers in Pods

- **Container Basics**:
  - The basic runtime unit for application execution.
  - Containers run within Pods.
- **Runtime Considerations**:
  - Use of container runtimes (e.g., containerd, CRI-O)
  - How containers are isolated yet share the Pod's resources.
- **Multi-Container Pods**:
  - Sidecar, Ambassador, and Adapter patterns

---

## Networking

- **Pod Networking**:
 - Each Pod gets its own private IP address
 - Frontend Pod can communicate with Database Pod using this internal IP address (not public IP address)
 - IP addresses are ephemeral (temporary) 
 - When replacement pod is created a new IP address will be assigned
 - Containers will run on different ports
 - Containers can talk to each other via localhost
 - Since IP addresses are ephemeral we need to use Services for permanent IP address
 - Ingress to route the traffic into cluster
 

---

## Storage & Volumes

- **Volume Types**:
  - EmptyDir, HostPath, ConfigMap, Secret, PersistentVolumeClaim, etc.
- **Mounting Volumes**:
  - How volumes are shared between containers in a Pod.
- **Data Persistence**:
  - Use cases for ephemeral vs. persistent storage.

---

## Configuration and Secrets

- **ConfigMaps**:
  - Storing non-confidential configuration data.
- **Secrets**:
  - Managing sensitive information.
- **Usage in Pods**:
  - Injecting configuration and secrets into containers.

---

## Lifecycle & Management

- **Pod Lifecycle**:
  - Phases: Pending, Running, Succeeded, Failed, Unknown.
- **Container Lifecycle Hooks**:
  - `postStart` and `preStop` hooks.
- **Probes**:
  - Liveness and readiness probes for health monitoring.

---

## Security Aspects

- **Container Security**:
  - Image vulnerabilities and scanning.
- **Pod Security Policies**:
  - Setting security contexts and privilege levels.
- **Best Practices**:
  - Principle of least privilege and container isolation.

---

## Troubleshooting & Best Practices

- **Common Issues**:
  - CrashLoopBackOff, image pull errors, networking issues.
- **Debugging Tools**:
  - `kubectl describe pod`, `kubectl logs`
- **Best Practices**:
  - Resource limits and requests, appropriate logging and monitoring.

---

## References

- [Kubernetes Blog 2015](https://kubernetes.io/blog/2015/04/borg-predecessor-to-kubernetes/)
- [Kubernetes Official Documentation](https://kubernetes.io/docs/)
- [Andrew Brown](https://www.youtube.com/watch?v=AplluksKvzI&t=3167s)
- [My Favorite Video - She is the best](https://www.youtube.com/watch?v=X48VuDVv0do)

---


