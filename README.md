# ArgoCD App Store
## Description
Model of a central repository for applications deployed through ArgoCD.

The only Argo application object one needs to add to ArgoCD is the a manifest for the ArgoCD itself. It ties the ArgoCD with this very repo and master revision, thus ArgoCD would start monitoring it, and automaticaly deploying all new ArgoCD objects added to here.
```
kubectl apply -f https://raw.githubusercontent.com/maciej-nowak-itc/argo-app-store/main/_argo-app-store.yaml
```

## How to
**This project assumes that ArgoCD objects will be deployed to an existing namespace `argocd` that is managable by your ArgoCD instance.**

In order to start be sure to go through the process of k8s and ArgoCD or be able to connect to working existing instance.

ArgoCD should be tied with some cluster as described at [ArgoCD -> Getting Started](https://argo-cd.readthedocs.io/en/stable/getting_started/).
Example for local [Kind](https://kind.sigs.k8s.io/docs/user/quick-start/) based cluster use
`argocd cluster add kind-kind --grpc-web --insecure --in-cluster`

If you are adding an application that is defined in private repo, be sure that you can access the repo from within the k8s cluster. [Read the docs](https://argo-cd.readthedocs.io/en/stable/user-guide/private-repositories/).