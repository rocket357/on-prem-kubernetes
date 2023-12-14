# install the operator
helm repo add projectcalico https://projectcalico.docs.tigera.io/charts

helm install calico projectcalico/tigera-operator --namespace tigera-operator --create-namespace

# configure calico
kubectl apply -f calico-bgp.yaml
