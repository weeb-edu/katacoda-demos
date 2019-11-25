## Let's create a chart and package it, and then save it locally


`cd /root/testapi; helm package testapi-chart --debug`{{execute}}

Expected output:

Successfully packaged chart and saved it to: /root/testapi/testapi-chart-0.1.0.tgz
[debug] Successfully saved /root/testapi/testapi-chart-0.1.0.tgz to /root/.helm/repository/local

Update helm repo
`helm update repo`{{execute}}

Let's look for our testapi-chart in order to find name for installation:

`helm search testapi-chart`{{execute}}

Install the chart:

`helm install testapi-chart`{{execute}}

Note LAST DEPLOYED information, as well as namespace, pod names, service name, and deployment name

Copy and run commands under NOTES as usual for exporting the POD_NAME and port forwarding the POD_NAME in order to expose the ports for testing.

`helm ls`{{execute}} to see our new helm controlled installation.

-----

Expected output:

master $ helm ls

NAME                    REVISION        UPDATED                         STATUS          CHART                   APP VERSION     NAMESPACE

vociferous-mandrill     5               Mon Nov 25 00:00:45 2019        DEPLOYED        testapi-chart-0.1.1                     default

master $
