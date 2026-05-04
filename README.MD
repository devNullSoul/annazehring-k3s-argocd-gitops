# Inhalt 

Das Repositoriy veranschaulicht die Verwendung des GitOps-Ansatzes
zur Beschleunigung der Deployment-Prozesse.

# Vorbereitung

## Installation von K3D
curl -s https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh | TAG=v5.8.3 bash
k3d cluster create mycluster
kubectl get nodes

Quelle: https://k3d.io/stable/#install-current-latest-release

## Installation von ArgoCD

kubectl create namespace argocd
kubectl apply --server-side --force-conflicts -k https://github.com/argoproj/argo-cd/manifests/crds\?ref\=stable

