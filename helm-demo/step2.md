## Let's download an example chart

Download:
`git clone https://github.com/daemonza/testapi.git; cd testapi`{{execute}}

Credit to Daemonza for the excellent tutorial:
https://daemonza.github.io/2017/02/20/using-helm-to-deploy-to-kubernetes/

A chart has the following structure: 
`tree ./testapi-chart/`{{execute}}

Examine contents on the command line. To get you started:
`cat ./testapi-chart/Chart.yaml`{{execute}}
`cat ./testapi-chart/values.yaml`{{execute}}

Helm lint check the chart:
`cd /root/testapi ; helm lint .`{{execute}}

Looks good!


