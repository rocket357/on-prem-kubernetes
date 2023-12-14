# on-prem-kubernetes
A poor-man's guide to running HA kubernetes in Xen on commodity hardware.

Tested on Debian bookworm on HP Z240 desktop devices with an OpenBSD dhcpd/tftpd server handing out the pxeboot files.  These configuration files assume the only OS that will be running on the desktop machines is Debian/Xen running Debian domUs.  **DO NOT RUN THE TFTP CONFIGS AGAINST HOSTS THAT HAVE DATA YOU WISH TO KEEP!**

The /etc/ folder contains the haproxy and keepalived example configs to utilize for HA kubernetes control plane configuration, as explained in [my blog series that this code refers to](https://www.linuxquestions.org/questions/blog/rocket357-328529/on-prem-kubernetes-part-2-5-39097/).

The /tftp folder contains the basic example configs to utilize tftp for pxebooting to install the xen hosts as well as the k8s domUs.  If you have installed your hosts manually (or automated in another fashion), ignore this folder.

The /xen folder contains the basic example configs for booting a controlplane and worker domU.  At minimum, you will need one configuration for each domU, with a unique MAC address, disk LVM assignment, and name.
