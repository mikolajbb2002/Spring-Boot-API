# Spring-Boot-API
 k8s,helm,argo

1. To install cluster use 'kind' coomand 

```bash
kind create cluster --name prd-global-cluster-5
```

2. Create chart template for spring-boot-api  

```bash 
helm create app_chart
```

3. Change the values in values file and then install helm chart 

```bash
helm install app_chart app_chart --namespace default
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


