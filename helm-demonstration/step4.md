
## Install the Chart

Inspect the chart for further detail:

`helm inspect testapi-chart`{{execute}}

Install the chart:

`helm install testapi-chart`{{execute}}

Note LAST DEPLOYED information, as well as namespace, pod names, service name, and deployment name

Copy and run commands under NOTES as usual for exporting the POD_NAME and port forwarding the POD_NAME in order to expose the ports for testing.

`helm ls`{{execute}} to see our new helm controlled installation.

-----


