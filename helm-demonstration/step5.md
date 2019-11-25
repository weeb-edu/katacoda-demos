
## Manual update of version number in Chart.yaml

Example output:

master $ helm ls

NAME                    REVISION        UPDATED                         STATUS          CHART                   APP VERSION     NAMESPACE

vociferous-mandrill     5               Mon Nov 25 00:00:45 2019        DEPLOYED        testapi-chart-0.1.1                     default


Let's pretend we have a new version to upgrade in our Helm Chart:

`cd /root/testapi ; cat ./testapi-chart/Chart.yaml ; sed -i 's/version: 0.1.0/version: 0.1.1/g' ./testapi-chart/Chart.yaml`{{execute}}
`cat ./testapi-chart/Chart.yaml`{{execute}}

---- NOTE: replace this with ENV variable templating ----

---- NOTE: explain use cases for values.yaml files ----

Confirm your version changes before running the upgrade command:

For the following commands, you will have to replace the <name> value with the custom name created by Kubernetes.

Name: A non-empty string guaranteed to be unique within a given scope at a particular time; used in resource URLs; provided by clients at creation time and encouraged to be human friendly; intended to facilitate creation idempotence and space-uniqueness of singleton objects, distinguish distinct entities, and reference particular entities across operations.

See the Kubernetes documentation for further detail.

`cd /root/testapi ; helm upgrade <replace with your name, e.g., vociferous-mandrill> ./testapi-chart`{{execute}}

Check to see the revision number has been incremented by expected number of changes, 
the time/date for update has been updated, and the chart version is correct/as expected.

Success!
`helm ls`{{execute}}

Let's do that one more time to give us some rollback room:

1. Upgrade the version number
`cd /root/testapi ; cat ./testapi-chart/Chart.yaml ; sed -i 's/version: 0.1.1/version: 0.1.2/g' ./testapi-chart/Chart.yaml`{{execute}}
`cat ./testapi-chart/Chart.yaml`{{execute}}

2. Upgrade using helm
`cd /root/testapi ; helm upgrade <name> ./testapi-chart`{{execute}}

Awesome!
`helm ls`{{execute}}
