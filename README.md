# on-prem-kubernetes
A poor-man's guide to running HA kubernetes in Xen on commodity hardware.

The /tftp folder contains the basic example configs to utilize tftp for pxebooting to install the xen hosts as well as the k8s domUs.  If you install these manually (or automated in another fashion) ignore this folder.

The /xen folder contains the basic example configs for booting a controlplane and worker domU.  
