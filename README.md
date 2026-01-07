# Sandbox Hub

![Go](https://img.shields.io/badge/Go-1.21-blue)
![Kubernetes](https://img.shields.io/badge/Kubernetes-1.27-blueviolet)
![Crossplane](https://img.shields.io/badge/Crossplane-1.14-lightgrey)
![License](https://img.shields.io/badge/License-MIT-green)

> **Sandbox Hub** is a cloud-native, developer-focused sandbox management platform leveraging Go, Kubernetes, Crossplane, and Backstage. It allows developers to create, manage, and observe isolated environments for experimentation, testing, or learning.

---

## Table of Contents

1. [Project Overview](#project-overview)  
2. [Tech Stack](#tech-stack)  
3. [Phased Roadmap](#phased-roadmap)  
4. [Conceptual Workflow](#conceptual-workflow)  
5. [Pro-Tips for Internship / Portfolio](#pro-tips-for-internship--portfolio)  
6. [Getting Started](#getting-started)  
7. [License](#license)  

---

## Project Overview

**Purpose:**  
Sandbox Hub provides developers with a platform to manage **isolated sandbox environments**, containerized and orchestrated for scalable cloud-native workflows.  

**Key Objectives:**  
- Create, list, and delete sandbox environments.  
- Support multiple sandbox templates (Python, Node, Go).  
- Enable containerized execution using Podman/Docker.  
- Integrate Kubernetes for scalable orchestration.  
- Use Crossplane for declarative infrastructure provisioning.  
- Offer a developer dashboard via Backstage.  
- Implement observability, reconciliation, and security best practices.  

---

## Tech Stack

| Layer | Technology | Purpose |
|-------|------------|---------|
| Backend | Go | Sandbox orchestration & API |
| Containers | Podman / Docker | Sandbox execution environment |
| Orchestration | Kubernetes | Scalable and isolated environments |
| Declarative Infra | Crossplane | Declarative sandbox provisioning |
| Developer Portal | Backstage | UI dashboard for sandbox management |
| Data Storage | SQLite / In-Memory DB | Track sandbox state and metadata |
| Optional | Prometheus / Grafana | Observability & metrics |

---

## Phased Roadmap

### Phase 0: Preparation
- Install Go, Podman/Docker, Kubernetes (Minikube/Kind).  
- Install Crossplane and Backstage.  
- Learn Kubernetes objects and Go APIs.  

### Phase 1: MVP – Local Sandbox Manager
- Backend API to create, list, delete sandboxes.  
- Sandboxes initially run as local processes or simple containers.  
- Optional HTML frontend for testing.  

### Phase 2: Containerized Sandboxes
- Containerize sandbox templates (Python, Node, Go).  
- Track dynamic ports and container IDs.  
- Auto-cleanup for inactive sandboxes.  
- Optional log streaming for observability.  

### Phase 3: Kubernetes Sandbox Management
- Each sandbox runs as a Kubernetes Deployment/Pod.  
- Use Services and Namespaces for isolation.  
- Backend tracks sandbox status.  

### Phase 4: Crossplane Integration
- Define Crossplane CRDs for sandbox templates.  
- Backend interacts with Crossplane for creation, tracking, and deletion.  
- Optionally provision cloud resources per sandbox.  

### Phase 5: Backstage Integration
- Backstage plugin connects to backend API.  
- Features: create, list, delete sandboxes, view logs/status.  
- Optional RBAC for user permissions.  

### Phase 6: Pro-Level Features
- **Observability:** Stream sandbox logs to the UI.  
- **Reconciliation Loop:** Detect and fix orphaned resources.  
- **Security:** Namespace isolation, network policies, CPU/memory limits.  
- Optional: multi-resource sandboxes, monitoring, audit logs.  

### Phase 7: Deliverables / Internship Demo
- Incremental demoable phases: MVP → K8s → Crossplane → Backstage → Pro-level features.  

---

## Conceptual Workflow

```text
User (Developer)
    ↓
Backstage Dashboard (UI)
    ↓
Go Backend API
    ↓
Crossplane CRDs / Kubernetes
    ↓
Sandbox Environment (Container / Pod / Cloud Resource)
