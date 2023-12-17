# install argocd
helm install argo-cd argo/argo-cd --values argo_ha-values.yaml --namespace argocd --create-namespace

# configuration of argocd
https://www.linuxquestions.org/questions/blog/rocket357-328529/on-prem-kubernetes-part-5-39102/
