# Inhalt 

Mit GitOps wissen wir jederzeit exakt, welche Version in Produktion läuft, und können innerhalb weniger Minuten auf eine funktionierende Version zurückgehen.
Neue Features erreichen den Kunden deutlich schneller und vor allem zuverlässig.

Jede Änderung wird automatisiert gebaut und als eindeutig versionierte Anwendung bereitgestellt.
Die gewünschte Version wird zentral im System definiert und automatisch in die Zielumgebung ausgerollt.

Dadurch ist jederzeit nachvollziehbar, welche Änderung von wem wann in welcher Umgebung aktiv ist.
Deployments werden reproduzierbar, sicher und unabhängig von manuellen Eingriffen.

# Vorbereitung

## Installation von K3D
curl -s https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh | TAG=v5.8.3 bash
k3d cluster create mycluster
kubectl get nodes

Quelle: https://k3d.io/stable/#install-current-latest-release

## Installation von ArgoCD

kubectl create namespace argocd
kubectl apply --server-side --force-conflicts -k https://github.com/argoproj/argo-cd/manifests/crds\?ref\=stable
kubectl apply --server-side --force-conflicts -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

