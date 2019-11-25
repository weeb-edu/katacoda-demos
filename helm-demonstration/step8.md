## Cleanup

Now that we have two installs of the helm chart, let's show how to delete one:

`helm ls`{{execute}}

`kubectl get deployments`{{execute}}

`helm delete --purge <name>`{{execute}}

If you're done, go ahead and clean up both. 

`helm delete --purge <other name>`{{execute}}

-----

You have now finished an introduction to creating, saving, installing, and updating Helm charts.

Sláinte!
