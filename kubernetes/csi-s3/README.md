# install the csi-s3 storageclass csi driver
helm install csi-s3 yandex-s3/csi-s3 -n k8s-csi-s3 --create-namespace --values k8s-csi-s3-values.yaml
