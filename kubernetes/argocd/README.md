# install argocd
helm install argo-cd argo/argo-cd --values argo_ha-values.yaml --namespace argocd --create-namespace

# configuration of argocd
https://www.linuxquestions.org/questions/blog/rocket357-328529/on-prem-kubernetes-part-5-39102/

# adding the "app of apps" directory
Create a new app in ArgoCD.  Point it to your repo (or a fork of this repo, if you wish).
Path within the repo should be kubernetes/app-of-apps/

This will install all of the apps listed in the app-of-apps folder as new Applications within
ArgoCD, which will then be installed.  If you change the folder layout, please double check the
paths within the app-of-apps yaml definitions to ensure they match up, otherwise the created
apps will not install correctly.
