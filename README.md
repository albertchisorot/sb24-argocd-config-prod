# ArgoCD Config

This repository contains the [Kustomization](https://kustomize.io) settings for ArgoCD.

## Maintenance

If you would like to update ArgoCD configuration (such as adding repositories etc) then update and push these files to bitbucket. Then navigate to the [ArgoCD UI](https://sb24-cicd-server-argocd.apps.cluster-dev-01.ao.sbicdirectory.com/) find the `argocd-app` application and sync to update.

## Bootstrapping

If you would like to migrate to a new cluster. Ensure that ArgoCD is installed in the `argocd` namespace. Ensure that your kubeconfig is updated to point to the target cluster and navigate to the root of this repository in your terminal. Execute
`kubectl diff -k .` to check that it will apply correctly. Once statisfied execute `kubectl apply -k .` to apply the configuration.
After applying you will need to create new [argocd credential template secrets](https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/#repository-credentials) for the image registry and bitbucket.# sb24-argocd-config-prod
