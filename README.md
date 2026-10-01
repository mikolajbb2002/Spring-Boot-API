# Spring-Boot-API
 k8s,helm,argo

1. To install cluster use 'kind' coomand 

```bash
kind create cluster --name prd-global-cluster-5
```

4. Deploy ArgoCD

```bash
kubectl create namespace argocd

kubectl apply -n argocd --server-side --force-conflicts -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

5. Depend on what cluster contexts you are, apply application set

```bash
kubectl apply -f argocd/applicationset-prod.yaml
```

6. You can get to ArgoCD UI using port-forward via k9s 

7. To use ingress you have to install controller previously 

kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml

8. Then match IngressClassName to IngressClass created or create an alias 
