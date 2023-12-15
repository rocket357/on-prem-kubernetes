# install lvm driver
helm install --repo https://helm.metal-stack.io csi-driver-lvm helm/csi-driver-lvm --set lvm.devicePattern='/dev/xvdb'
