# 🚀 End-to-End CI/CD Pipeline

> **Python Flask → Docker → GitHub Actions → Kubernetes**

A production-ready CI/CD pipeline demonstrating modern DevOps practices: automated testing, containerization, and zero-downtime Kubernetes deployment.

---

## 🏗️ Architecture

```
Developer Push
      │
      ▼
┌─────────────────────────────────────────────┐
│           GitHub Actions Pipeline            │
│                                             │
│  [Test] ──► [Build & Push] ──► [Deploy]    │
│   pytest     Docker Hub       Kubernetes    │
└─────────────────────────────────────────────┘
      │
      ▼
┌─────────────────┐
│   Kubernetes    │
│  ┌───────────┐  │
│  │  Pod x2   │  │  ← RollingUpdate (zero-downtime)
│  │  Flask App│  │
│  └───────────┘  │
│  Service (ClusterIP)                        │
└─────────────────┘
```

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| App | Python 3.12 + Flask |
| Container | Docker (multi-stage build) |
| Registry | Docker Hub |
| CI/CD | GitHub Actions |
| Orchestration | Kubernetes |

## 🔄 Pipeline Flow

1. **Test** — `pytest` runs on every push
2. **Build** — Multi-stage Docker image built & pushed to Docker Hub
3. **Deploy** — `kubectl apply` with rolling update strategy

## 🔐 Required GitHub Secrets

| Secret | Description |
|--------|-------------|
| `DOCKERHUB_USERNAME` | Docker Hub username |
| `DOCKERHUB_TOKEN` | Docker Hub access token |
| `KUBECONFIG` | base64-encoded kubeconfig |

## 🚦 Key Features

- ✅ **Zero-downtime deployments** via RollingUpdate strategy
- ✅ **Health checks** (liveness + readiness probes)
- ✅ **Non-root container** (security best practice)
- ✅ **Multi-stage Docker build** (smaller image size)
- ✅ **Resource limits** defined for all pods
- ✅ **Automated testing** before every build

## 👩‍💻 Author

**Latifa** — Kubestronaut | DevOps Engineer  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://linkedin.com/in/YOUR_LINKEDIN)
[![Docker Hub](https://img.shields.io/badge/Docker%20Hub-latifaa13-blue)](https://hub.docker.com/u/latifaa13)

