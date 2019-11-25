## Install another instance of helm chart 

It is also possible to install another cluster in parallel with a second install command, but most use cases will require a rollback or an upgrade.

To install another cluster:
`cd /root/testapi ; helm install ./testapi-chart`{{execute}}

`kubectl get deployments`{{execute}}
`helm ls`{{execute}}
`kubectl get pods`{{execute}}

## Cleanup

Now that we have two installs of the helm chart, let's show how to delete one:

`helm ls`{{execute}}
`kubectl get deployments`{{execute}}

`helm delete --purge <livid-llama or your relevant helm name>`{{execute}}

If you're done, go ahead and clean up both. 

`helm delete --purge <the other relevant helm name>`{{execute}}

-----

You have now finished an introduction to creating, saving, installing, and updating Helm charts.

Sláinte!
