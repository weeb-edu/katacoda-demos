## Install another instance of helm chart 

It is also possible to install another cluster in parallel with a second install command, but most use cases will require a rollback or an upgrade.

To install another cluster:
`cd /root/testapi ; helm install ./testapi-chart`{{execute}}

`kubectl get deployments`{{execute}}
`helm ls`{{execute}}
`kubectl get pods`{{execute}}


