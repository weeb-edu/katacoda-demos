## Install kubernetes cluster

Let's prep the mounts

`chmod 777 -R /mnt/data*`{{execute}}

Create persistent volumes

`kubectl apply -f pv.yaml`{{execute}}
