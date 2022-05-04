
## About

ArgoCD Tutorial for Beginners | GitOps CD for Kubernetes

This ArgoCD crash course teaches you everything to get started with ArgoCD. ArgoCD is a GitOps continuous delivery tool that is gaining popularity in the DevOps world.
First, you will learn what ArgoCD is and what are the common use cases or why we need ArgoCD. 
Then, you will see how ArgoCD actually works and how it does its job.
In the final part, we will do a hands-on demo project, where we deploy ArgoCD in Kubernetes and setup a fully automated CD pipeline for Kubernetes configuration changes to get some practical experience with ArgoCD. 

Credits to Nana :- https://youtu.be/MeU5_k9ssrs

## Deployment

To deploy this project run

```bash
# install ArgoCD in k8s
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# access ArgoCD UI
kubectl get svc -n argocd
kubectl port-forward svc/argocd-server 8080:443 -n argocd

# login with admin user and below token (as in documentation):
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo

# you can change and delete init password
```

## Links


```bash
Config repo: https://gitlab.com/nanuchi/argocd-app-config

Docker repo: https://hub.docker.com/repository/docker/nanajanashia/argocd-app

Install ArgoCD: https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd

Login to ArgoCD: https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli

ArgoCD Configuration: https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/

```
