# install metallb
helm install metallb metallb/metallb -f metallb-values.yaml --namespace metallb --create-namespace
