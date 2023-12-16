# install cert-manager
helm install cert-manager jetstack/cert-manager --namespace cert-manager --create-namespace --set installCRDs=true

# configure a ClusterIssuer
kubectl apply -f cert-manager-le-prod.yaml
