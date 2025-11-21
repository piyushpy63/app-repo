🚀 GitOps-Based CI/CD Pipeline using GitHub Actions, DockerHub, ArgoCD & Kubernetes

This project demonstrates a fully automated GitOps CI/CD pipeline where code changes made in Repo A automatically trigger:
1. CI Pipeline (GitHub Actions)
2. Docker Image Build (multi-arch: amd64 + arm64)
3. Image Push to Docker Hub
4. Manifest Update in Repo B
5. ArgoCD Auto-Sync
6. Continuous Deployment to Kubernetes (Minikube)

## File Structure
```

📁 Repository Structure

.
├── app-repo/                             # Application source code + CI pipeline
│   ├── app.py                            # Python Flask application
│   ├── requirements.txt                  # Python dependencies
│   ├── Dockerfile                        # Multi-arch Docker image build
│   └── .github/
│       └── workflows/
│           └── ci-cd.yml                 # GitHub Actions CI/CD pipeline
│
└── manifest-repo/                        # Kubernetes GitOps manifests watched by ArgoCD
    ├── deployment.yaml                   # Deployment manifest updated automatically by CI
    └── service.yaml                      # NodePort service to expose the application

```

## Prerequisites

- Python 3.11+
- Docker & DockerHub Account (to build and push multi-arch images)
- GitHub Personal Access Token (PAT) with repo scope
- Minikube (local Kubernetes cluster)
- ArgoCD
- GitHub Actions enabled in Repo A

## Project Impact
- Achieved fully automated end-to-end deployments with zero manual intervention by integrating GitHub Actions, ArgoCD, DockerHub, and Kubernetes.
- Reduced deployment time from minutes to under 10 seconds, enabling instant rollout of new application versions.
- Ensured consistent and reliable environments by using GitOps principles—ArgoCD continuously synced manifests and self-healed drift.
- Delivered multi-architecture Docker images (amd64 + arm64) ensuring compatibility across cloud clusters and local ARM-based Minikube.
- Improved deployment reliability and developer productivity through automated testing, image building, and manifest updates triggered directly from Git pushes.
