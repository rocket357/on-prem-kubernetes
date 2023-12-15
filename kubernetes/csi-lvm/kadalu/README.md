# install kadalu operator/driver
taken from: https://github.com/kadalu/kadalu
# first download the chart and set the default env
K8S_DIST=kubernetes

curl -sL https://github.com/kadalu/kadalu/releases/latest/download/kadalu-helm-chart.tgz -o /tmp/kadalu-helm-chart.tgz

# next install operator
helm install operator --namespace kadalu --create-namespace /tmp/kadalu-helm-chart.tgz --set operator.enabled=true --set global.kubernetesDistro=$K8S_DIST

# now install the csi driver the operator will manage
helm install csi-nodeplugin --namespace kadalu /tmp/kadalu-helm-chart.tgz --set csi-nodeplugin.enabled=true --set global.kubernetesDistro=$K8S_DIST

# now we need to tell kadalu what host devices to use, and for that we need the kadalu kubectl plugin...so let's install it!
curl -fsSL https://github.com/kadalu/kadalu/releases/latest/download/install.sh | sudo bash -x

# and set up a storageclass by telling kadalu what hosts/drives to use...
kubectl kadalu storage-add storage-pool-1 --device kube1:/dev/xvdc
