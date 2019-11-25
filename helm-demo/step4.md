## Manual update of version number in Chart.yaml

Let's pretend we have a new version to upgrade in our Helm Chart:

`cd /root/testapi ; cat ./testapi-chart/Chart.yaml ; sed -i 's/version: 0.1.0/version: 0.1.1/g' ./testapi-chart/Chart.yaml`{{execute}}
`cat ./testapi-chart/Chart.yaml`{{execute}}

Confirm your version changes before running the upgrade command:

`cd /root/testapi ; helm upgrade <enter podname here> ./testapi-chart`{{execute}}

Check to see the revision number has been incremented by expected number of changes, 
the time/date for update has been updated, and the chart version is correct/as expected.

Success!
`helm ls`{{execute}}

Let's do that one more time to give us some rollback room:

1. Upgrade the version number
`cd /root/testapi ; cat ./testapi-chart/Chart.yaml ; sed -i 's/version: 0.1.1/version: 0.1.2/g' ./testapi-chart/Chart.yaml`{{execute}}
`cat ./testapi-chart/Chart.yaml`{{execute}}

2. Upgrade using helm
`cd /root/testapi ; helm upgrade <enter podname here> ./testapi-chart`{{execute}}

Awesome:
`helm ls`{{execute}}

Now we can rollback one version back with the number 1 in the second parameter below:

`cd /root/testapi ; helm rollback <enter podname here> 1`{{execute}}


`helm ls`{{execute}}

It is also possible to install another cluster in parallel with a second install command, but most use cases will require a rollback or an upgrade.

To install another cluster:
`cd /root/testapi ; helm install ./testapi-chart`{{execute}}

`kubectl get deployments`{{execute}}
`helm ls`{{execute}}
`kubectl get pods`{{execute}}




