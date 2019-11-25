## Package and save Helm chart

Let's package up the chart we downloaded if everything looks okay:
`cd /root/testapi; helm package testapi-chart --debug`{{execute}}

Expected output:

Successfully packaged chart and saved it to: /root/testapi/testapi-chart-0.1.0.tgz

Successfully saved /root/testapi/testapi-chart-0.1.0.tgz to /root/.helm/repository/local

Note that this chart has been saved locally.

Update helm repo
`helm update repo`{{execute}}

Search for testapi-chart: (note name for installation)

`helm search testapi-chart`{{execute}}

----- 
