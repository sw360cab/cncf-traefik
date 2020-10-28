# Traefik Autumn Edition - S01E01

## Prerequisites

* K8S (+ kubectl)

## Run

1. Run Kubernetes Cluster in your environment (e.g. Kind, K3s)

       kubectl create -f k8s/traefik

## Setup ARGO CD

    kubectl create namespace argocd
    kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

### Port Forward

    kubectl port-forward svc/argocd-server -n argocd 8081:443

### Get Password

    kubectl get pods -n argocd -l app.kubernetes.io/name=argocd-server -o name | cut -d'/' -f 2
